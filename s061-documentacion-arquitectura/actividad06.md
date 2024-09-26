# Actividad: Documentación de Arquitectura

## Parte 1: Tácticas de Disponibilidad y Mantenibilidad

Para poder tener una mayor cantidad de elementos que incluir en nuestros gráficos, agregaremos **tácticas de disponibilidad y mantenibilidad**. Con ello enriqueceremos nuestra propuesta de arquitectura.

Cada integrante del grupo debe, en su módulo correspondiente, identificar escenarios de disponibilidad y mantenibilidad. A continuación, deben elegir una táctica que permita obtener la medida de respuesta deseada en el escenario. El resultado final será la implementación de una o varias tácticas, las cuales se documentarán, al igual que el entregable anterior, en forma de ADR.

Dado que estamos diseñando aplicaciones desde cero, no aplicarán tácticas como la reducción de módulos o el refactoring. Sin embargo, se pueden utilizar técnicas de **parametrización** para mejorar la mantenibilidad. Un ejemplo de parametrización para CrediMype sería diseñar el sistema de manera que la configuración de parámetros operativos (como límites de crédito en una aplicación de préstamos) se pueda ajustar sin modificar el código fuente, facilitando la gestión y actualización de datos.

Debemos realizar lo siguiente:
1. Mencionar el escenario (Es importante que los escenarios de encuentren codificados para poder tener trazabilidad en el documento).
2. Mencionar la táctica de disponibilidad o mantenibilidad elegida.
3. Documentar la decisión de elección de la táctica utilizando un formato de ADR. En caso existan varias opciones de implementación de la táctica (elección de tecnología), también puede considerarlas.

### Ejemplo

#### Escenario
Consideremos el siguiente escenario para CrediMype

| **Cod Escenario** | **Atributo de Calidad** | **Estímulo**                           | **Fuente del Estímulo** | **Artefacto**                  | **Entorno**                         | **Respuesta**                                                | **Medida de Respuesta**                             |
|------------------|-------------------------|----------------------------------------|-------------------------|--------------------------------|-------------------------------------|-------------------------------------------------------------|-----------------------------------------------------|
| ESC-02           | Mantenibilidad           | Cambios en los montos máximos para otorgar préstamos        | Equipo de Desarrollo     | Módulo de Evaluación de Riesgo   | Entorno de desarrollo y producción  | Los cambios se aplican sin necesidad de modificar el código fuente | Los cambios están en producción en un tiempo de 2 horas |


---

## Parte 2: Documentación de la Arquitectura con el Modelo C4

En esta segunda parte de la actividad, cada integrante del equipo debe elaborar la documentación de la arquitectura de su módulo utilizando el modelo **C4**. Esto incluye los siguientes niveles:

### 1. Diagrama de Contexto
Este diagrama muestra la visión más alta de la arquitectura, definiendo el sistema en su entorno, y las interacciones con usuarios del mismo y sistemas externos.

**Lineamientos**:
- Definan con claridad quiénes son los usuarios y sistemas externos que interactúan con su sistema. En caso tengan módulos totalmente aislados, puede ser relevante hacer más de un diagrama.
- Representen las relaciones a través de líneas simples indicando el tipo de interacción.
- Mantengan la simplicidad, limitando la cantidad de elementos que aparecen en este diagrama.

### 2. Diagrama de Contenedores
Este diagrama ilustra los contenedores dentro del sistema, es decir, aplicaciones, bases de datos, microservicios y otros elementos, que forman la solución y cómo interactúan entre ellos.

**Lineamientos**:
- Enfóquense en mostrar las principales aplicaciones o servicios y cómo interactúan entre sí.
- Representen las tecnologías utilizadas en cada contenedor (ejemplo: bases de datos, servicios REST).
- Definan los límites de los subsistemas que componen la solución.

### 3. Diagrama de Componentes
Este diagrama profundiza en uno o varios contenedores, descomponiéndolos en los componentes clave que colaboran para proporcionar la funcionalidad del sistema.

**Linamientos**:
- Dividan los contenedores en sus componentes internos, como librerías, módulos, y otros elementos.
- Representen cómo estos componentes interactúan y colaboran dentro del contenedor.
- Especifiquen el propósito de cada componente y cómo se integra con los demás.

### Referencia y Ejemplos
Pueden visitar la [página oficial](https://c4model.com/).

### Entregables:
- Crear los tres diagramas (contexto, contenedores y componentes) utilizando la herramienta de su preferencia (como código o como diagramación).
- Incluir una breve descripción debajo de cada diagrama explicando los elementos y sus interacciones.
