# User Preferences — Dynamic

> **Purpose:** Tracks how the user prefers to learn, per topic area. Updated automatically by the agent based on observed patterns and validated with the user.
> **Updated by:** Agent (auto) + User (validation at session end).
> **Last Validated:** 2026-05-06

---

## Terminology Gaps

> Technical terms the user has asked about or didn't recognize. Organized by topic area.
> **Rule:** When a term appears here 2+ times, the agent MUST explain it proactively in future sessions on that topic.

### distributed-systems
- eventual-consistency — explained during acoplamiento session, needs reinforcement
- race-condition — user identified independently, good intuition

### cloud-native
- _(e.g., sidecar-pattern, service-mesh, istio)_

### architecture
- acoplamiento (coupling) — ✅ studied 2026-05-02
- aggregate vs aggregate root — ✅ clarified 2026-05-06 (guardian metaphor, border of consistency)
- bounded context — ✅ concept understood 2026-05-11 (language change = context boundary, share only ID, communicate via events)
- context-mapping — session pending (patterns of relationship between contexts)
- domain-service vs application-service — ✅ clarified 2026-05-06 (domain = business rule, app = orchestrator)
- entity-mutable — user forgets Entities are mutable when comparing with VOs (needs occasional reminder)

### java-modern
- _(e.g., records, sealed-classes, pattern-mapping)_

### general
- domain-event — ✅ clarified 2026-05-02 and 2026-05-06 (event = Value Object, like an invoice/receipt, immutable past tense)

---

## Depth Preferences

> How much depth the user needs per topic area. Validated with the user at session end.

| Topic Area | Depth | Rule | Last Validated |
|------------|-------|------|----------------|
| ddd | deep | Explain all technical terms, use concrete examples, relate to microservices context | 2026-05-06 |
| distributed-systems | deep | Explain all technical terms before using them | |
| cloud-native | deep | | |
| architecture | deep | Use "what breaks if..." scenarios to explain trade-offs | 2026-05-02 |
| java-core | medium | Skip basics, focus on new features | |
| java-modern | medium | | |
| sdcl-workflows | medium | | |
| soft-skills | shallow | | |

### Depth Definitions
- **Deep:** Explain all technical terms, provide analogies, show trade-offs, include examples
- **Medium:** Assume basic knowledge, explain only advanced terms, focus on application
- **Shallow:** Skip explanations of fundamentals, go straight to design decisions and trade-offs

---

## Explanation Style Preferences

> How the user prefers to receive information, per context.

| Context | Preferred Style | Notes |
|---------|----------------|-------|
| New architecture concepts | Analogies-first, then technical | User explicitly asked for simpler language on building blocks |
| Code examples | Java-first, minimal boilerplate | Per user profile |
| Trade-off discussions | Table format, pros/cons | Per user profile |
| Design katas | Present scenario, let user design first | |
| Topic ordering | Explicitly relate new topics to previously studied topics | User requested: "relacioná los temas para poder entenderlos mejor" |
| Concept sequencing | Go concept by concept, not all at once | User said: "espera vamos concepto por concepto" |
| Classification questions | Use "la prueba decisiva" format | User responded well to "¿son intercambiables?" test for Entity vs VO |
| Mechanism explanations | Explain WHY things work, not just THAT they work | User needs mechanism behind concepts, not just declarations |
| Design choices | Ask "what breaks if..." to guide toward decoupled solutions | First instinct is synchronous; needs coupling reminders |

---

## Validation Log

> Record of when preferences were validated with the user and what changed.

| Date | Topic Area | What Changed | User Response |
|------|------------|--------------|---------------|
| 2026-05-01 | general | Added: relate topics explicitly, go concept-by-concept, simpler language for building blocks | User explicitly requested both |
| 2026-05-02 | architecture | User struggles with DB-first thinking; needs explicit "domain first, DB last" framing | User acknowledged: "me cuesta dejar de ver todo como CRUD" |
| 2026-05-06 | ddd | User discovers concepts intuitively before formal explanation — leverage this for Bounded Contexts | User said: "entiendo que todo va dependiendo en qué contexto del negocio se esté hablando" before it was explained |

---

## Active Session Notes

### Terms user asked about this session
- Bounded Context delimiting (how to identify boundaries) — resolved: language change, not Entities or attributes
- Inter-context data synchronization — resolved: share only ID, create when needed, communicate via events

### Depth adjustments noticed
- User connects coupling principles from previous sessions to new concepts (Context Mapping)
- Needs explicit "what breaks if X is down?" question to choose decoupled over synchronous

### Style observations
- "What breaks if..." prompts work very well for guiding toward decoupled design choices
- User naturally connects concepts across sessions (coupling → events → context communication)