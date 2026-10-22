# Turbine · Resumen breve para el equipo

## ¿Qué aplicación nos piden?

Una **web interna**, independiente de Brain, para registrar clientes, emitir facturas y seguir cobros con poco trabajo manual. Debe funcionar bien en móvil y ordenador. Los clientes de Turbine reciben facturas y avisos, pero **no entran en la aplicación**. La aplicación **no cobra**: comprueba si se ha pagado. Para el proyecto se puede simular Stripe.


## Requisitos funcionales, agrupados por actor

**Personal de Turbine (todos los perfiles)**

| ID | Qué debe hacer |
| --- | --- |
| RF-01 | Iniciar sesión con correo corporativo y contraseña; **la aplicación** valida el dominio (@turbineh.com). |
| RF-02 | Recuperar la contraseña mediante un enlace con caducidad, validado por la aplicación.   |

**Empleado operativo** (sobre sus clientes asignados y según permisos; el administrador también puede actuar sobre todos)

| ID | Qué debe hacer |
| --- | --- |
| RF-03 | Gestionar empresas y varios contactos, distinguiendo datos comerciales y fiscales, país y moneda; validar datos, advertir duplicados y conservar histórico al desactivar o reactivar fichas.  |
| RF-04 | Buscar clientes por nombre, identificador fiscal, ubicación o sector y facturas por número, fecha, tipo o estado, dentro del ámbito autorizado.  |
| RF-05 | Preparar y emitir facturas puntuales o recurrentes con líneas de concepto, cantidad, precio, descuento e impuesto; corregir borradores y previsualizar, bloqueando la emisión si faltan datos fiscales.   |
| RF-06 | Revisar anualmente el tramo con datos verificados y proponer cambios de tarifa o descuentos con vigencia; exigir aprobación cuando corresponda, sin modificar facturas históricas ni regularizar automáticamente meses anteriores.  |
| RF-07 | Generar y conservar el PDF emitido con datos fiscales, fechas, líneas, impuestos, total e imagen corporativa; asignar serie y número únicos al emitir.  |
| RF-08 | Conciliar manualmente cobros dudosos, corregir o revertir asociaciones con motivo e historial; mantener pendiente una factura no totalmente saldada.  |
| RF-09 | Registrar y aplicar la baja efectiva, deteniendo nuevas mensualidades aunque exista deuda y manteniendo el recobro anterior; no esperar al pago para completar la baja comercial.  |
| RF-10 | Gestionar la suscripción separada de sus facturas: plan, tarifa, responsable, condiciones de pago, inicio y estados; permitir inicio futuro, pausa y reactivación con fechas y motivo, sin generar mensualidades durante la pausa.  |
| RF-11 | Consultar informes por periodo, cliente, responsable, tipo y estado; exportar a CSV y PDF únicamente los datos autorizados.  |
| RF-12 | Importar clientes por CSV con mapeo y previsualización; detectar errores y duplicados antes de confirmar y registrar el resultado de la importación. |

**Administrador**

| ID | Qué debe hacer |
| --- | --- |
| RF-13 | Crear o desactivar usuarios y gestionar permisos y asignaciones de clientes, manteniendo la autoría histórica y transfiriendo el seguimiento pendiente al nuevo responsable; no admitir autorregistro.  |
| RF-14 | Consultar el panel global de facturado, cobrado, pendiente y vencido por periodo, distinguiendo recurrente y puntual y accediendo al detalle que justifica los totales.   |
| RF-15 | Aprobar o rechazar cambios económicos excepcionales y revisiones de tarifa según permisos y umbrales; registrar decisión y motivo, impedir el envío pendiente de aprobación y evitar autoaprobación cuando la política lo exija.   |
| RF-16 | Rectificar facturas emitidas mediante documentos vinculados al original, con permisos y aprobación cuando corresponda; conservar ambos y actualizar el saldo, sin editar silenciosamente la factura emitida.  |

**Responsable de configuración** (superadministrador con permiso adicional; también ejerce las capacidades administrativas)

| ID | Qué debe hacer |
| --- | --- |
| RF-17 | Configurar tarifas por tramo, impuestos, series, emisor, plantillas, dominio autorizado, plazos, recordatorios y umbrales de aprobación; validar y registrar cambios sin alterar facturas emitidas.  |
| RF-18 | Consultar y filtrar el historial de acciones relevantes con autor, fecha y cambios, sin poder reescribirlo.  |

**Aplicación y servicios colaboradores**

| ID | Quién colabora | Qué debe hacer |
| --- | --- | --- |
| RF-19 | Planificador de la aplicación | Generar la primera mensualidad proporcional, previsualizando el cálculo, y las siguientes el día 1 según la suscripción vigente, sin repetir aprobaciones ordinarias; mostrar en el calendario solo clientes autorizados.  |
| RF-20 | Servicio de correo | Enviar facturas y registrar destinatario, fecha y resultado; permitir reintentos sin crear otra factura y avisar al responsable ante fallos de entrega, sin inferir lectura del mensaje.  |
| RF-21 | Proveedor de cobros simulado | Consultar y recibir pagos simulados, asociándolos por coincidencia clara; actualizar el estado de cobro y remitir pagos ambiguos o con diferencias a revisión, conservando el movimiento justificativo.  |
| RF-22 | Planificador y servicio de correo | Enviar recordatorios según vencimiento pactado y cadencia configurada; detenerlos al cobrar. Permitir pausa por disputa con motivo y fecha de revisión y avisar al responsable de cobros, vencimientos y revisiones pendientes.  |
| RF-23 | API y sistema externo autorizado | Ofrecer una API mínima para consultar deuda y registrar solicitudes de baja, con permisos y las mismas reglas que la interfaz; documentar el contrato.  |

**Ojo:** el correo y el proveedor de cobros son colaboradores externos; el planificador es un mecanismo interno. El correo no inicia sesión ni valida el dominio.

## Requisitos no funcionales

| ID | Cómo debe ser |
| --- | --- |
| RNF-01 | **Rápida y sencilla:** operaciones frecuentes en pocos clics, con el objetivo orientativo de menos de un minuto; búsquedas fluidas y tareas pesadas sin bloquear la interfaz. Comprobarlo con usuarios y carga representativa.  |
| RNF-02 | **Responsive y accesible:** usable en móvil, tableta y ordenador, con navegadores actuales, teclado, etiquetas, contraste y zoom.  |
| RNF-03 | **Segura y respetuosa con los datos:** aplicar permisos en servidor, proteger contraseñas sin texto plano, cifrar comunicaciones, caducar sesiones y controlar descargas; definir conservación y anonimización sin invalidar documentos históricos.  |
| RNF-04 | **Fiable y trazable:** evitar duplicados en facturación, envíos y cobros; detectar conflictos de edición, conservar historial y recuperar automatismos tras fallos sin duplicar ni detener todo el proceso por un cliente.  |
| RNF-05 | **Escalable:** admitir miles de clientes, cientos de miles de facturas y crecimiento de usuarios sin rehacer el modelo ni cargar todo el histórico en el navegador.   |
| RNF-06 | **Mantenible y documentada:** documentar uso, reglas, modelo de datos, API, despliegue reproducible y restauración; mantener trazabilidad y separar integraciones y configuración del núcleo y sus secretos del repositorio.  |
| RNF-17 | **Recuperable:** realizar backups automáticos de datos y documentos con política definida y demostrar que pueden restaurarse.  |
| RNF-19 | **Exacta en sus cálculos:** usar precisión decimal y reglas documentadas de impuestos, prorrateo, redondeo y fechas de negocio; hacer coincidir los importes guardados, el PDF, los saldos y los informes.  |
| RNF-25 | **Verificable:** probar automáticamente reglas económicas, permisos, conciliación y generación sin duplicados, con escenarios de aceptación comprensibles para administración y datos ficticios separados de producción.  |

## Actores y criterios para los diagramas UML

- **Empleado operativo:** gestiona los clientes asignados, sus suscripciones, facturas y cobros según permisos.
- **Administrador:** opera sobre todos los clientes, gestiona usuarios/asignaciones, aprueba excepciones y consulta el panel global.
- **Responsable de configuración:** administrador con permiso adicional para ajustes y consulta de auditoría.
- **Servicio de correo, proveedor de cobros simulado y sistema externo autorizado por API:** colaboradores externos.

## **Los requisitos de negocio y las necesidades del cliente se concretan en las tablas anteriores. De forma resumida, los principales son:**

- **Negocio:** centralizar la gestión de clientes, facturas y cobros; facilitar el seguimiento de los pagos pendientes y evitar facturas o avisos duplicados.
- **Cliente (Turbine):** automatizar la facturación mensual y los recordatorios, permitir que cada empleado gestione sus clientes asignados y ofrecer al administrador una visión global y control sobre los usuarios.

## **RESUMEN PARA EL EQUIPO:**
AL HACER LOS REQUISITOS TRAS LOS APUNTES HECHOS EN LA CHARLA Y DE LA TRANSCRIPCIÓN, SALÍAN DEMASIADOS REQUISITOS NO TAN IMPORTANTES EN NUESTRA OPINIÓN Y HEMOS DECIDIDO PARA NO DISTRAERNOS HACER UN CONJUNTO DE REQUISITOS FUNCIONALES Y NO FUNCIONALES MÁS QUE CRÍTICOS E IMPORTANTES
LOS REQUISITOS SELECCIONADOS SON BASTANTE INTUITIVOS EN CASO DE CUALQUIER DUDA PONEDLO POR EL GRUPO.
LA PLANTILLA NO ESTÁ SEGUIDA A RAJATABLA YA QUE HEMOS CONSIDERADO UNA DIVISIÓN ALGO DIFERENTE QUE NOS PARECE MÁS CÓMODA.
