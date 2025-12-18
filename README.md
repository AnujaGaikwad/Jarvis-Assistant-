JARVIS – AI Desktop Voice Assistant

JARVIS is a cyclic, event-driven AI desktop assistant built using Python.
It operates on a continuous listen → process → respond loop and intelligently combines rule-based automation with Gemini AI for natural language understanding and smart responses.

This project demonstrates AI integration, system design, speech processing, and modular architecture.

🔁 System Overview

JARVIS continuously listens for a wake word, processes commands, and responds using voice output.

Listen → Understand → Decide → Act → Speak


Its core strength lies in:

Clear decision routing

Reliable voice input/output

Seamless Gemini AI fallback for complex queries

🎯 Core Event Triggers
Trigger	Action	Library
Wake Word: “Jarvis”	Activates command listening	speech_recognition
Voice Command	Routed to logic handler	processCommand()
🧠 Decision Logic (processCommand())

The processCommand() function acts as the central controller of the system.

🔹 Priority 1: Predefined Commands

Hard-coded utility commands are checked first:

Open websites (Google, YouTube, etc.)

Play music

Fetch news

Perform system tasks

➡ If matched, the corresponding function is executed immediately.

🔹 Priority 2: AI Fallback (Gemini)

If no predefined rule matches:

The command is forwarded to Gemini AI

AI generates an intelligent, natural-language response

This ensures JARVIS never stays silent, even for unexpected queries.

🧠 AI Brain – Gemini Integration

Function: aiProcess(command)

Model Used: gemini-2.5-flash

Purpose:

General knowledge queries

Logical reasoning

Definitions & explanations

Creative text responses

Gemini acts as the brain whenever automation logic ends.

🎙️ Input & Output Pipeline
🔊 Voice Input Flow
User Voice
   ↓
Microphone
   ↓
speech_recognition
   ↓
Text Command

🔈 Voice Output Flow
Response Text
   ↓
gTTS (Primary)
   ↓
MP3 Audio
   ↓
pygame
   ↓
Speech Output


🟡 Fallback:
If gTTS fails, JARVIS automatically switches to offline pyttsx3.
