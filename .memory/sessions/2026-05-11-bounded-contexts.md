# Session: 2026-05-11 — DDD Bounded Contexts (concepto + delimitación)

## Goal
- Gate 1 repaso: Building Blocks en contexto de veterinaria
- Introducir Bounded Contexts formalmente
- Cómo se delimitan los contextos
- Cómo se comunican entre contextos (IDs, eventos)

## Gates Passed
- **Gate 1 (Building Blocks review):** ✅ All 6 blocks correct in veterinary context. Domain Service naming needed guidance (went from listing entities → verbs → noun concept: AsignacionCompetente)

## Concepts Covered
- **Bounded Context definition:** límite explícito donde un modelo tiene un único significado consistente. Donde cambia el lenguaje, cambia el contexto.
- **Bounded Context delimiting:** no por Entities individuales, no por atributos, sino por **cambio de lenguaje** (Ubiquitous Language). Mismo concepto, diferente significado = diferente contexto.
- **Inter-context communication:** share only ID minimum, each context has its own model, create when needed (lazy), communicate via Domain Events.
- **Decoupled vs Synchronous:** User's first instinct was sync both sides, needed to recall coupling principles to arrive at decoupled approach.

## Discoveries
- User first tried to identify contexts by "entities that become Value Objects" — close but not the full picture
- User first tried "entities/objects that don't share attributes" — still data-thinking
- Needed guiding questions to arrive at "language change" as the delimiter
- First instinct for data sync was "create in both at the same time" — needs coupling reminder to choose decoupled approach
- Domain Service naming: user listed entities first, then verbs, needed guidance to arrive at business concept noun

## Preferences Updated
- First instinct for inter-service communication is synchronous — needs explicit "what breaks if X is down?" reminder
- Still connects concepts across sessions (coupling → events → context communication) — very strong

## Next Steps
- Context Mapping: patterns of relationship (Customer-Supplier, Anti-Corruption Layer, Conformist, Partnership)
- Gate 2 (Kata): E-commerce estilo MercadoLibre — identify bounded contexts
- Gate 3: Edge cases
- Gate 4: Junior roleplay
- Update vault note with Bounded Context content

## Relevant Files
- `10-Engineering-Fundamentals/domain-driven-design.md` — Needs Bounded Contexts section added
- `.memory/topics/domain-driven-design.md` — Updated with session progress
- `.memory/agent-memory-index.md` — Updated with new session