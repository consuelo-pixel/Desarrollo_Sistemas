# Especificación de requisitos del sistema

## 1. Actores del sistema

| N.º | Actor | Interacción con el sistema |
|---|---|---|
| ACT-01 | Recepcionista | Registra clientes y equipos, abre órdenes y gestiona el pago y la entrega. |
| ACT-02 | Técnico asignado | Consulta sus órdenes, actualiza estados, registra notas y detalla repuestos y costos. |
| ACT-03 | Cliente | Consulta el estado y presupuesto de su reparación y acepta o rechaza el presupuesto en línea. |
| ACT-04 | Dueño/administrador | Consulta el panel y los reportes semanales y mensuales. |

## 2. Requisitos funcionales

| N.º | Requisito | Actor(es) |
|---|---|---|
| RF-01 | El sistema debe permitir registrar los datos de identificación de cada cliente, incluido su número de carnet. | Recepcionista |
| RF-02 | El sistema debe permitir abrir una orden de trabajo por cada equipo recibido y asociarla con el cliente correspondiente. | Recepcionista |
| RF-03 | El sistema debe registrar la marca, modelo, número de serie, accesorios incluidos y falla reportada de cada equipo. | Recepcionista |
| RF-04 | El sistema debe generar un código único de ticket para cada orden de trabajo. | Recepcionista |
| RF-05 | El sistema debe permitir asignar un técnico a cada orden. | Recepcionista |
| RF-06 | El sistema debe permitir al técnico consultar las órdenes que tiene asignadas. | Técnico |
| RF-07 | El sistema debe permitir cambiar el estado de una orden a “En diagnóstico”, “Esperando repuestos”, “Reparado” o “Entregado”. | Técnico |
| RF-08 | El sistema debe permitir registrar notas técnicas en la orden de trabajo. | Técnico |
| RF-09 | El sistema debe permitir listar los repuestos necesarios y registrar el costo de cada uno. | Técnico |
| RF-10 | El sistema debe calcular y mostrar el presupuesto estimado según los conceptos y costos registrados en la orden. | Técnico, cliente |
| RF-11 | El sistema debe permitir al cliente consultar sus reparaciones mediante su carnet o código de ticket y ver el estado y presupuesto de la orden. | Cliente |
| RF-12 | El sistema debe permitir al cliente aceptar o rechazar el presupuesto en línea y guardar su decisión. | Cliente |
| RF-13 | El sistema debe permitir a la recepcionista registrar el monto y medio de pago —efectivo, tarjeta o transferencia— y generar una nota de venta o recibo PDF imprimible. | Recepcionista |
| RF-14 | Al cerrar una orden, el sistema debe registrar la fecha de finalización y calcular automáticamente la garantía de 90 días. | Recepcionista, sistema |
| RF-15 | El sistema debe mostrar reportes semanales y mensuales con equipos atendidos, productividad de los técnicos, ingresos totales y repuestos más solicitados. | Dueño/administrador |

## 3. Requisitos no funcionales

| N.º | Requisito no funcional | Base |
|---|---|---|
| RNF-01 | Las búsquedas de tickets deben responder en menos de 2 segundos. | Caso |
| RNF-02 | El sistema debe soportar al menos 30 consultas de tickets simultáneas sin dejar de responder. | Caso |
| RNF-03 | El sistema debe alcanzar una disponibilidad mensual de al menos 99,5%, excluyendo mantenimientos programados. | Propuesta |
| RNF-04 | Las contraseñas deben guardarse mediante un hash seguro con sal individual; nunca en texto plano. | Protección indicada en el caso; detalle técnico propuesto |
| RNF-05 | El sistema debe aplicar permisos por rol y rechazar acciones que no correspondan al rol del usuario. | Caso |
| RNF-06 | La comunicación entre el navegador y el sistema debe usar HTTPS con TLS 1.2 o superior. | Propuesta |
| RNF-07 | Los datos personales y las copias de seguridad deben cifrarse cuando estén almacenados. | Propuesta |
| RNF-08 | La consulta por carnet o ticket debe mostrar solo los datos de la reparación correspondiente, sin exponer información personal innecesaria ni órdenes de otros clientes. | Propuesta |
| RNF-09 | La interfaz debe adaptarse a pantallas de 360 a 1920 píxeles de ancho sin cortar contenido ni requerir desplazamiento horizontal. | Caso; rango propuesto |
| RNF-10 | El sistema debe funcionar en las dos versiones estables más recientes de Chrome, Firefox y Edge en escritorio, y Chrome y Safari en móviles. | Propuesta |
| RNF-11 | Las funciones principales deben poder usarse con teclado y cumplir el nivel AA de WCAG 2.1. | Propuesta |
| RNF-12 | El sistema debe generar una copia de seguridad diaria, conservarla durante al menos 30 días y permitir restaurarla en un máximo de 4 horas. | Propuesta |
| RNF-13 | El PDF del recibo debe poder abrirse e imprimirse en tamaño A4 sin cortar información y generarse en menos de 5 segundos. | Caso; tamaño y tiempo propuestos |
| RNF-14 | Las pantallas, etiquetas y mensajes de validación deben estar en español. | Propuesta |
| RNF-15 | El sistema debe guardar el usuario y la fecha y hora de los cambios de estado, presupuesto, pago y cierre; esos registros deben conservarse por al menos 12 meses. | Propuesta |