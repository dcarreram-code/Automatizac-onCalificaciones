# Automatizac-onCalificaciones
En este proyecto se desarrollo una aplicacion web por medio de httml, en la cual toda su logica fue trabajada dentro de n8n, usando webnoks y scrips conectados a una base de datos trabajada en microsoft sql server


************************Pasos de Instalación**************************** 

1)Instalacion de docker Desktop por medio de consola usando el linck oficial subido a github

git clone https://github.com/n8n-io/self-hosted-ai-starter-kit.git
cd self-hosted-ai-starter-kit
cp .env.example .env # you should update secrets and passwords inside

2) Luego de haber instalado el n8n de manera local  podremos iniciar el contenedor el cual contiene el n8n, ollama y postgre sql, de los cuales solamente usamos n8n de manera local

3) Instalamos microsoft sql server usando la version gratuita proporcionada por Microsoft

   https://www.microsoft.com/es-es/sql-server/sql-server-downloads

4) luego de tener instalada sql server tomamos El script de nuestra base de datos y lo ejecutamos en ella

5) Despues iniciamos nuestro programa y tendriamos listo todo

Tecnologías utilizadas
HTML5
CSS3
Bootstrap 5
JavaScript
SQL Server
n8n
REST API (Webhooks)
Funcionalidades
Módulo de autenticación
Inicio de sesión para docentes y estudiantes.
Validación de credenciales almacenadas en SQL Server.
Redirección automática según el rol del usuario.
Módulo de docentes
Visualización del dashboard docente.
Creación de nuevas tareas.
Consulta de entregas realizadas por estudiantes.
Registro de calificaciones.
Gestión de tareas activas.
Módulo de estudiantes
Visualización del dashboard estudiantil.
Consulta de tareas disponibles.
Registro de entregas.
Visualización de estado de tareas.
Consulta de notas obtenidas.
Automatización con n8n
Validación de usuarios.
Consulta de información académica.
Registro de tareas.
Registro de entregas.
Registro de calificaciones.
Generación de respuestas mediante Webhooks.
Estructura del proyecto
Proyecto/
│
├── index.html
├── dashboard-docente.html
├── dashboard-estudiante.html
├── subir-tarea.html
├── tareas-docente.html
├── calificar-tareas.html
│
├── workflows-n8n/
│   ├── login
│   ├── dashboard-docente
│   ├── dashboard-estudiante
│   ├── crear-tarea
│   ├── tareas-activas
│   ├── recepcion-tarea
│   └── calificacion
│
└── Base de Datos SQL Server
Base de Datos

El sistema utiliza SQL Server para almacenar la información académica.

Tablas principales
Usuarios
Estudiantes
Docentes
Cursos
Tareas
Entregas
Calificaciones
Auditoria
Flujo general del sistema
Inicio de sesión
El usuario ingresa sus credenciales.
El frontend envía la información al webhook de login.
n8n valida las credenciales en SQL Server.
Se devuelve el rol del usuario.
El sistema redirige al dashboard correspondiente.
Publicación de tareas
El docente registra una nueva tarea.
La información se almacena en SQL Server.
La tarea queda disponible para los estudiantes.
Entrega de tareas
El estudiante selecciona una tarea activa.
Se valida que no exista una entrega previa.
Se registra la entrega en la base de datos.
Se actualiza el dashboard del estudiante.
Calificación
El docente consulta las entregas registradas.
Asigna una calificación.
La nota queda almacenada en SQL Server.
El estudiante puede visualizar el resultado.
Seguridad implementada
Validación de usuarios mediante credenciales.
Separación de funcionalidades por rol.
Validación de entregas duplicadas.
Restricciones de acceso mediante autenticación.
Registro de acciones mediante auditoría.
Mejoras futuras
Carga real de archivos PDF.
Recuperación de contraseña.
Gestión completa de cursos.
Administración de usuarios desde la interfaz.
Reportes académicos.
Panel administrativo.
Autor

David Carrera
   
