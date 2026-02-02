# Twilio Forwarding Webhook (Internal)

Mission Learning Statement
- Mission: Deliver a production-ready SMS forwarding + response orchestration webhook with persistent memory.
- Learning focus: webhook design, rate limiting, Firestore state, and concise response orchestration.
- Project start date: 2024-12-01 (given by user)

## Overview
This service receives inbound SMS, enriches with conversation memory, and generates concise responses.
It uses Twilio for SMS, Firestore for persistence, and
the OpenAI Responses API for text generation.

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

## Quickstart
```bash
python main.py
```

## Environment
Use an `env.txt` file in the same directory:
```
OPENAI_API_KEY=...
TWILIO_ACCOUNT_SID=...
TWILIO_AUTH_TOKEN=...
TWILIO_PHONE_NUMBER=...
```

## Firebase
Place your Firebase service account key at `cred.txt` (local-only, never commit).

## Deployment
Designed for Google Cloud Functions via `functions_framework`.

