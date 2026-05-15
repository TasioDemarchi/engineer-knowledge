# Topic: Domain-Driven Design (DDD)

## Status
🟡 In Progress — Building Blocks ✅, Bounded Contexts (concept + delimiting + inter-context communication) ⏳, Context Mapping ⏳

## Strengths
- Ubiquitous Language: entendido rápidamente, buen ejemplo propio
- Entity: correcto desde el primer intento, reforzado con pruebas de identidad
- Value Object: confusión inicial pero entendió la prueba decisiva ("¿son intercambiables?")
- Aggregate/Root: entendió como "borde de consistencia" y "guardian" con analogía del carrito
- Domain Event: entendió como "factura que certifica que algo pasó", inmutable, comunicación entre contextos
- Contexto como regla de oro: descubrió SOLO que los Building Blocks dependen del contexto del negocio ANTES de que se explicara Bounded Contexts
- Repository: claro desde el inicio — "el bibliotecario"
- Domain Service: entendió la regresión "lógica sin hogar, no es de ninguna Entity"
- Domain Service naming: aprendió que se nombra por el concepto del negocio (sustantivo), no por la acción ni por los participantes
- Bounded Context delimiting: entendió que el límite lo marca dónde cambia el lenguaje, no dónde cambian los atributos
- Inter-context communication: entendió que compartís solo el ID mínimo, cada contexto tiene su modelo, y se crean cuando se necesitan

## Struggles
- Value Object vs Entity: tendencia a decir que cosas con identificador son Value Objects (GPU con código de barras). Necesita la prueba: "¿son intercambiables?"
- Entity = mutable: se le olvida que las Entities son mutables por definición
- Domain Service: confundió Domain Service con Application Service al principio (común). Clave: Domain Service tiene la regla, Application Service solo orquesta
- Domain Service naming: primero listó Entities (VeterinarioEspecialidadDisponibilidad), luego describió acción (GarantizarVeterinarioEspecializado). Necesita recordar: sustantivo del concepto de negocio
- Bounded Context identification: primero pensó que se identificaban por Entities individuales o por dónde cambian los atributos. Tuvo que llegar a "dónde cambia el lenguaje" con guía
- Data sync between contexts: primer instincto fue sincronizar ambos lados a la vez. Necesitó recordar acoplamiento para llegar a la opción desacoplada

## Session History
| Date | Session | Outcome |
|------|---------|---------|
| 2026-05-01 | DDD: Ubiquitous Language + Building Blocks | Gates 1-2 passed. Gate 3 pending. Bounded Contexts not covered. |
| 2026-05-06 | DDD Building Blocks (refuerzo completo) | Repaso de todos los Building Blocks con nueva profundidad. Descubrió que el contexto del negocio define el rol. Domain Event = Value Object. Domain Service vs Application Service. |
| 2026-05-11 | DDD Bounded Contexts (concepto + delimitación) | Gate 1 passed (veterinaria examples). Bounded Context concept understood. Delimiting by language change understood. Inter-context communication (ID sharing, lazy creation) understood. Domain Service naming reviewed. |

## Next Session Plan
1. Quick repaso: "¿Qué define el límite de un Bounded Context?"
2. **Context Mapping:** patrones de relación (Customer-Supplier, Anti-Corruption Layer, Conformist, Partnership)
3. **Gate 2 (Kata):** E-commerce estilo MercadoLibre — identificar bounded contexts
4. **Gate 3:** Edge cases
5. **Gate 4:** Junior roleplay

## Key Insights from Sessions
- User discovers concepts BEFORE they're formally explained (discovered Bounded Contexts intuitively from the Entity/VO context dependency)
- User needs mechanism explanations (not just "it works that way") — responds well to "what breaks if..." scenarios
- User connects concepts across sessions naturally (coupling → events → context communication)
- First instinct for data sync is "both at the same time" — needs to recall coupling principles to arrive at decoupled approach
- Domain Service naming: needs to remember "concept of business as noun" not "list of entities" or "action verb"

## Related Topics
- [[acoplamiento]] — ✅ studied 2026-05-02, directly connected to inter-context communication (low coupling = share only ID, communicate via events)
- [[microservicios]] — DDD is the prerequisite for defining service boundaries
- [[clean-architecture]] — Domain, Application, Infrastructure layers touched during Domain Service explanation