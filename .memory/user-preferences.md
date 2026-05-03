# User Preferences — Dynamic

> **Purpose:** Tracks how the user prefers to learn, per topic area. Updated automatically by the agent based on observed patterns and validated with the user.
> **Updated by:** Agent (auto) + User (validation at session end).
> **Last Validated:** 2026-05-02

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
- aggregate vs aggregate root — confusion initial, clarified in session
- bounded context — session pending, not yet studied

### java-modern
- _(e.g., records, sealed-classes, pattern-mapping)_

### general
- domain-event — confusion with aggregate/state, clarified 2026-05-02

---

## Depth Preferences

> How much depth the user needs per topic area. Validated with the user at session end.

| Topic Area | Depth | Rule | Last Validated |
|------------|-------|------|----------------|
| ddd | deep | Explain all technical terms, use concrete examples, relate to microservices context | 2026-05-01 |
| distributed-systems | deep | Explain all technical terms before using them | |
| cloud-native | deep | | |
| architecture | deep | | 2026-05-02 |
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

---

## Validation Log

> Record of when preferences were validated with the user and what changed.

| Date | Topic Area | What Changed | User Response |
|------|------------|--------------|---------------|
| 2026-05-01 | general | Added: relate topics explicitly, go concept-by-concept, simpler language for building blocks | User explicitly requested both |
| 2026-05-02 | architecture | User struggles with DB-first thinking; needs explicit "domain first, DB last" framing | User acknowledged: "me cuesta dejar de ver todo como CRUD" |

---

## Active Session Notes

### Terms user asked about this session
- domain-event vs aggregate — clarified: event is a message/receipt, not state or entity
- acoplamiento — understood via DDD events, race conditions, async trade-offs

### Depth adjustments noticed
- User identified race condition independently — good architectural intuition
- User needed clarification on "event bus" vs "polling a list"

### Style observations
- User responds well to concrete "what breaks if..." scenarios
- User self-corrects well when given the mechanism behind the concept
