# 🌤️ AI Morning Weather Assistant

An automated morning weather assistant built with **n8n**, **OpenWeather**, and the **WhatsApp Cloud API**.

Every morning, the workflow checks the weather forecast for Riga, filters the information that is relevant for the day, and sends a short WhatsApp briefing.

The project is designed as a first step toward building practical **agentic AI tools** that can gather information, interpret it, and take action.

## 🚀 What it does

Every day at **07:00**, the workflow:

1. Retrieves the weather forecast for Riga.
2. Analyzes temperature, rain, and wind conditions.
3. Focuses on useful weather information between **09:00 and 20:00**.
4. Builds a concise morning summary.
5. Sends the summary automatically through WhatsApp.

## 🧠 Project goal

The goal is not simply to build a weather notification. This project explores an intelligent workflow that:

- retrieves external data
- interprets changing conditions
- applies decision logic
- produces a useful summary
- takes action through an external service

The current version is primarily a reliable automation. The next iteration will evolve toward a more agentic architecture with an AI Agent, tool selection, context, and memory.

## 🏗️ Architecture

```text
Schedule Trigger
      ↓
OpenWeather API
      ↓
Weather Processing
      ↓
Morning Summary
      ↓
WhatsApp Cloud API
      ↓
User
```

## 🛠️ Technologies

- n8n
- OpenWeather API
- WhatsApp Cloud API
- Meta Developer Platform
- JavaScript
- REST APIs
- JSON
- Workflow automation

## ⚙️ Weather logic

The briefing focuses on rain between **09:00 and 20:00 Riga local time**.

- Rain before 09:00 is ignored.
- Separate rain periods are kept separate.
- A maximum rain probability is not presented as if it applied continuously across a long time range.
- Umbrella recommendations are based only on meaningful rain risk during the relevant part of the day.

## 🔐 Credentials

Real credentials are not stored in this repository.

See `.env.example` for the names of the required values. In n8n, credentials should remain in the n8n Credentials store and should never be committed to GitHub.

## 📥 Importing the workflow

Once `workflow/workflow.json` is added:

1. Open n8n.
2. Create a new workflow.
3. Import `workflow/workflow.json`.
4. Configure your own OpenWeather credentials.
5. Configure your own WhatsApp Cloud credentials.
6. Update the recipient phone number.
7. Test the workflow.
8. Activate it.

## 🔮 Planned improvements

- AI Agent node instead of deterministic summary logic
- Google Calendar integration
- personalized recommendations based on daily plans
- memory and user preferences
- natural-language WhatsApp interaction
- commute recommendations
- clothing suggestions
- extreme-weather alerts
- multi-user support

## 🎯 Agentic AI roadmap

The next version will move toward:

```text
                 ┌── Weather Tool
                 │
Schedule → AI Agent ── Calendar Tool
                 │
                 ├── User Preferences
                 │
                 └── Other Tools
                         ↓
                  Personalized Briefing
                         ↓
                     WhatsApp
```

## 👤 Author

**Alic Merlivat**

GitHub: https://github.com/Alic-Merlivat

## 📄 License

This project is for educational and portfolio purposes.
