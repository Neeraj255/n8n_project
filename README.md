# n8n_project

<img width="1649" height="773" alt="Screenshot 2025-10-05 223355" src="https://github.com/user-attachments/assets/2582989d-419e-46a8-a88b-5914a353c98a" />

🌾 AI WhatsApp Assistant for Farmers (Built with n8n)
📖 Overview

This project is an AI-powered WhatsApp assistant built using n8n, designed to help users (e.g., farmers) interact naturally via text, images, or voice messages.
The workflow integrates AI for message understanding, image analysis, and scheduling, providing smart responses and actions through WhatsApp.

⚙️ Features

WhatsApp Integration
Handles text, image, and voice messages using a WhatsApp trigger.

Voice Transcription
Converts audio messages into text using the Google Gemini Transcribe node.

Image Analysis
Identifies crops or detects diseases from images using AI (Gemini Vision).

AI Chat Agent
A custom AI agent powered by Google Gemini Chat Model with MongoDB memory for contextual replies.

Google Workspace Integration

Fetches or creates events in Google Calendar.

Reads or writes data in Google Sheets.

🧠 Workflow Structure
WhatsApp Trigger
   └── Switch (audio / text / image)
         ├── Audio → Get Audio → HTTP Request → Transcribe → Edit Fields
         ├── Image → Get Image URL → HTTP Request → Analyze Image → Edit Fields
         └── Text  → Edit Fields
               ↓
            AI Agent (Gemini + MongoDB)
               ↓
             If → Send WhatsApp Message

🗂️ Nodes Used
Category	Node	Purpose
Messaging	WhatsApp Trigger	Receives user messages
Control Flow	Switch	Routes message types
HTTP	HTTP Request	Retrieves media URLs
AI	Transcribe a Recording	Converts audio to text
AI	Analyze Image	Processes image content
AI	AI Agent	Handles chat logic
Database	MongoDB Chat Memory	Stores conversation history
Productivity	Google Calendar / Sheets	Creates or fetches events
Output	Send Message	Sends AI response to WhatsApp
🚀 How to Use

Export Workflow:
Import the .json workflow file into your n8n instance (Settings → Import from file).

Configure Credentials:
Set up the following credentials in n8n:

WhatsApp API

Google Gemini API Key

MongoDB Connection

Google Calendar & Sheets OAuth

Test the Workflow:
Click Execute Workflow or send a message to your WhatsApp bot.

Deploy:

Optionally deploy n8n on Docker or a VPS.

Use n8n webhook URLs for WhatsApp callbacks.

🧩 Folder Structure Example
my-n8n-farmer-bot/
 ├── workflows/
 │   └── farmer-assistant.json
 ├── README.md
 ├── .gitignore
 ├── .env.example

🧾 Example .gitignore
.env
.n8n/
*.db
node_modules/

🏗️ Tech Stack

n8n (Automation & Orchestration)

Google Gemini AI

MongoDB

Google Calendar & Sheets APIs

WhatsApp Cloud API

💡 Future Enhancements

Add support for multiple languages (Malayalam, English)

Auto-summaries of chat sessions

Weather or soil data integration for farmers

👨‍💻 Author

Developed by Neeraj G — AI automation enthusiast & n8n workflow builder.
