Case Study: AI-Powered Restaurant Booking Automation
### 1. Introduction

Crown Street Food, a local restaurant in Lillington, faced challenges with manual booking management. Staff were spending significant time handling calls, managing double-bookings, and confirming reservations manually.

To solve this, I built an AI-powered booking assistant using:

- Vapi (Voice AI Assistant)

- Make.com (automation & integration)

- Google Calendar (single source of truth for reservations)

- Gmail (customer confirmations)

### 2. Problem Statement

- Manual calls → prone to human error

- No centralized booking system → double-bookings possible

- Time-consuming for staff to confirm or cancel bookings

- Customers lacked instant confirmation

### 3. Solution Overview

- I designed a CRUD-based booking automation workflow:

* Create → AI captures booking request → Webhook → Calendar event created → Confirmation email sent

* Read → AI checks existing bookings in Calendar → returns availability

* Update → Customer requests change → AI finds event by Booking ID or name+time → updates details → sends confirmation

* Delete → Customer cancels → AI finds event → deletes → sends cancellation email

### 4. Workflow Architecture

* Vapi AI → Collects booking details from customer (name, guests, date, time, email).

* Webhook to Make.com → Routes request into automation.

* Router in Make.com → Directs request to Create / Read / Update / Delete branch.

* Google Calendar Module → Stores and manages events.

* Gmail Module → Sends booking confirmation or cancellation email.

* Webhook Response → Returns AI confirmation message instantly.



### 📌 See Screenshot-(./workflow_overview.png)

### 5. Business Impact

- Reduced booking errors by ensuring Google Calendar is the source of truth.

- Improved customer satisfaction with instant confirmations.

- Freed up staff from manual call management.

- Scalable to SMS/WhatsApp reminders in the future.

### 6. Future Enhancements

- SMS reminders (via Twilio or Vonage).

- Daily summary email to restaurant staff with upcoming reservations.

- Loyalty tracking (frequent diners, special offers).

- Multi-language support for diverse customer base.

### 7. Key Learnings

- Importance of router + filters in Make.com to separate CRUD operations.

- Handling Booking ID vs Search Event for updates/deletions.

- Best practices for exposing automation projects on GitHub (document, don’t expose live webhooks).
