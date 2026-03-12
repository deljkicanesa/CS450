Proposal for a Beauty Salon Management System
1. Business Understanding
1.1 Overview

This proposal presents a customized software solution for managing Isabella’s beauty salon. The salon offers multiple beauty services and requires a centralized system to manage appointments, customers, employees, payments, and operational reporting.

1.2 Core Business Processes

The main business processes of the salon are:

registering and managing customers

scheduling appointments

assigning employees to services

tracking service delivery

processing payments

sending reminders and notifications

generating operational and financial reports

1.3 Main Services Offered

The salon offers a variety of services, such as:

haircuts

hair coloring

hairstyling

manicure

pedicure

makeup

facials

eyebrow treatments

1.4 Pain Points Without Software

Without a software solution, the salon faces several challenges:

appointments are tracked manually through calls, messages, or notebooks

risk of double booking

cancellations may not be recorded properly

employee availability is hard to track

customer history is not centralized

payment records are manual and error-prone

reporting is difficult and time-consuming

1.5 Goals of the System

The goals of the system are:

improve appointment organization

reduce scheduling errors

centralize customer and employee information

track payments accurately

improve customer communication through reminders

provide useful reports for decision-making

support future online booking

2. Functional Features
2.1 Customer Management

The system should allow users to:

register new customers

store contact information

view appointment history

track preferred services and notes

2.2 Appointment Scheduling

The system should allow:

creating appointments

assigning services and employees

checking employee availability

rescheduling and canceling appointments

preventing double booking

2.3 Staff Management

The system should support:

employee profiles

assigned skills/services

work schedules

availability tracking

2.4 Payments and Billing

The system should support:

recording payments

payment methods such as cash and card

invoice or receipt generation

daily revenue tracking

2.5 Notifications

The system should provide:

appointment reminders

cancellation notifications

schedule update notifications

2.6 Reports

The system should generate:

daily and monthly revenue reports

most popular services

employee workload reports

appointment statistics

cancellation reports

3. Domain Model (Conceptual)
3.1 Main Entities / Aggregates

Main domain entities include:

Customer

Employee

Service

Appointment

Payment

Notification

3.2 Relationships

A customer can have many appointments.

An appointment belongs to one customer.

An appointment may include one or more services.

An employee can perform many appointments.

A service can be performed by one or more employees, depending on skills.

An appointment may have one payment.

Notifications are linked to appointments and customers.

3.3 Important Business Rules

An employee cannot have two appointments at the same time.

An appointment must have a date, time, customer, and at least one service.

Only qualified employees can perform certain services.

A payment can only be recorded for a completed appointment.

Canceled appointments should not be billed.

Notifications should be sent before scheduled appointments.

3.4 Value Objects

Possible value objects:

FullName

PhoneNumber

EmailAddress

Money

TimeSlot

ServiceDuration

4. Database Structure (High-Level)
4.1 Customers

Fields:

CustomerID (PK)

FirstName

LastName

Phone

Email

Notes

4.2 Employees

Fields:

EmployeeID (PK)

FirstName

LastName

Role

Phone

Email

Status

4.3 Services

Fields:

ServiceID (PK)

ServiceName

Description

DurationMinutes

Price

4.4 Appointments

Fields:

AppointmentID (PK)

CustomerID (FK)

EmployeeID (FK)

AppointmentDate

StartTime

EndTime

Status

Notes

4.5 AppointmentServices

Fields:

AppointmentServiceID (PK)

AppointmentID (FK)

ServiceID (FK)

PriceAtBooking

4.6 Payments

Fields:

PaymentID (PK)

AppointmentID (FK)

Amount

PaymentMethod

PaymentDate

PaymentStatus

4.7 Notifications

Fields:

NotificationID (PK)

AppointmentID (FK)

CustomerID (FK)

NotificationType

SentAt

Status

5. User Roles and Permissions
5.1 Owner / Administrator

Can:

view all data

create, edit, and delete customers, employees, services, appointments, and payments

approve schedule changes

access all reports

5.2 Staff Member

Can:

view own schedule

view assigned appointments

update appointment status

view limited customer details relevant to service delivery

5.3 Receptionist

Can:

view schedules

create and edit appointments

manage customers

record payments

send notifications

cannot delete core financial records without permission

5.4 Customer (Optional)

Can:

view available slots

create booking requests

view own appointments

cancel or reschedule according to salon policy
