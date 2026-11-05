# Diagrama de Arquitectura y Componentes (Turbine)

---

## 1. Introducción y Sintaxis en PlantUML

A continuación, se detalla la arquitectura lógica del sistema mediante el diagrama de componentes. 

En lugar de recurrir a flechas de dependencia genéricas, se ha implementado de forma estricta la notación estándar de **interfaces requeridas y proporcionadas** (*lollipop / socket*):

* ** Interfaz Requerida (semicírculo / enchufe):** Representa la necesidad de un componente; indica que este módulo solicita datos o invoca servicios de otro para poder completar su flujo.
* ** Interfaz Proporcionada (círculo / piruleta):** Define el contrato público o servicio que un componente expone hacia el resto del sistema.

> **Sintaxis PlantUML:** Para unir la interfaz requerida con la proporcionada en un único enlace directo y limpio, se utilizó la notación `-(0-`, posicionando la etiqueta del contrato en el punto exacto de integración.

---

## 2. Estructura de Paquetes y Conexiones Base

La arquitectura se articula en **cuatro paquetes desacoplados** con responsabilidades bien delimitadas:

### Paquete de Gestión de Clientes
* **`Interfaz Web` (Capa de Presentación):** Constituye el punto de acceso de los usuarios. Al ser puramente consumidora, únicamente declara interfaces requeridas:
  * `IAuth` $\rightarrow$ Solicita validación corporativa de acceso.
  * `IUser` $\rightarrow$ Consulta permisos y perfiles de usuario.
  * `IClientes` $\rightarrow$ Interactúa con la lógica de negocio y expedientes de empresas.
  * `IAuditoria` $\rightarrow$ Canaliza la supervisión y trazabilidad del sistema.
* **`Módulo de Gestión de Clientes`:** Actúa como orquestador de negocio. Coordina la operativa comercial requiriendo la interfaz `IFacturación`, despacha avisos mediante `INotificaciones` y almacena los datos de los clientes mediante `IDatabase`.

### Paquete de Facturación
* Centraliza las reglas de negocio contables, emisión de cobros y estados de facturación, operando completamente desacoplado de la interfaz visual directa.

### Paquete de Notificaciones e Integración
* Agrupa el motor asíncrono de comunicaciones del sistema y los enlaces con colaboradores y pasarelas externas.

### Paquete de Persistencia
* En la base del sistema, el componente **`Base de Datos`** expone de forma compartida la interfaz `IDatabase`. A ella se conectan como clientes demandantes *Gestión de Clientes*, *Facturación* y *Notificaciones*, garantizando la persistencia transaccional y la integridad referencial.

---

## 3. Mejoras Incorporadas y Lógica de Negocio de Turbine

Tomando como punto de partida el esquema base planteado en clase, se incorporaron piezas clave para que el modelo responda fielmente a las especificaciones y casos de uso consolidados en la primera entrega:

### Ampliación en Facturación
* **`Generador de PDF` (`IPDF`):** En Turbine, la emisión de una factura exige por normativa de negocio congelar y archivar un resguardo oficial en **PDF inmutable**, impidiendo alteraciones posteriores.
* **`Planificador interno` (`IProgramador`):** Mecanismo desatendido en segundo plano encargado de calcular la **parte proporcional** (*prorrateo*) del primer mes si el alta es a mitad de ciclo, automatizando además la emisión regular cada día 1 de mes.

### Ampliación en Notificaciones e Integración (Colaboradores Externos)
* **`Servicio de Correo` (`IMailService`):** Gestiona la cola de envíos y la política de reintentos automáticos para facturas emitidas y recordatorios de vencimiento.
* **`Simulador de Pagos / Stripe` (`IPagos`):** Refleja la arquitectura real del sistema: Turbine **no procesa cobros directos**, sino que consulta y concilia en segundo plano si un pago ha sido liquidado para detener las alertas de cobro.

### Seguridad y Trazabilidad Global
* **`Módulo de Auditoría` (`IAuditoria`):** Conectado directamente a la base de datos, cumple el requisito crítico del rol *SuperAdmin* de disponer de un registro histórico inmutable con autor, acción y fecha exacta, evitando modificaciones o borrados silenciosos.
