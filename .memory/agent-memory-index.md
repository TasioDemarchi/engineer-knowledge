# Agent Memory — Index

> **Purpose:** Lightweight overview of user progress. Read at EVERY session start.
> **Size target:** Keep under 100 lines. Archive old sessions to keep it small.

---

## User Profile

- **Preferred language for examples:** Java
- **Current level:** Intermediate Java, Beginner in distributed systems and architecture patterns
- **Learning style:** Concept-by-concept, explicit relationships between topics, analogies-first, simple language
- **Notes:** Self-identified "mentalidad de informática antigua" — needs explicit contrast between old mental models and new ones. Asks questions before advancing.

---

## Topics Covered

| Topic | Category | Date | Gates Passed | Iterations | Notes |
|-------|----------|------|-------------|------------|-------|
| DDD (Domain-Driven Design) | Architecture | 2026-05-01 | Gate 1 (partial), Gate 2 | 1 | Ubiquitous Language ✅, Building Blocks ✅, Bounded Contexts ⏳ pending next session |
| Acoplamiento (Coupling) | Architecture | 2026-05-02 | Gates 1-4 | 1 | Understood via DDD events, race conditions, async trade-offs. |
| Domain Events (Review) | Architecture | 2026-05-02 | N/A (Clarification) | 1 | Cleared confusion: events are messages, not aggregates or state. |

---

## Recurring Struggles

| Pattern | Topic | First Noticed | Status |
|---------|-------|---------------|--------|
| Confuses Entity with everything (old mental model) | DDD | 2026-05-01 | Improving — understood VO after correction |
| Needs concrete examples before abstract concepts | All | 2026-05-01 | Active |
| Thinks in DB tables first | Architecture | 2026-05-02 | Active — improving with DDD framing |

---

## Recent Sessions (last 5)

| Date | Topic | Outcome | Next Steps |
|------|-------|---------|------------|
| 2026-05-02 | Acoplamiento + DDD Events review | Gates 1-4 passed. Vault note created. | Start Bounded Contexts next session |
| 2026-05-01 | DDD (Ubiquitous Language + Building Blocks) | Gates 1-2 passed. Bounded Contexts not started. | Start next session with Bounded Contexts + Context Mapping |

---

## Pending "To Study" Items

> Items captured from `00-To-Study/` that still need a full learning session.

| Concept | Source | Date Captured | Priority | Status |
|---------|--------|---------------|----------|--------|
| Acoplamiento (Coupling) | User request during DDD | 2026-05-01 | High | ✅ Completed 2026-05-02 |
| Bounded Contexts + Context Mapping | Microservicios roadmap | 2026-05-01 | High | In progress (next session) |
| Descentralización de Datos | Microservicios Fase 1 | 2026-05-01 | High | Pending |
| Service Discovery + Comunicación | Microservicios Fase 2 | 2026-05-01 | High | Pending |
| API Gateway + BFF | Microservicios Fase 3 | 2026-05-01 | Medium | Pending |
| Transacciones Distribuidas (Sagas + CQRS) | Microservicios Fase 4 | 2026-05-01 | High | Pending |
| Resiliencia | Microservicios Fase 5 | 2026-05-01 | High | Pending |
| Observabilidad | Microservicios Fase 6 | 2026-05-01 | Medium | Pending |
| Deployment + Operación | Microservicios Fase 7 | 2026-05-01 | Medium | Pending |
