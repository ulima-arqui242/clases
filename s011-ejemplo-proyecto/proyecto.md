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

***Propuesta de valor***:

****Para los Salones de Belleza:****
  - **Visibilidad y Acceso a Nuevos Clientes:** InStudio ofrece a los salones pequeños y medianos la oportunidad de destacarse en un mercado competitivo, permitiéndoles llegar a un público más amplio y diverso a través de una   plataforma digital.
  - **Gestión Centralizada:** Los salones pueden gestionar su perfil, actualizar sus servicios, precios, y promociones en tiempo real, lo que facilita la adaptación a las necesidades del mercado.
  - **Reducción de Costos de Marketing:** Al utilizar InStudio, los salones pueden reducir los costos asociados con la publicidad tradicional, aprovechando la exposición que la plataforma les brinda.
  - **Fidelización de Clientes:** Mediante un sistema de reseñas y valoraciones, los salones pueden obtener feedback directo de sus clientes, mejorando la calidad del servicio y aumentando la lealtad de sus usuarios.
  - **Ver Ordenes de sus Clientes:** Los spas podran ver las ordenes realizadas por sus clientes, gestionar sus horarios para citas
  - **Analítica** : Dashboarding de métricas clave del negocio 

****Para los Clientes:****

- **Comodidad y Facilidad de Uso:** InStudio permite a los usuarios explorar y comparar múltiples opciones de salones de belleza desde la comodidad de sus hogares, con información detallada y actualizada sobre servicios, precios, y horarios.
- **Transparencia y Confianza:** Los usuarios pueden tomar decisiones informadas basadas en las reseñas y valoraciones de otros clientes, asegurándose de recibir un servicio de calidad.
- **Ofertas y Promociones Exclusivas:** Los clientes pueden acceder a ofertas especiales y descuentos exclusivos al reservar a través de la plataforma, lo que les permite ahorrar dinero mientras disfrutan de servicios de belleza.
- **Reservar cita online mediante módulo de pago**: Reservar en el spa deseado el servicio que deseen --> Ver disponibilidad de citas

***Segmento de Clientes***:

InStudio tiene dos segmentos principales de clientes:

- Salones de Belleza (PYMES)
- Clientes Usuarios Finales

A continuación, se detallan las características y necesidades de cada segmento:
- **Salones de Belleza (PYMES)** : Este segmento incluye a pequeños y medianos salones de belleza que buscan aumentar su visibilidad, atraer más clientes y optimizar la gestión de sus servicios. (Salones Nuevos o Emergentes, Salones Establecidos con Baja Presencia Digital)
- **Clientes Usuarios Finales** : Personas que buscan acceder a servicios de belleza de manera conveniente, comparando opciones según sus necesidades y preferencias. (Adultos Jóvenes (18-35 años), Profesionales Ocupados)

***Canales de Distribución:***

***Relaciones con clientes:***

***Fuentes de Ingresos:***

***Recursos Clave***

***Actividades Clave***

***Socios Clave:***

***Estructura de Costos:***


**1.3. Estructura del Equipo**

