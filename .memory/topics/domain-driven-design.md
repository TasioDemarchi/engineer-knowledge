# Topic: Domain-Driven Design (DDD)

## Status
🟡 In Progress — Building Blocks ✅, Bounded Contexts ⏳

## Strengths
- Ubiquitous Language: entendido rápidamente, buen ejemplo propio
- Entity: correcto desde el primer intento
- Domain Service: entendido como último recurso

## Struggles
- Value Object: confusión inicial (pensó que Libro era VO). Necesita la "prueba rápida": ¿son intercambiables si tienen los mismos datos?
- Aggregate vs Aggregate Root: confusión inicial sobre si el Root es solo un "contenedor". Se aclaró con analogía de casa/puerta.
- Mental model: "todo es una Entity" — viene de mentalidad de bases de datos tradicionales

## Session History
| Date | Session | Outcome |
|------|---------|---------|
| 2026-05-01 | DDD: Ubiquitous Language + Building Blocks | Gates 1-2 passed. Gate 3 pending. Bounded Contexts not covered. |

## Next Session Plan
1. Repasar brevemente: "¿Qué es un Value Object? Dame un ejemplo nuevo"
2. Bounded Contexts: concepto + ejemplo veterinaria
3. Context Mapping: patrones de relación
4. Gate 3: E-commerce (MercadoLibre) — identificar bounded contexts

## Related Topics
- [[acoplamiento]] — pending, depends on DDD completion
- [[microservicios]] — DDD is the prerequisite for defining service boundaries
