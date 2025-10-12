# 🗣️ Voice Agent – AI-Powered Appointment Booking Workflow

## 📌 Overview
**Voice Agent** is an intelligent appointment booking system built using **n8n**, **OpenAI**, and **Google Calendar**.  
It functions as a **smart conversational assistant** that understands natural speech, interprets intent, and performs real-world actions such as checking availability, booking, or canceling appointments automatically.

This workflow seamlessly connects **AI reasoning** with **calendar automation**, making it ideal for businesses handling service appointments or consultations.

---

## ⚙️ Features

- 🎤 **Voice Interaction** – Accepts and processes conversations from phone calls (via Retell AI or Twilio).
- 🧠 **AI Understanding** – Uses OpenAI GPT-4.1-mini to extract customer name, phone number, service type, and requested time from the transcript.
- 📅 **Google Calendar Integration** –  
  - Checks available time slots.  
  - Books or cancels appointments automatically.  
  - Prevents double bookings with conflict detection.
- 🤖 **LangChain Agent** – Acts as the central logic engine to manage context, tools, and decisions.
- 🧭 **Context Awareness** – Uses current time and date to provide natural and human-like responses.
- 🛑 **Validation Rules** – Ensures no booking is made without required details such as name, phone, and service type.

---

## 🧩 Workflow Structure

| Node | Description |
|------|--------------|
| **Webhook** | Receives call transcript and metadata from voice systems. |
| **Switch** | Routes execution flow based on user intent (`check_availability`, `book_appointment`, or `cancel_appointment`). |
| **ISO to Unix** | Converts preferred booking time into Unix timestamps for time range calculations. |
| **AI Agent** | The main decision-making node powered by LangChain and OpenAI. |
| **Google Calendar (Create/Delete)** | Performs appointment creation or cancellation actions. |
| **Respond to Webhook** | Sends final AI-generated responses back to the voice interface. |
| **OpenAI Chat Model** | Provides the language understanding and reasoning capabilities. |

---

## 🚀 How It Works

1. **Voice Call Initiation**  
   A user interacts with the AI agent via a connected voice service like **Twilio** or **Retell AI**.

2. **Webhook Trigger**  
   The call transcript is sent to the n8n workflow via a webhook endpoint.

3. **Intent Recognition**  
   The AI Agent analyzes the conversation to identify the user's intent (e.g., check availability, book, or cancel).

4. **Data Extraction**  
   The system automatically extracts:
   - Customer name  
   - Contact number  
   - Appliance/service type  
   - Issue description  
   - Preferred time

5. **Calendar Interaction**  
   Depending on intent:
   - **Check availability** → Queries Google Calendar for open slots.  
   - **Book appointment** → Creates a new event if time is free.  
   - **Cancel appointment** → Locates and deletes the event.

6. **AI Response**  
   The AI generates a natural conversational reply confirming the action or suggesting alternatives.

---

## 🧠 Example Scenario

**Conversation Example**
