# Actividad 04: Decisiones de Arquitectura

En esta actividad empezaremos con la definición de las decisiones de arquitectura de nuestro proyecto. Varias de ellas serán producto de la aplicación de tácticas pero podemos empezar a realizar algunas decisiones en función a las categorías vistas en clase:

- Asignación de Responsabilidades.
- Modelo de Coordinación.
- Modelo de Datos.
- Gestión de Recursos.
- Elección de Tecnología.

Realice la especificación de decisiones importantes por módulo, se cuenta con una plantilla de ADR con una estructura definida y ejemplos sobre esta misma carpeta.

Algunas sugerencias de decisiones que pueden tomarse en cuenta en esta etapa.

- Estructura de la aplicación: Veremos algunos patrones más adelante, pero podrían empezar a considerar algunas decisiones estructurales. Por ejemplo, monolito vs microservicios, arquitectura en capas vs arquitectura hexagonal. Estas decisiones irían en la categoría de Asignación de Responsabilidades.

- Comunicación entre módulos: La manera en que un módulo puede invocar funcionalidades de otro módulo. Por ejemplo, REST API vs mensajería en colas, gRPC vs WebSockets, entre otros casos. Estas decisiones irían en la categoría de Modelo de Coordinación.

- Lenguajes de programación: Tipado estático vs tipado dinámico, lenguajes de programación específicos (Java vs Python), lenguajes de programación para desarrollo móvil (Java vs Kotlin). Estas decisiones irían en la categoría de Asignación de Elección de Tecnología.

- Frameworks: Para frontend (React vs Angular vs Vue), para backend (Express vs NestJs), para CSS (Material UI vs Bootstrap vs Bulma). Estas decisiones irían en la categoría de Asignación de Elección de Tecnología.

- Elección de Motores de BD: Motores SQL vs No SQL (la elección la pueden hacer por módulo y seleccionar varios motores), elección entre motores de un tipo específico (Postgres vs MariaDB, MongoDB vs CosmosDB). La decisión del tipo de modelo (relacional, documental, clave-valor, etc.) iría en la categoría de Modelo de Datos. Sin embargo, la elección particular del motor iría en la sección de Elección de Tecnología.