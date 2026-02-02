# Twilio Forwarding Webhook (Internal)

Mission Learning Statement
- Mission: Deliver a production-ready SMS forwarding + response orchestration webhook with persistent memory.
- Learning focus: webhook design, rate limiting, Firestore state, and concise response orchestration.
- Project start date: 2024-12-01 (given by user)

Inbound SMS webhook that enriches conversations with memory and generates concise responses.

## Features

- Twilio inbound SMS ingestion
- Firestore-backed conversation memory
- OpenAI Responses API orchestration
- Designed for Google Cloud Functions deployment

## Installation

### Requirements

- Python 3.8+
- Twilio credentials
- Firebase service account

## Quick Start

```bash
python main.py
```

## Usage

Environment variables via `env.txt`:

```
OPENAI_API_KEY=...
TWILIO_ACCOUNT_SID=...
TWILIO_AUTH_TOKEN=...
TWILIO_PHONE_NUMBER=...
```

Place Firebase service account at `cred.txt` (local-only, never commit).

## Architecture

```
Inbound SMS (Twilio)
    |
    v
Webhook Handler (main.py)
    |
    +--> Firestore (conversation memory)
    |
    +--> Response Orchestrator
             |
             v
        OpenAI Responses API
             |
             v
          SMS Reply
```

## Project Structure

```
main.py      # Webhook entry point
cred.txt     # Firebase service account (local-only)
```

## Building

No build step required. Run directly with Python.

## Contributing

Internal tool; changes should preserve privacy and credential handling.

## License

No license file is included in this repository.
