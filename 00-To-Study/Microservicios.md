### Fase 0: Fundamentos — Definición de Límites (PREREQUISITO)

- **Domain-Driven Design (DDD) Táctico:**
    
    - Entidades, Value Objects, Aggregates, Aggregate Roots.
        
    - Ubiquitous Language y su rol en la comunicación del equipo.
        
- **Bounded Contexts:**
    
    - Cómo definir los límites de cada microservicio.
        
    - Context Mapping: relaciones entre bounded contexts (Partnership, Customer-Supplier, Conformist, Anti-Corruption Layer).
        
    - Peligro del "Distributed Monolith": servicios demasiado acoplados.
        
- **Criterios de Descomposición:**
    
    - Descomposición por negocio (subdominios) vs descomposición técnica.
        
    - Heurísticas: "¿Puede este equipo deployar independientemente?"

---

### Fase 1: Descentralización de Datos

- **Patrón _Database per Service_:**
    
    - Aislamiento de estado y esquemas.
        
    - Antipatrón de base de datos compartida.
        
- **Modelos de Consistencia:**
    
    - Limitaciones de las transacciones ACID en sistemas distribuidos.
        
    - Concepto e implicancias de la Consistencia Eventual (_Eventual Consistency_).
        
    - Teorema CAP: Consistency, Availability, Partition Tolerance — elegí 2 de 3.

---

### Fase 2: Service Discovery y Comunicación entre Servicios

- **_Service Registry & Discovery_:**
    
    - Registro dinámico de instancias (latidos o _heartbeats_).
        
    - Descubrimiento del lado del cliente vs. del lado del servidor.
        
    - Balanceo de carga del lado del cliente (_Client-side load balancing_).
        
- **Protocolos Síncronos:**
    
    - REST (HTTP/1.1): Contratos y OpenAPI.
        
    - gRPC (HTTP/2): Serialización binaria (Protobuf), multiplexación y baja latencia.
        
    - Riesgos del acoplamiento temporal.
        
- **Protocolos Asíncronos:**
    
    - Arquitectura Orientada a Eventos (EDA).
        
    - Publicación/Suscripción (_Pub/Sub_) y Colas de Mensajes.
        
    - Message Brokers: Kafka, RabbitMQ — diferencias conceptuales.

---

### Fase 3: Gestión de Fronteras (Edge)

- **API Gateway:**
    
    - Enrutamiento dinámico, composición de respuestas, autenticación y _Rate Limiting_.
        
    - Gateway como punto de entrada único al sistema.
        
- **Patrón _Backend for Frontend_ (BFF):**
    
    - Agregación de datos adaptada a tipos específicos de clientes (web, móvil).
        
- **API Versioning:**
    
    - Estrategias: URL path, headers, content negotiation.
        
    - Evolución de contratos sin romper clientes existentes.

---

### Fase 4: Transacciones Distribuidas

- **Patrón Saga:**
    
    - Diseño de transacciones compensatorias (Rollback semántico).
        
    - Saga Coreografiada: Comunicación descentralizada mediante eventos.
        
    - Saga Orquestada: Control de flujo centralizado mediante un servicio coordinador.
        
    - Cuándo usar cada una: trade-offs y criterios de decisión.
        
- **Patrón CQRS (_Command Query Responsibility Segregation_):**
    
    - Segregación a nivel lógico (distintos modelos en código).
        
    - Segregación a nivel físico (distintas bases de datos sincronizadas mediante eventos).
        
    - Cuándo vale la pena y cuándo es over-engineering.

---

### Fase 5: Resiliencia y Tolerancia a Fallos

- **Patrón _Circuit Breaker_ (Cortocircuito):**
    
    - Estados del circuito: Cerrado, Abierto, Semi-abierto.
        
    - Gestión de umbrales de fallo y tiempos de espera.
        
- **Patrones de Recuperación:**
    
    - _Fallback_: Provisión de respuestas degradadas por defecto.
        
    - _Retries_ (Reintentos) con _Exponential Backoff_ y _Jitter_.
        
    - Timeout patterns y deadline propagation.
        
- **Patrón _Bulkhead_ (Mamparo):**
    
    - Aislamiento de recursos (pools de hilos o semáforos) para prevenir fallos en cascada.
        
- **Rate Limiting y Throttling:**
    
    - Protección contra sobrecarga y abusos.

---

### Fase 6: Observabilidad Distribuida

- **_Distributed Tracing_ (Trazabilidad Distribuida):**
    
    - Propagación de contexto: _Trace IDs_ y _Span IDs_.
        
    - Análisis de cuellos de botella en peticiones multi-servicio.
        
- **Telemetría y Monitorización:**
    
    - _Logging_ estructurado (JSON) y agregación centralizada.
        
    - _Health Checks_: Liveness y Readiness probes.
        
    - Métricas: RED method (Rate, Errors, Duration) y USE method (Utilization, Saturation, Errors).
        
- **Alerting:**
    
    - Definición de SLOs, SLIs y SLAs.
        
    - Alertas accionables vs ruido.

---

### Fase 7: Deployment y Operación

- **Containerización:**
    
    - Docker a nivel conceptual: imágenes, contenedores, layers.
        
    - Orquestación: Kubernetes pods, services, deployments (conceptos base).
        
- **Estrategias de Deployment:**
    
    - Blue-Green, Canary, Rolling deployments.
        
    - Feature Flags y toggles.
        
- **Gestión de Configuración:**
    
    - Configuración externa (Config Servers).
        
    - Secrets management.
        
- **CI/CD para Microservicios:**
    
    - Pipelines independientes por servicio.
        
    - Contract Testing (Pact) para verificar compatibilidad entre servicios.
        
    - Testing en entornos efímeros.
