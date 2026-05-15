# Agent Memory — Index

> **Purpose:** Lightweight overview of user progress. Read at EVERY session start.
> **Size target:** Keep under 100 lines. Archive old sessions to keep it small.

---

## User Profile

- **Preferred language for examples:** Java
- **Current level:** Intermediate Java, Beginner in distributed systems and architecture patterns
- **Learning style:** Concept-by-concept, explicit relationships between topics, analogies-first, simple language
- **Notes:** Self-identified "mentalidad de informática antigua" — needs explicit contrast between old mental models and new ones. Asks questions before advancing. Discovers concepts intuitively before formal explanation.

---

## Topics Covered

| Topic | Category | Date | Gates Passed | Iterations | Notes |
|-------|----------|------|-------------|------------|-------|
| DDD (Domain-Driven Design) | Architecture | 2026-05-01 | Gate 1 (partial), Gate 2 | 1 | Ubiquitous Language ✅, Building Blocks ✅, Bounded Contexts ⏳ |
| Acoplamiento (Coupling) | Architecture | 2026-05-02 | Gates 1-4 | 1 | Understood via DDD events, race conditions, async trade-offs. |
| Domain Events (Review) | Architecture | 2026-05-02 | N/A (Clarification) | 1 | Cleared confusion: events are messages, not aggregates or state. |
| DDD Building Blocks (Refuerzo) | Architecture | 2026-05-06 | No formal gate | 1 | Deep review of all 5 categories. Discovered context-dependency intuitively. |
| DDD Bounded Contexts | Architecture | 2026-05-11 | Gate 1 ✅ | 1 | Concept ✅, Delimiting by language ✅, Inter-context communication ✅. Context Mapping pending. |

---

## Recurring Struggles

| Pattern | Topic | First Noticed | Status |
|---------|-------|---------------|--------|
| Confuses Entity with everything (old mental model) | DDD | 2026-05-01 | Improving — understood VO and Aggregate with analogies |
| Needs concrete examples before abstract concepts | All | 2026-05-01 | Active |
| Thinks in DB tables first | Architecture | 2026-05-02 | Active — improving with DDD framing |
| Forgets Entity = mutable when comparing with VO | DDD | 2026-05-06 | Needs occasional reminder |
| First instinct is synchronous/data sync | Architecture | 2026-05-11 | Needs to recall coupling principles to arrive at decoupled approach |
| Domain Service naming (lists entities/verbs, not concepts) | DDD | 2026-05-11 | Needs reinforcement — noun of business concept |

---

## Recent Sessions (last 5)

| Date | Topic | Outcome | Next Steps |
|------|-------|---------|------------|
| 2026-05-11 | DDD Bounded Contexts (concepto + delimitación) | Gate 1 ✅. Bounded Context concept ✅. Delimiting by language ✅. Inter-context communication ✅ | Context Mapping + Kata (MercadoLibre) next session |
| 2026-05-06 | DDD Building Blocks (refuerzo) | All 5 categories understood. Domain Event=VO, Domain Service vs App Service. Context rule discovered intuitively. | Start Bounded Contexts + Context Mapping next session |
| 2026-05-02 | Acoplamiento + DDD Events review | Gates 1-4 passed. Vault note created. | Start Bounded Contexts next session |
| 2026-05-01 | DDD (Ubiquitous Language + Building Blocks) | Gates 1-2 passed. Bounded Contexts not started. | Start next session with Bounded Contexts + Context Mapping |

---

## Pending "To Study" Items

> Items captured from `00-To-Study/` that still need a full learning session.

| Concept | Source | Date Captured | Priority | Status |
|---------|--------|---------------|----------|--------|
| Acoplamiento (Coupling) | User request during DDD | 2026-05-01 | High | ✅ Completed 2026-05-02 |
| Bounded Contexts + Context Mapping | Microservicios roadmap | 2026-05-01 | High | 🔵 In progress — concept ✅, Context Mapping pending |
| Descentralización de Datos | Microservicios Fase 1 | 2026-05-01 | High | Pending |
| Service Discovery + Comunicación | Microservicios Fase 2 | 2026-05-01 | High | Pending |
| API Gateway + BFF | Microservicios Fase 3 | 2026-05-01 | Medium | Pending |
| Transacciones Distribuidas (Sagas + CQRS) | Microservicios Fase 4 | 2026-05-01 | High | Pending |
| Resiliencia | Microservicios Fase 5 | 2026-05-01 | High | Pending |
| Observabilidad | Microservicios Fase 6 | 2026-05-01 | Medium | Pending |
| Deployment + Operación | Microservicios Fase 7 | 2026-05-01 | Medium | Pending |