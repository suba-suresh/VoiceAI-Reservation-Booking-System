# Crown Street Food – Voice AI Booking Assistant

This project integrates a **Voice AI Assistant** (via Vapi) with **Make.com**, **Google Calendar**, and **Gmail** to automate restaurant table bookings for **Crown Street Food** in Lillington.  

Customers can book, edit, or cancel reservations using natural voice commands. The system updates Google Calendar in real-time and sends confirmation or cancellation emails automatically.

---

## 📌 Business Use Case & Purpose
- **Business Use Case**:  
  Crown Street Food wants to provide a modern, AI-driven reservation system. Customers can speak naturally to make or manage bookings, while the restaurant’s staff spend less time handling calls manually.  

- **Purpose**:  
  - Save staff time and reduce errors in reservations  
  - Deliver a fast and voice-friendly booking experience  
  - Keep reservations organized in **Google Calendar**  
  - Ensure customers receive timely confirmation/cancellation emails  

---

## ⚙️ Workflow Overview
1. **Voice AI Assistant (Vapi)** collects booking intent and details.  
2. **Make.com Webhook** receives data from Vapi.  
3. **Router** determines action:  
   - **Create Event** → Adds booking in Google Calendar → Sends confirmation email  
   - **Update Event** → Updates booking using `booking_id` → Sends updated confirmation email  
   - **Delete Event** → Cancels booking using `booking_id` → Sends cancellation email  
4. **Webhook Response** returns confirmation back to Vapi to continue the voice conversation.  

---

## 🛠️ Integrations
- **Vapi** → Voice AI Assistant that talks with customers  
- **Make.com** → Orchestration platform  
- **Google Calendar** → Stores reservations  
- **Gmail** → Sends booking confirmations & cancellations  
- **Webhook Response** → Ensures smooth conversation with the AI  

---

## 🚀 Future Enhancements
- Automated reminders (24h & 2h before booking) via email or SMS  
- Availability check before confirming new bookings  
- Customer history tracking (Google Sheets/Airtable)  
- Pre-payment or deposit collection for large parties  
- Multi-channel support (WhatsApp, Messenger, Website chat)  
- Analytics dashboard for booking trends  

---

## 📂 Repository Structure
/scenarios
 └── booking-system.json # Exported Make.com scenario blueprint
/screenshots
 └── scenario.png        # Visual workflow screenshot


---

## 📸 Screenshots
Example:
![Scenario Overview](./screenshots/scenario.png)

---

## 📑 System Prompt (Vapi)
The assistant is configured with a system prompt that defines restaurant info, booking flow, date handling, and error handling rules. See the [System Prompt](./SYSTEM_PROMPT.md) file for full details.

---

## 🔧 How to Use
1. Import the `booking-system.json` file into **Make.com**.  
2. Connect your **Google Calendar** and **Gmail** accounts.  
3. Deploy your Vapi assistant with the included system prompt.  
4. Run the scenario → start making bookings by voice!  

---

## 📌 Short Description
> A **voice-driven restaurant booking system** that connects Vapi with Make.com, Google Calendar, and Gmail. Customers can book, update, or cancel tables by voice, while the system handles confirmations, emails, and calendar updates automatically.

---
