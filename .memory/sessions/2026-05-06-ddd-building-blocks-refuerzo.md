# Session: 2026-05-06 — DDD Building Blocks (Refuerzo completo)

## Goal
- Repasar y profundizar todos los Building Blocks de DDD
- Conectar Entity/VO con Aggregate, Domain Event, Repository, Domain Service
- Aclarar dudas sobre Domain Event (no es Entity, es Value Object)

## Gates Passed
- Sin gates formales (sesión de refuerzo/depth)
- User descubrió intuitivamente que el contexto del negocio define el rol de cada Building Block (esto es Bounded Contexts sin explicarlo formalmente)
- User entendió Domain Event = Value Object (inmutable, pasado, como una factura)
- User entendió Domain Service vs Application Service (regla de negocio vs orquestador)

## Discoveries
- User PIENSA en DB tables primero, pero cuando se le plantea el contexto del negocio, autocorrige bien
- User descubrió Bounded Contexts ANTES de que se explicaran: "entendí que todo va dependiendo en qué contexto del negocio se esté hablando"
- User confunde Domain Service con Application Service en primera instancia (común en devs Java/Spring)
- Se necesita reforzar: Entity = mutable (se le olvida en Value Object vs Entity comparaciones)
- Domain Event entendido con analogía de factura: certifica que algo pasó, otros la usan para reaccionar

## Preferences Updated
- User responds well to "la prueba decisiva" format for classification questions ("¿son intercambiables?")
- User connects concepts across sessions (coupling → events → context communication)
- User discovered Bounded Contexts intuitively — next session should leverage this insight

## Next Steps
- Start Bounded Contexts + Context Mapping formally (user already has intuition for it)
- Review all Building Blocks with Gate 1 before starting
- Connect Bounded Contexts to microservices architecture (why Microservice boundary ≈ Bounded Context boundary)
- Update vault note was done during session

## Relevant Files
- `10-Engineering-Fundamentals/domain-driven-design.md` — Updated with full Building Blocks categorization, user's own words, context-dependent examples
- `.memory/agent-memory-index.md` — To be updated
- `.memory/user-preferences.md` — To be updated
- `.memory/topics/domain-driven-design.md` — Updated with session progress