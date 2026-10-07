# Turbine · Resumen breve para el equipo


## ¿Qué aplicación nos piden?

Una **web interna**, independiente de Brain, para registrar clientes, emitir facturas y seguir cobros con poco trabajo manual. Debe funcionar bien en móvil y ordenador. Los clientes de Turbine reciben facturas y avisos, pero **no entran en la aplicación**. La aplicación **no cobra**: comprueba si se ha pagado. Para el proyecto se puede simular Stripe.

## Requisitos funcionales, agrupados por actor

**Personal de Turbine (todos los perfiles)**

| ID | Qué debe hacer |
| --- | --- |
| RF-01✅  | Iniciar sesión con correo corporativo y contraseña; **la aplicación** valida el dominio ( @turbineh.com). |

**Empleado operativo** (sobre sus clientes asignados; el administrador también puede hacerlo sobre todos)

| ID | Qué debe hacer |
| --- | --- |
| RF-02✅ | Dar de alta y editar empresas cliente, datos fiscales y contactos. |
| RF-04 | Buscar clientes por ubicación o sector y facturas por fecha, tipo o estado. |
| RF-05✅ | Crear facturas puntuales y suscripciones con una **factura nueva cada mes**. |
| RF-07✅ | Ajustar importes y actualizar el precio tras la revisión anual del tramo del cliente. |
| RF-08✅ | Generar y guardar el PDF con datos fiscales, IVA, numeración e imagen de Turbine. |
| RF-12✅ | Corregir manualmente un estado de cobro y registrar el cambio. |
| RF-13 | Registrar la solicitud de baja y parar nuevas mensualidades; completar la baja cuando no queden facturas pendientes, manteniendo entretanto su seguimiento. |

**Administrador**

| ID | Qué debe hacer |
| --- | --- |
| RF-03 | Crear usuarios y asignarles clientes concretos. |
| RF-14 | Ver un panel global de facturado, cobrado y pendiente (acceso a todos los clientes). |

**Responsable de configuración** (Superadministrador con permiso adicional)

| ID | Qué debe hacer |
| --- | --- |
| RF-15✅ | Cambiar ajustes generales, como el plazo de pago habitual de cinco días y demás funcionalidades exclusivas de dicho cargo. |

**Aplicación y servicios colaboradores**

| ID | Quién colabora | Qué debe hacer |
| --- | --- | --- |
| RF-06 | Calendario de la aplicación | Generar la primera mensualidad proporcional y las siguientes el día 1 y que en el calendario se muestre solo las empresas asociadas a cada uno, todas en caso de administrador y super. |
| RF-09✅ | Servicio de correo | Enviar la factura y registrar el resultado para tener resguardo de que se ha enviado la factura. |
| RF-10 | Proveedor de cobros simulado | Informar si la factura está pagada, pendiente o vencida. |
| RF-11 | Consulta al calendario y servicio de correo | Enviar recordatorios, detenerlos tras el cobro y avisar al responsable. |

**Ojo:** el servicio de correo **no inicia sesión ni valida el dominio**. Puede enviar correos de recuperación de contraseña si esa función se añade, pero la entrevista no la confirmó para esta entrega.

## Requisitos no funcionales

| ID | Cómo debe ser |
| --- | --- |
| RNF-01✅ | **Rápida y sencilla:** operaciones habituales en pocos clics; objetivo orientativo de menos de un minuto. |
| RNF-02✅ | **Responsive:** usable desde móvil, tableta y ordenador. |
| RNF-03✅ | **Segura:** proteger datos personales y fiscales y respetar los permisos por cliente. |
| RNF-04✅ | **Fiable:** evitar facturas o avisos duplicados y conservar un historial de cambios. |
| RNF-05✅ | **Escalable:** pasar de pocos clientes a miles sin rehacer el sistema. |
| RNF-06 | **Documentada:** facilitar su mantenimiento y la futura integración real con pagos. |

## Actores y casos de uso del UML

- **Empleado operativo** (mejor nombre que «lector»): gestiona los clientes que tiene asignados, sus facturas y cobros. La aclaración final del cliente le permite **crear y editar**, además de consultar.
- **Administrador:** hace lo mismo con todos los clientes, gestiona usuarios y asignaciones, y ve el panel global.
- **Responsable de configuración:** administrador con permiso adicional para ajustes generales y consulta de actividad.
- **Servicio de correo y proveedor de cobros simulado:** sistemas externos para enviar avisos y comprobar pagos.

En el diagrama, agruparía los casos de uso en: **gestionar clientes, gestionar usuarios y asignaciones, emitir facturas, consultar facturas, enviar facturas, comprobar cobros, gestionar recordatorios, tramitar bajas, consultar panel y configurar el sistema**. El cliente de Turbine no necesita un actor con acceso a la web: recibe comunicaciones fuera de ella.

## Cuatro aclaraciones que conviene recordar

1. **Brain queda fuera del proyecto.** Esta es una aplicación administrativa separada.
2. **«Lector o Empleado operativo» no significa solo lectura.** Puede modificar lo que tenga asignado.
3. **Baja y deuda son cosas distintas.** Se dejan de generar facturas nuevas, pero se siguen las pendientes.
4. **Stripe real, WhatsApp, importación CSV y API externa** pueden quedar como ampliaciones. Para la entrega, basta demostrar bien el flujo principal con un simulador de cobros.

**Pendiente de confirmar:** calendario definitivo de recordatorios, reglas de precios y cómo corregir una factura ya emitida. La transcripción contiene respuestas contradictorias; este resumen sigue las aclaraciones finales del cliente.
