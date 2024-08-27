# Proyecto del Curso - Grupo 10

Bienvenidos al repositorio del Proyecto del Curso del Grupo 10. Aquí encontrarán toda la documentación y archivos relevantes para nuestro proyecto.

## Índice

1. [Integrantes del grupo](01.%20integrantes/integrantes.md)
2. Tema del Proyecto

## Tema de proyecto: InStudio
InStudio es una aplicación web diseñada para conectar a los usuarios con una variedad de salones de belleza (PYMES) pequeños y medianos. InStudio permite a los salones registrarse y administrar sus servicios, mientras que los clientes pueden explorar, comparar ,dejar reseñas fácilmente y reservar una cita en el spa deseado.

## Modulos
- **Gestión de Reservas:** Este módulo permite a los usuarios realizar, modificar, y cancelar reservas en salones de belleza. Los salones pueden administrar sus horarios, gestionar la disponibilidad de servicios y personal, y confirmar o rechazar citas. --- (Manejo de Colas)
- **Notificaciones:**  El sistema de notificaciones busca mantener a los usuarios y salones informados sobre sus actividades dentro de la plataforma. Notificaciones push y correos electrónicos para confirmaciones de reserva, recordatorios de citas, y ofertas especiales. -- (Firebase Push Notifications) --> analiis de eventos (oferta o reserva)
- **Gestión de Ofertas:**  Este módulo permite a los salones de belleza crear y gestionar promociones y ofertas especiales para atraer más clientes. Creación de ofertas con fechas de inicio y fin, descuentos, y condiciones especiales. Visualización de las ofertas en la página principal de cada salón. (Upload de imagen de la promoción a S3)  -- MongoDB para flexibilidad (validar)
- **Auth/Seguridad - Gestión de Pagos:** Este módulo asegura que la plataforma sea segura para todos los usuarios y facilita la gestión de pagos por parte de los clientes. Autenticación y autorización de usuarios.  Gestión de facturación para la reservas. --> JWT / Outh2  -- Pagos -> Stripe
- **Analítica -> Descarga de Datos Masivos:** Este módulo proporciona a los salones herramientas para analizar el rendimiento de sus servicios, la satisfacción de sus clientes, y la efectividad de sus promociones. Dashboards personalizables con métricas clave como número de reservas, ingresos generados, y tasa de cancelación. Permite a los administradores exportar datos detallados en formato CSV o Excel para un análisis más profundo fuera de la plataforma. Esto incluye datos de reservas, pagos, y reseñas, facilitando la integración con herramientas de BI. -- (Lambda , --> evaluación de otras adicionales)

**1. Caso de Negocio**

**1.1. Generalidades**

**Nombre del startup:**  InStudio

Tras la pandemia, el sector de la belleza en Perú no se ha podido recuperar y actualmente enfrenta una grave crisis laboral que amenaza con la pérdida de aproximadamente 100,000 empleos, afectando principalmente a las mujeres, que constituyen el 90% de la fuerza laboral de este rubro, y a la comunidad LGBT. Dado que 3 mil a 7 mil trabajadores se han convertido trabajadores independientes (Hérnandez, 2024). Se decidió crear InStudio, una página web que le brindaría a los clientes información sobre los servicios que puede recibir en cada salon de belleza, como sus precios, sus horarios, sus ofertas, sus servicios, entre otros. De esta manera, los salones de belleza se pueden dar a conocer ante el público.

**1.2. Modelo de Negocio**

**Canvas de Modelo de Negocio**

- Ruta de enlace al Canvas de InStudio: 
  https://www.canva.com/design/DAGPE7GwV5E/_zWjxflfOcCKQ94MVStm_g/view?utm_content=DAGPE7GwV5E&utm_campaign=designshare&utm_medium=link&utm_source=editor

![alt text](<Canvas de Modelo de Negocio Tabla para estrategia planeación negocio pastel moderno.png>)

**1.3. Estructura del Equipo**

Nuestro equipo en InStudio está compuesto por expertos con experiencia en tecnología, belleza y gestión empresarial:

- CEO: Lidera la visión estratégica y el crecimiento general de InStudio.
- CTO: Supervisa el desarrollo y mantenimiento de la plataforma digital.
- COO: Gestiona las operaciones diarias y establece alianzas estratégicas con salones de belleza.
- Equipo de Desarrollo: Ingenieros y diseñadores dedicados a la creación y mejora continua de la plataforma.
- Equipo de Atención al Cliente: Proporciona soporte en línea y asistencia a salones y clientes.
- Equipo de Marketing: Encargado de las estrategias de promoción y publicidad para atraer y retener usuarios.

**1.4. Listado de Stakeholders**

| **Stakeholder** | **Rol** | **Responsabilidad** | **Interés en la arquitectura** |
| --- | --- | --- | --- |
| Salones de belleza | Cliente | Usan la plataforma para gestionar servicios y reservas | Asegurar que la plataforma sea fácil de usar y eficaz en la gestión de citas y clientes |
| Clientes (usuarios finales) | Cliente | Utilizan la plataforma para buscar y reservar servicios de belleza | Garantizar una experiencia de usuario fluida y accesible |
| Inversionistas y accionistas | Conformance Checker | Invierten en el proyecto y esperan retorno de inversión | Verificar que la plataforma cumpla con los estándares de calidad y la hoja de ruta del proyecto |
| Reguladores y organismos de protección de datos | Representante de Sistema Externo | Aseguran el cumplimiento con regulaciones de privacidad y seguridad | Definir los requisitos y asegurar el cumplimiento con las leyes de protección de datos |
| Colaboradores | Ingeniero de sistemas | Responsable del diseño de sistemas o componentes | Asegurar el entorno provisto por el sistema |
