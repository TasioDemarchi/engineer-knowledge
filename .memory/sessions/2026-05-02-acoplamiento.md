# Session: 2026-05-02 — Acoplamiento + DDD Events Review

## Goal
- Clarify Domain Events confusion (event vs aggregate vs state)
- Study Acoplamiento (Coupling) as requested by user
- Connect DDD events to low coupling patterns

## Gates Passed
- **Gate 1 (Acoplamiento):** ✅ User defined coupling correctly as dependency percentage
- **Gate 2 (Design Kata):** ✅ Redesigned turno system with events, identified async bottleneck
- **Gate 3 (Edge Cases):** ✅ Identified race condition (double booking) independently
- **Gate 4 (Junior Roleplay):** ✅ Explained benefits of event-driven decoupling clearly

## Discoveries
- User still thinks in DB tables first, but improving with DDD framing
- User has good intuition for race conditions and failure scenarios
- User needs explicit mechanism explanation (not just "it works asynchronously")

## Preferences Updated
- Added "domain first, DB last" framing requirement
- Noted user responds well to "what breaks if..." scenarios

## Next Steps
- Start Bounded Contexts + Context Mapping to complete DDD
- Connect Bounded Contexts to microservices architecture

## Relevant Files
- `10-Engineering-Fundamentals/architecture/acoplamiento.md` — Created vault note
- `.memory/agent-memory-index.md` — Updated progress
- `.memory/user-preferences.md` — Updated terminology gaps and style notes
