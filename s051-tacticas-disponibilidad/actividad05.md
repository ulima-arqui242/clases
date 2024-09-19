# Tácticas de Disponibilidad

En esta actividad utilizaremos los nuevos conceptos de diseño que estamos aprendiendo (en este caso tácticas), para enriquecer nuestra propuesta de arquitectura.
Cada integrante del grupo debe, en su módulo correspondiente, identificar escenarios de disponibilidad. Luego de ello, debe elegir una táctica que permita obtener la medida de respuesta deseada en el escenario. El resultado final será la implementación de una táctica, la cual se documentará en forma de una decisión de arquitectura.
Debe presentar la información de esta forma:
- Mencionar el escenario (Es importante que los escenarios de encuentren codificados para poder tener trazabilidad en el documento).
- Mencione la táctica.
- Documente la decisión de elección de la táctica utilizando un formato de ADR. En caso existan varias opciones de implementación de la táctica (elección de tecnología), también puede considerarlas.

## Ejemplo

### Escenario
Consideremos el siguiente escenario para CrediMype

| **Cod Escenario** | **Atributo de Calidad** | **Estímulo**                           | **Fuente del Estímulo** | **Artefacto**                  | **Entorno**                         | **Respuesta**                                                | **Medida de Respuesta**                             |
|------------------|-------------------------|----------------------------------------|-------------------------|--------------------------------|-------------------------------------|-------------------------------------------------------------|-----------------------------------------------------|
| ESC-01           | Disponibilidad           | Fallo en el servidor de base de datos  | Servidor de la nube      | Módulo de Procesamiento de Pagos | Operación en horario laboral con alta demanda                | El sistema continúa operando sin interrupciones   | El sistema mantiene una disponibilidad del 99.9% anual |


### Táctica Elegida
En este caso, para poder llegar a los niveles de respuesta deseados según el escenario (99.9% anual) se está eligiendo la táctica de disponibilidad de redundancia activa. A continuación documentamos los detalles de la decisión.

### Documentación de la Decisión (ADR)

**Título**:  
- Elección entre Redundancia Activa vs Redundancia Pasiva para el Módulo de Procesamiento de Pagos.

**Contexto**:  
- La plataforma maneja transacciones críticas para micro y pequeñas empresas, principalmente durante periodos de alta actividad, como el fin de mes o fechas de vencimiento de préstamos. La interrupción del módulo de procesamiento de pagos podría generar incumplimientos de pago, afectando la confianza de los usuarios en la plataforma. La operación se lleva a cabo a través de servidores en la nube de AWS, lo que podría facilitar la implementación de tácticas de disponibilidad.

**Alternativas**:
1. **Redundancia Activa**  
   - Se mantienen varios servidores activos, todos recibiendo solicitudes. Si uno falla, las solicitudes son automáticamente redirigidas a otro servidor activo sin interrupción.
   - Proporciona tiempos de conmutación imperceptibles para el usuario final, por lo que permite mantener una solución en alta disponibilidad.
   - Requiere una mayor inversión en infraestructura y monitoreo constante.

2. **Redundancia Pasiva**  
   - Un servidor está activo mientras que uno o varios servidores de respaldo están en espera. Cuando el servidor principal falla, el servidor de respaldo se activa para asumir las operaciones.
   - Menor costo operativo pero con tiempos de conmutación más largos, lo que puede afectar la disponibilidad en momentos críticos.
   - Puede implementarse para sistemas no críticos donde periodos de inactividad pueden ser tolerados.

**Criterios de Elección**:  
- Importancia crítica del tiempo de inactividad.
- Impacto financiero y reputacional de la inactividad.
- Costo de operación.
- Escalabilidad ante picos de demanda.
- Transparencia en la transición durante fallos.

**Decisión**:  
- Se elige la **Redundancia Activa**.

**Sustento**:  
- Debido a la naturaleza crítica del módulo de procesamiento de pagos y la necesidad de mantener una alta disponibilidad sin interrupciones, la redundancia activa garantiza que no haya pérdida de servicio ante fallos del servidor. Esto es clave para evitar cualquier afectación a las micro y pequeñas empresas que dependen del sistema para cumplir con sus obligaciones financieras. A pesar de que la redundancia activa implica mayores costos, se justifica la inversión por el valor que proporciona en términos de confiabilidad y continuidad del servicio, factores esenciales para la confianza de los clientes en la plataforma.


