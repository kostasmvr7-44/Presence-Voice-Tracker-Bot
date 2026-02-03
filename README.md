Discord Presence & Voice Analytics Bot
A professional Discord bot for presence tracking, voice activity analytics, and audit-ready reporting, designed with privacy, transparency, and compliance in mind.

✨ Features

Presence tracking (online / idle / dnd / offline)
Voice channel analytics (join / leave / move)
Session duration calculation
Participant counts per voice session
HTML report generation (admin-only)
Explicit user consent logging
Automatic data retention cleanup
CSV-based, audit-friendly storage

🧱 Architecture Overview

| Component | Description                          |
| --------- | ------------------------------------ |
| Runtime   | Event-driven (Discord Gateway)       |                                                                                    
| Language  | Python 3.10+                         |
| Framework | discord.py                           |
| Storage   | Local CSV files                      |
| Reporting | Server-side HTML generation          |
| Timezone  | Europe/Athens                        |
| State     | In-memory sessions + persistent logs |

📁 Data Storage

All data is stored locally in CSV format for maximum transparency and portability.

| File                    | Description                      |
| ----------------------- | -------------------------------- |
| `presence_events.csv`   | Presence status changes          |
| `presence_sessions.csv` | Presence sessions with durations |
| `voice_events.csv`      | Voice join / leave / move events |
| `voice_sessions.csv`    | Voice session analytics          |
| `consents.csv`          | Consent audit trail              |

🔐 Slash Commands

| Command                | Description                         | Permission |
| ---------------------- | ----------------------------------- | ---------- |
| `/presence_report`     | Generate HTML presence report       | Admin      |
| `/voice_report`        | Generate HTML voice activity report | Admin      |
| `/export_presence_csv` | Export CSV data                     | Admin      |
| `/consent accept`      | Register consent                    | User       |                                                             
| `/consent revoke`      | Revoke consent                      | User       |


⚙️ Configuration
Edit the following variables before running the bot:
TOKEN = "YOUR_DISCORD_BOT_TOKEN"
ADMIN_ROLE_NAME = "Presence-Admin"
RETENTION_DAYS = 90
DAILY_REPORT_HOUR_UTC = 7

🚀 Installation & Run
Requirements
Python 3.10+
Discord bot with Presence and Voice State intents enabled


Install dependencies
pip install -U discord.py

🔑 Permissions Required
View Channels
Read Message History
View Guild Members
Presence Intent (enabled in Discord Developer Portal)
Voice State Intent
Admin access is granted if the user:
Has Manage Server permission, or
Has the role defined in ADMIN_ROLE_NAME

🛡 Privacy & Compliance

| Aspect                | Status          |
| --------------------- | --------------- |
| Message content       | ❌ Not collected |
| Voice audio           | ❌ Not recorded  |
| Metadata only         | ✅ Yes           |
| Explicit consent      | ✅ Logged        |
| Retention enforcement | ✅ Automatic     |

The bot stores metadata only and provides an auditable consent trail, making it suitable for community, eSports, or organizational servers.

🧹 Data Retention

Configurable retention window (RETENTION_DAYS)
Old sessions are automatically deleted
Cleanup runs on a scheduled background task


📌 Use Cases
Community activity analytics
eSports team participation tracking
Moderation transparency
Time-based presence reporting
Internal Discord usage audits

📜 License

This project is provided as-is.
You are responsible for ensuring compliance with:
Discord Terms of Service
Local privacy and data-protection regulations

