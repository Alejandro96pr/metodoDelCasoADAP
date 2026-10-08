@startuml
"Usuario" as User
"Administrador" as Admin
"SuperAdmin" as Super
Admin --|> User
Admin <|-- Super
'Casos de Todos'
usecase "Iniciar Sesión"as CU01

'Casos de Usuario'
usecase "Gestionar Clientes" as CU02
usecase "Buscar Clientes" as CU03


'Casos de Administrador'
usecase "Crear Usuario" as CU0
usecase "Asignar Clientes a Usuario" as CU4
usecase "Ver panel Global" as CU1


'Casos de SuperAministrador'
usecase "Cambiar Ajustes y consultar Actividad" as CU2


User -- CU02
User -- CU03
User -- CU01

Admin -- CU0
Admin --CU4
Admin -- CU1

Super -- CU2


@enduml
