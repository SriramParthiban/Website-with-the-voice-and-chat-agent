# 💬 Chat Agent – AI-Powered Appointment Booking System

## 📌 Overview
Chat Agent is an AI-driven appointment scheduling assistant built using **n8n, OpenAI, and Google Calendar**.  
It automates customer interactions over chat by understanding natural language, extracting booking details, and performing real-time calendar actions such as checking availability, booking, rescheduling, or canceling appointments.

This workflow works across platforms like:
- WhatsApp Business API (Twilio, WATI, Gupshup)
- Instagram DM / Facebook Messenger
- Website chatbot
- CRM chat widgets

---

## 🚀 Features

| Feature | Description |
|--------|-------------|
| 💬 Chat-based conversation | Customer books appointments via chat |
| 🧠 NLP intelligence | Extracts name, service, date, time & intent |
| 🤖 AI decision logic | Determines whether to book, check, or cancel |
| 📅 Calendar automation | Google Calendar create + delete + availability check |
| ✅ Double-booking protection | Ensures slot conflicts are avoided |
| 🧭 Contextual reasoning | Understands time, dates, and follow-up questions |
| 🔐 Validation rules | Booking only happens after collecting required info |

---

## 🧩 Workflow Structure

| Node | Function |
|------|---------|
| **Webhook / Chat Trigger** | Receives incoming chat text |
| **OpenAI Chat Model** | Extracts details + identifies intent |
| **Switch Node** | Routes logic based on intent (book / check / cancel) |
| **Date-Time Parser** | Converts user time to system timestamp |
| **Google Calendar Nodes** | Search, create, or delete appointments |
| **Response Node** | Sends the message back to the user |

---

## 🧠 AI Understanding

The agent extracts:
- Customer name  
- Phone / chat identifier  
- Service / appointment type  
- Preferred date & time  
- Notes / issue description (if applicable)  
- Intent: `check_availability` | `book_appointment` | `cancel_appointment`

Example input:
> "Hey, can I book a haircut tomorrow around 4pm?"

| Intent               | Action                            |
| -------------------- | --------------------------------- |
| ✅ Check availability | Searches calendar for open slots  |
| 📅 Book appointment  | Creates Google Calendar event     |
| ❌ Cancel appointment | Searches + deletes matching event |
| 🔄 Reschedule        | Cancels old slot + books new one  |



⚙️ Setup Guide
1️⃣ Import Workflow

Upload the Chat-Agent.json workflow file into n8n.

2️⃣ Add Credentials

Google Calendar OAuth

OpenAI API Key

Chat API key (Twilio / WATI / Webhook etc.)

3️⃣ Update Webhook URL

Replace placeholder webhook URL with your live endpoint.

4️⃣ Enable Workflow

Test with a real chat message or sample payload.

✅ Ideal Use Cases

Clinics / Hospitals / Dentists

Salons / Spas / Beauty services

Automating demo bookings for SaaS businesses

Consulting / Coaching / Agencies

Home service businesses (repairs, cleaning, AC service, etc.)

📎 Notes

Dynamic rescheduling can be enabled

Can store booking logs in Sheets / Airtable / CRM

Supports multi-agent upgrade (booking + reminders + follow-ups)

🎯 Result

A fully-automated AI chat booking agent that:

Understands customers naturally

Manages appointments end-to-end

Eliminates manual scheduling
