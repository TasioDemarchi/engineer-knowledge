# Principios de Desarrollo de Software

Principios recopilados de práctica real. No son teoría de libro — surgieron de errores concretos, tokens quemados, y bugs que un agente de IA dejó en producción.

Cada principio explica QUÉ es, PARA QUÉ sirve, y CUÁNDO aplica. No dice "cómo integrarlo a tu workflow" — eso depende de tu herramienta.

---

## 1. Caveman Structure (Estructura Primitiva)

**Qué es**: Si un plan puede ser 10 líneas, debe ser 10 líneas. Lo mínimo indispensable para comunicar la intención, ni una palabra más.

**Para qué sirve**: Ahorrar tokens y tiempo. Los artifacts intermedios (plan.md, design.md) son medios, no fines. Si el plan es más largo que el código que vas a escribir, algo está mal.

**Cuándo aplica**: Al escribir cualquier documento intermedio — prompts, planes, specs, reportes. Si podés decirlo en 3 bullets, no escribas 3 párrafos.

**Se viola cuando**: Agregas contexto "por si acaso", repetís la misma información en 3 secciones diferentes, o escribís un plan de 200 líneas para un fix de 1 archivo.

---

## 2. Inversion of Control (Inversión de Control)

**Qué es**: El HUMANO planifica, el AGENTE ejecuta. El agente propone, cuestiona, desafía — pero el humano decide.

**Para qué sirve**: Evitar que el agente se auto-delegue autoridad que no tiene. Sin esto, el agente implementa sin aprobación, introduce features que no se pidieron, o cambia el scope por su cuenta.

**Cuándo aplica**: SIEMPRE. Ninguna implementación sin aprobación explícita del usuario. El agente puede proponer, pero jamás ejecutar sin permiso.

**Se viola cuando**: El agente implementa algo "porque parecía una buena idea" o "mientras estaba ahí, arreglé esto también".

---

## 3. Chesterton's Fence (La Cerca de Chesterton)

**Qué es**: Antes de cambiar algo, entendé POR QUÉ existe. Si no podés explicar por qué está ahí, no podés cambiarlo de forma segura.

**Para qué sirve**: Prevenir refactors destructivos. Mucho código "feo" existe por una razón — un edge case, un bug que ya se fixó, una decisión de negocio. Borrarlo sin entender el contexto introduce bugs.

**Cuándo aplica**: Ante cualquier refactor o "mejora". Si alguien dice "refactorizá X", tu primera pregunta es "¿por qué existe X?". Si la respuesta es "no sé", no lo tocás.

**Se viola cuando**: El agente "mejora" código que no necesitaba mejora, o reescribe algo que funcionaba sin entender el contexto original.

---

## 4. Impact Checklist (Lista de Impacto)

**Qué es**: Definí "listo" ANTES de empezar. ¿Qué significa que este cambio está completo? ¿Qué NO debería cambiar como resultado?

**Para qué sirve**: Prevenir scope creep. Si no sabés cuándo terminás, nunca terminás. El Impact Checklist es tu línea de meta — cada item es un chequeo objetivo, no un deseo vago.

**Cuándo aplica**: Antes de cualquier cambio medium o large. Simple changes pueden obviarlo, pero cualquier cosa que toque 4+ archivos necesita un checklist.

**Se viola cuando**: El cambio crece "mientras estamos en eso" o cuando no hay forma objetiva de saber si terminaste.

---

## 5. Ockham's Razor (Navaja de Ockham)

**Qué es**: La hipótesis más simple es probablemente la correcta. Si hay dos explicaciones, elegí la más simple primero.

**Para qué sirve**: Evitar sobre-ingeniería. Cuando algo falla, la causa más simple (typo, config incorrecta, permisos) es más probable que una race condition exótica o un bug del compilador.

**Cuándo aplica**: Al debuggear, al diseñar, al evaluar explicaciones. Empezá por lo simple. Si lo simple no funciona,subí de complejidad.

**Se viola cuando**: Se asume un bug complejo antes de verificar lo obvio, o se diseña una solución elaborada para un problema que tiene una solución trivial.

---

## 6. AHA — Avoid Hasty Abstraction (Evitá Abstracciones Apresuradas)

**Qué es**: No abstraigas hasta tener 3+ casos de uso. El código duplicado es mejor que la abstracción prematura.

**Para qué sirve**: Prevenir abstracciones que atan las manos. Una abstracción hecha con 1 caso de uso es un cuello de botella — cada cambio futuro tiene que adaptarse a una interfaz que se diseñó sin saber qué se necesita realmente.

**Cuándo aplica**: Cuando sentís la tentación de "generalizar" algo que solo se usa en un lugar. Duplicá primero, abstraé cuando tengas 3 usos reales y diferentes.

**Se viola cuando**: Se crea una interfaz/genérico/trait para algo que solo tiene una implementación, "porque después va a crecer".

---

## 7. Unix Philosophy (Filosofía Unix)

**Qué es**: Una herramienta = una tarea. Cada componente hace UNA cosa bien.

**Para qué sirve**: Mantener componentes simples, testeables y reemplazables. Un agente que explora no debería implementar. Un agente que aplica no debería diseñar.

**Cuándo aplica**: Al diseñar agentes, módulos, funciones, servicios. Si hace más de una cosa, dividilo.

**Se viola cuando**: Un agente hace de todo (explorar + diseñar + implementar + verificar), o una función tiene 5 responsabilidades.

---

## 8. Least Touch (Menor Contacto)

**Qué es**: Solo tocá los archivos explícitamente listados en el plan. Si notás algo fuera del scope, ANOTALO pero NO lo implementes.

**Para qué sirve**: Prevenir side effects. Cuando un agente toca código "que podría mejorar" mientras implementa un fix, introduce bugs en código que funcionaba. Cada archivo fuera del scope es un riesgo.

**Cuándo aplica**: SIEMPRE durante la implementación. Las observaciones van al plan, no al código.

**Se viola cuando**: El agente "mejora" código adyacente, agrega features que no se pidieron, o reestructura algo que funcionaba porque "estaba feo".

---

## 9. Progressive Detail (Detalle Progresivo)

**Qué es**: 3 niveles de detalle, no todo upfront. Nivel 1: Intención + Scope. Nivel 2: Plan con archivos afectados. Nivel 3: Diseño con arquitectura (solo para cambios grandes).

**Para qué sirve**: No desperdiciar tiempo planeando detalles que van a cambiar. Los cambios simples solo necesitan Nivel 1. Los medianos necesitan Nivel 2. Solo los grandes necesitan Nivel 3.

**Cuándo aplica**: Al planificar cualquier cambio. No escribas un design.md para un bugfix. No necesitas diagramas de arquitectura para cambiar un CSS.

**Se viola cuando**: Se escribe un diseño completo para un fix de 3 archivos, o se salta el plan para un cambio de 10 archivos.

---

## 10. Feynman Technique (Técnica de Feynman)

**Qué es**: Si no podés explicarlo de forma simple, no lo entendés. Los planes deben ser legibles por un junior.

**Para qué sirve**: Prevenir jerga innecesaria y complejidad artificial. Si un plan necesita un diccionario para entenderse, es demasiado complejo.

**Cuándo aplica**: Al escribir planes, diseños, documentación. Si un dev junior no lo entiende, simplificá.

**Se viola cuando**: Se usa jerga para impresionar, se escriben párrafos donde bastan bullets, o se asume conocimiento que el lector no tiene.

---

## 11. KISS — Keep It Simple, Stupid (Mantenelo Simple, Estúpido)

**Qué es**: La solución más simple que funciona. No "qué pasaría si algún día". Resolvé el problema de hoy, hoy.

**Para qué sirve**: Prevenir sobre-ingeniería. El código especulativo (que "algún día va a necesitar") es código muerto que mantiene vivo con cada refactor.

**Cuándo aplica**: Al elegir entre implementaciones. Si la simple funciona y la compleja "es más extensible", elegí la simple. Extendé cuando tengas el caso de uso real, no antes.

**Se viola cuando**: Se agrega configurabilidad para un caso que no existe, se preparan interfaces para funcionalidad futura, o se "future-proof" sin un requisito real.

---

## 12. Token Economy (Economía de Tokens)

**Qué es**: Cada token cuesta dinero. No repitas información, no expliques lo que el lector puede abrir, no des previews de lo que vas a hacer.

**Para qué sirve**: Ahorrar presupuesto. Una conversación donde el agente explica, resume, y vuelve a preguntar la misma cosa gasta 3x los tokens necesarios.

**Cuándo aplica**: Al escribir prompts, respuestas, cualquier comunicación agente-humano. Decilo una vez. Decilo simple. Si el archivo está en disco, resumí — no dupliques.

**Se viola cuando**: El agente explica algo, lo resume, y vuelve a preguntar; incluye el contenido completo de un archivo que el usuario puede abrir; describe lo que va a hacer antes de hacerlo.

---

## 13. Role Separation (Separación de Roles)

**Qué es**: El humano decide DIRECCIÓN (qué, por qué, hacia dónde). El agente decide TÉCNICA (cómo, qué patrón, qué código). Solo escalar al humano cuando los patrones existentes son perjudiciales o hay una alternativa significativamente mejor.

**Para qué sirve**: Evitar que el agente inunde al usuario con decisiones técnicas que el agente debería tomar automáticamente. "¿Gris o azul?" es dirección — el humano decide. "¿CSS before pseudo-element o JS textContent swap?" es técnica — el agente decide.

**Cuándo aplica**: En cada interacción agente-humano. El agente recomienda dirección (con justificación breve), el humano aprueba. Las decisiones técnicas se toman siguiendo los patrones existentes del codebase.

**Se viola cuando**: El agente muestra código, line numbers, o detalles de implementación en la conversación de scoping. O cuando el usuario tiene que decidir cosas que el agente debería saber resolver.

**El agente escala al humano solo cuando**: Seguir los patrones sería perjudicial, hay una alternativa 2x mejor, o la dirección del usuario choca con un principio core.

---

## 14. Decision Scope (Alcance de Decisiones)

**Qué es**: Las decisiones de un change específico van en el plan.md de ese change. Las decisiones de proyecto (arquitectura, stack, patrones cross-cutting) van en docs/decisions.md. No duplicar.

**Para qué sirve**: Evitar que decisions.md crezca infinitamente con decisiones que solo importan durante un change. Si "usar JSON para API keys" solo importa durante el change de persistencia, es una decisión del change, no del proyecto. Si "usar two-tier settings model" importa para todos los cambios futuros, es del proyecto.

**Cuándo aplica**: Al clasificar cualquier decisión. Regla práctica: si solo importa durante UN change, va al plan. Si importa para cambios FUTUROS, va a decisions.md.

**Se viola cuando**: Cada fix genera 3 ADRs en decisions.md, o cuando las decisiones del change se pierden porque no están documentadas en ningún lado.

---

## 15. Verify Before Present (Verificar Antes de Presentar)

**Qué es**: El orquestador verifica la implementación contra el Impact Checklist y las Decisions del plan ANTES de presentar al usuario. Si hay errores, re-delega al apply con fixes específicos (máximo 1 retry).

**Para qué sirve**: Prevenir bugs del sub-agente lleguen a producción. El apply agent puede cometer errores — el orquestador es el último filtro antes del usuario.

**Cuándo aplica**: Después de cada implementación. El orquestador lee los archivos tocados, verifica contra cada item del Impact Checklist, y revisa que las Decisions se respetaron. Si hay errores, envía fixes específicos. Si después de 2 pasadas sigue habiendo problemas, escala al usuario.

**Se viola cuando**: El orquestador presenta el resultado del apply agent sin verificar, o cuando se acepta "todo bien" sin leer los archivos cambiados.

---

*Cada principio surgió de un error concreto. No son reglas académicas — son cicatrices de código que rompimos, tokens que quemamos, y bugs que llegaron a producción.*