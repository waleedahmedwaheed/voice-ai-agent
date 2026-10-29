# Voice AI Agent

Realtime voice AI agent starter for speech-to-speech assistants and phone-style conversations.

Useful for support bots, coaching assistants, booking agents, and other low-latency voice use cases.

## What you get

- Speech-to-text → LLM reasoning → text-to-speech loop
- Session state for multi-turn conversations
- Pluggable STT / TTS providers
- Hooks for tool calls during a live call (calendar, CRM, FAQ)

## Project layout

```text
src/
  stt/           # speech-to-text adapters
  tts/           # text-to-speech adapters
  agent.py       # conversation + tool loop
  session.py     # turn memory / call state
requirements.txt
```

## Quick start

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
# set OPENAI_API_KEY and optional STT/TTS keys

python -m src.agent
```

## Conversation loop

1. Capture / receive audio  
2. Transcribe user speech  
3. Run agent + optional tools  
4. Synthesize reply audio  
5. Keep short-term session context  

## Extensions

- [ ] WebRTC / websocket transport
- [ ] Interruption / barge-in handling
- [ ] Telephony provider integration
- [ ] Post-call summaries and CRM sync

## License

MIT
