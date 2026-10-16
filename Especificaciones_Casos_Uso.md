Especificación de Casos de Uso

# CU01: Iniciar Sesión (CU01 ..> CU01_Val : <include>)
- **Objetivo:** Autenticar al usuario interno comprobando que su correo es válido.
- **Actores:** Usuario, Administrador, SuperAdmin .
- **Precondiciones:** El actor no tiene sesión activa y su cuenta existe.
- **Flujo principal:**
  1. El actor introduce sus credenciales.
  2. El sistema valida la clave y abre la sesión.
- **Flujos alternativos:** Petición de recuperación de clave (llama a `CU02`).
- **Flujos de excepción:** Credenciales incorrectas, bloqueo por intentos fallidos. Si falla 3 veces, bloquea la cuenta.
- **Postcondiciones:** El actor accede a su cuenta.
---

# CU02: Recuperar contraseña
- **Objetivo:** Restablecer la clave de acceso.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Precondiciones:** El actor dispone de una cuenta.
- **Flujo principal:**
  1. El actor solicita recuperar su clave introduciendo su correo corporativo.
  2. El sistema envía un enlace único con tiempo de caducidad al email.
  3. El actor introduce la nueva clave y el sistema la guarda cifrada.
- **Flujos de excepción:** Enlace caducado.
- **Postcondiciones:** Contraseña actualizada.
---

# CU03: Gestionar Empresas
- **Objetivo:** Registrar o modificar la información y los contactos de las empresas clientes.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Flujo principal:**
  1. El actor rellena o modifica los datos de la empresa (nombre, NIF, dirección) y añade o actualiza a sus personas de contacto.
  2. El sistema comprueba que no haya otra empresa repetida y guarda los cambios.
- **Flujos alternativos:** Desactivar a un contacto antiguo, recuperar un cliente del pasado, revisar su tarifa (`CU06`) o darle de baja (`CU09`).
- **Postcondiciones:** La ficha de la empresa queda guardada y actualizada.

# CU04: Buscar Clientes y Facturas
- **Objetivo:** Encontrar clientes o facturas con el buscador y los filtros.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Flujo principal:**
  1. El actor introduce un término (nombre, contacto, correo o número de factura) y aplica filtros (sector, ubicación, estado, fechas).
  2. El sistema devuelve los registros que el actor tiene permiso para ver.
- **Postcondiciones:** Se muestra la información solicitada[cite: 6].
---

# CU05: Preparar y Emitir facturas (CU05 ..> CU07 : <include>)
- **Objetivo:** Crear facturas (puntuales o recurrentes), emitirlas con numeración única y enviarlas al cliente.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Flujo principal:**
  1. El actor redacta el borrador (cantidad, precio, impuesto) y revisa la vista previa.
  2. El actor confirma la emisión y el sistema asigna serie y número único.
  3. El sistema genera el PDF (`CU07`), lo envía  y programa los recordatorios de cobro.
- **Flujos de excepción:** Bloqueo si faltan datos o el periodo está cerrado o si el envío falla.
- **Postcondiciones:** Factura emitida oficialmente, PDF almacenado y envío registrado.
---

# CU06: Revisión anual de tramo (extiende a CU03)
- **Objetivo:** Revisar la facturación anual de un cliente para proponer una nueva tarifa anual.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Precondiciones:** Pasa un año completo desde la última revisión.
- **Flujo principal:**
  1. El actor introduce o el sistema recopila la facturación anual del cliente indicando fuente y fecha.
  2. El sistema consulta la tabla de tarifas vigente y propone el nuevo tramo.
  3. La propuesta pasa a validación humana (`CU16`) indicando la fecha de entrada en vigor.
- **Postcondiciones:** Tarifa actualizada para futuras emisiones.
---

# CU07: Generar PDF de la factura (incluido en CU05)
- **Objetivo:** Maquetar y conservar de forma inmutable el documento PDF oficial de la factura emitida.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Flujo principal:**
  1. El sistema crea y guarda el PDF de la factura con el diseño actual, asegurando que nunca se modifique aunque la empresa cambie su logo en el futuro.
- **Postcondiciones:** Documento PDF accesible y protegido.
---

# CU08: Conciliar y Corregir estado de cobros
- **Objetivo:** Asociar pagos recibidos con facturas emitidas.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Precondiciones:** Existen facturas pendientes.
- **Flujo principal:**
  1. El sistema busca a qué factura corresponde cada pago recibido y, si no lo tiene claro, le pide al usuario que lo asigne manualmente.
- **Postcondiciones:** Estado de la factura y saldo del cliente actualizados y trazados.
---

# CU09: Registrar y Aplicar Baja Efectiva (extiende a CU03)
- **Objetivo:** Dar de baja a un cliente para no cobrarle más meses, pero manteniendo el control de lo que aún debe.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Precondiciones:** El cliente tiene una suscripción activa.
- **Flujo principal:**
  1. El actor indica la solicitud de baja del cliente y su fecha.
  2. El sistema frena la creación de facturas nuevas a partir de ese día.
- **Flujos alternativos:** Si el cliente tiene facturas sin pagar, el sistema le seguirá enviando recordatorios para intentar cobrarlas.
- **Postcondiciones:** El cliente queda dado de baja manteniendo su historial intacto.
---

# CU10: Generar Suscripciones y Estados
- **Objetivo:** Configurar la suscripción de un cliente y sus condiciones de pago.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Precondiciones:** La empresa cliente ya está registrada.
- **Flujo principal:**
  1. El actor configura los datos de la suscripción (plan, tarifa, fecha de inicio) y el sistema calcula el cobro proporcional si empieza a mitad de mes.
  2. El sistema activa la suscripción para generar las facturas automáticamente el día uno de cada mes.
- **Flujos alternativos:** Pausar la suscripción temporalmente o poner una fecha de inicio para el futuro.
- **Postcondiciones:** Suscripción lista para facturar de forma automática.
---

# CU11: Consultar e Importar/Exportar Informes
- **Objetivo:** Descargar informes, exportar datos o cargar facturas antiguas.
- **Actores:** Usuario, Administrador, SuperAdmin.
- **Flujo principal:**
  1. El actor filtra los datos que necesita y solicita descargar el informe.
  2. El sistema crea el archivo (mostrando solo lo que ese usuario tiene permitido ver) y guarda un registro de la descarga.
- **Postcondiciones:** El archivo se genera y queda registrado quién lo descargó.
---
