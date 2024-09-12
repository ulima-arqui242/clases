### Plantilla de ADR (Architecture Decision Record)

#### Indicaciones:
- **Título**: Describa claramente la decisión que se está tomando. Debe ser corto.
- **Contexto**: Describa el problema o situación que impulsa la toma de decisiones. Debe ser específico sobre las características de la empresa o el proyecto que afectan la decisión (volumen de usuarios, tipo de datos, normativa actual, etc.).
- **Alternativas**: Enumere al menos dos alternativas con una descripción completa de cada una. Asegúrese de que las alternativas sean viables y realistas. Puede utilizar todo tipo de fuentes para encontrar alternativas o documentarlas en detalle (no abusen de la IA).
- **Criterios de Elección**: Defina los factores clave que influyen en la decisión, como el rendimiento, las habilidades del equipo, el costo, etc. Sea específico sobre cómo estos criterios impactan al sistema que está construyendo.
- **Decisión**: Declare la alternativa seleccionada.
- **Sustento**: Justifique la decisión basada en los criterios de elección. Especifique cómo la decisión se alinea con las necesidades de la empresa y mencione características técnicas que ofrezcan ventajas específicas para el contexto dado.

---

### Ejemplos (para CrediMype)

#### Decisión 1 (Elección de Tecnología)

**Título**:  
- Elección entre Lenguaje Tipado vs No Tipado para todo el proyecto

**Contexto**:  
- El equipo de desarrollo es muy pequeño (3 desarrolladores) los cuales tienen experiencia con Java, Javascript y Python. La velocidad de desarrollo es crucial dado que la empresa está constantemente agregando nuevas funcionalidades. A pesar de esto, se necesita un nivel adecuado de seguridad y robustez para proteger los datos financieros de los usuarios.

**Alternativas**:  
1. **Lenguaje Tipado (Java, Kotlin)**  
   - Ofrece mayor seguridad de tipos, lo que reduce errores en tiempo de ejecución.
   - Proceso de desarrollo más rígido pero mejora la mantenibilidad y robustez a largo plazo.
2. **Lenguaje No Tipado (JavaScript, Python)**  
   - Desarrollo ágil y flexibilidad en las primeras fases.
   - Con Node.js, ofrece capacidades de concurrencia eficientes para manejar solicitudes múltiples.
   - Puede facilitar la interacción con el frontend al manejar un solo lenguaje.

**Criterios de Elección**:  
- Velocidad de desarrollo.
- Minimizar la cantidad de lenguajes diferentes que utilizará el equipo (son pocos desarrolladores).
- Flexibilidad para cambios rápidos en los módulos de la plataforma.
- Necesidades de seguridad y robustez en los módulos financieros.

**Decisión**:  
- Se elige JavaScript.

**Sustento**:  
- Dado el rápido ritmo de crecimiento y la necesidad de iterar rápidamente, JavaScript proporciona la flexibilidad necesaria. Node.js facilita el manejo de múltiples solicitudes concurrentes en tiempo real, además ha sido Mantener el mismo lenguaje (Javascript) en frontend y backend reduce la complejidad del stack tecnológico, facilitando que el equipo actual pueda hacer frente a estos desafíos. Es cierto que un lenguaje tipado podría ofrecer más seguridad y robustez, pero los aspectos previamente mencionados son más importantes en el contexto actual.

---

#### Decisión 2

**Título**:  
- Elección entre un modelo de datos relacional vs documental para el manejo de los datos del módulo de CRM

**Contexto**:  
- La información de los clientes, almacenada por el módulo de CRM, es menos estructurada que la del resto de la plataforma. Suelen almacenarse también interacciones con el soporte y comunicaciones por diversos canales. Se está revisando si se utilizará el modelo relacional (como en otros módulos) o se opta por un esquema documental.

**Alternativas**:  
1. **Modelo Relacional (PostgreSQL)**  
   - Garantiza consistencia entre los datos.
   - Permite manejar relaciones complejas con entidades de otros módulos como clientes y sus préstamos.
2. **Modelo Documental (MongoDB)**  
   - Escalabilidad horizontal para manejar datos no estructurados, como interacciones de clientes.
   - Flexibilidad para manejar esquemas cambiantes.

**Criterios de Elección**:  
- Integridad de datos y soporte para consultas estructuradas.
- Flexibilidad en la definición del esquema de los datos de clientes.
- Requisitos de escalabilidad para el CRM.

**Decisión**:  
- Se elige un modelo documental (como MongoDB).

**Sustento**:  
- La escalabilidad que se requiere es bastante grande, y el módulo puede operar totalmente aislado de los módulos relacionados con las transacciones financieras (que requieren propiedades ACID). PostgreSQL ofrece flexibilidad para manejar JSON, pero es posible que el alto tráfico de las interacciones pueda tener influencia en módulos críticos.
