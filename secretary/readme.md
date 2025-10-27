# 👩‍⚕️ Workflow: AI Secretary (Healthcare)

This workflow simulates an AI-powered secretary for medical clinics, capable of interacting with patients via WhatsApp to schedule, confirm, or cancel appointments. The flow is designed to understand both text and audio inputs.

![Workflow Preview](./flow-preview.png)

---

### Objective

To automate primary patient communication, freeing up human staff for more complex tasks. The goal is to provide instant responses, check the professional's schedule, and autonomously book appointments 24/7.

---

### How It Works

1.  **Trigger (Webhook):** The flow starts when a new message (text or audio) is received on WhatsApp, captured by a Webhook (e.g., Evolution API).
2.  **Transcription (STT):** If the message is audio, it's sent to a *Speech-to-Text* service (e.g., Elevenlabs) to be converted to text.
3.  **AI Agent (Intent):** The text (original or transcribed) is sent to an AI Agent (LLM) to identify the patient's intent (e.g., "schedule," "cancel," "question") and extract entities (e.g., "doctor," "desired date").
4.  **Scheduling Logic:**
    * If the intent is "schedule," the flow queries the doctor's schedule (e.g., Google Calendar) to check for free slots.
    * The AI Agent formulates a response, suggesting times or asking for more details.
5.  **Confirmation:** Once the patient confirms a time, the flow creates the event in Google Calendar and sends a final confirmation.
6.  **Audio Generation (TTS):** The AI's text response is sent to a *Text-to-Speech* service (e.g., OpenAI TTS) to create an audio response.
7.  **Response (WhatsApp):** The workflow sends both the text message and the audio file back to the patient via WhatsApp.

---

### Key Components

* **Webhook (Evolution API):** Receives audio and text messages.
* **Speech-to-Text (Elevenlabs):** Transcribes audio into text.
* **AI Agent (LLM):** Processes natural language, understands intent, and formulates replies.
* **Google Calendar Node:** Checks and creates calendar events.
* **Text-to-Speech (TTS):** Converts the AI's text response into audio.

---

### How to Test

1.  Import the `secretary.json` file into n8n and configure the credentials (AI, Google, WhatsApp APIs).
2.  Send an audio message to the connected WhatsApp number saying, "Hi, I'd like to book an appointment with Dr. Smith for next week."
3.  Verify that the flow responds with available time slots, in both text and audio formats.
