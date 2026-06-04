# Sistema Académico Automatizado con n8n y SQL Server

## Descripción

Este proyecto consiste en una aplicación web académica desarrollada utilizando HTML, Bootstrap y JavaScript para la interfaz de usuario. La lógica de negocio fue implementada mediante workflows en n8n, utilizando Webhooks para la comunicación entre la aplicación y la base de datos.

El sistema permite la gestión de tareas académicas mediante dos tipos de usuarios: docentes y estudiantes.

---

# Instalación

## 1. Instalación de Docker Desktop

Clonar el repositorio oficial de n8n:

```bash
git clone https://github.com/n8n-io/self-hosted-ai-starter-kit.git
cd self-hosted-ai-starter-kit
cp .env.example .env
```

Configurar las variables necesarias dentro del archivo `.env`.

---

## 2. Iniciar los contenedores

Ejecutar Docker Desktop y levantar los servicios correspondientes.

El contenedor incluye:

* n8n
* PostgreSQL
* Ollama

Para este proyecto únicamente se utilizó n8n.

---

## 3. Instalar Microsoft SQL Server

Descargar SQL Server desde el sitio oficial:

https://www.microsoft.com/es-es/sql-server/sql-server-downloads

Instalar SQL Server y SQL Server Management Studio (SSMS).

---

## 4. Crear la base de datos

Ejecutar el script SQL incluido en el repositorio para crear:

* Usuarios
* Estudiantes
* Docentes
* Cursos
* Tareas
* Entregas
* Calificaciones
* Auditoría

---

## 5. Ejecutar la aplicación

Abrir el archivo:

```text
index.html
```

e iniciar sesión con los usuarios registrados en la base de datos.

---

# Tecnologías Utilizadas

* HTML5
* CSS3
* Bootstrap 5
* JavaScript
* SQL Server
* n8n
* REST API
* Webhooks

---

# Funcionalidades

## Módulo de Autenticación

* Inicio de sesión para docentes y estudiantes.
* Validación de credenciales en SQL Server.
* Redirección según el rol.

## Módulo Docente

* Crear tareas.
* Visualizar entregas.
* Calificar tareas.
* Consultar tareas activas.

## Módulo Estudiante

* Consultar tareas disponibles.
* Registrar entregas.
* Visualizar estado de tareas.
* Consultar calificaciones.

---

# Arquitectura del Sistema

```text
Frontend Web
(HTML + Bootstrap + JavaScript)
            |
            v
      Webhooks n8n
            |
            v
      Workflows n8n
            |
            v
        SQL Server
```

---

# Estructura del Proyecto

```text
Proyecto
│
├── index.html
├── dashboard-docente.html
├── dashboard-estudiante.html
├── subir-tarea.html
├── tareas-docente.html
├── calificar-tareas.html
│
├── workflows-n8n
│   ├── login
│   ├── dashboard-docente
│   ├── dashboard-estudiante
│   ├── crear-tarea
│   ├── tareas-activas
│   ├── recepcion-tarea
│   └── calificacion
│
└── scripts-sql
```

---

# Flujo Principal

## Inicio de Sesión

1. El usuario ingresa sus credenciales.
2. El frontend envía la información al webhook.
3. n8n valida las credenciales.
4. SQL Server devuelve la información del usuario.
5. Se redirige al dashboard correspondiente.

## Entrega de Tareas

1. El estudiante selecciona una tarea.
2. Se envían los datos al webhook.
3. n8n valida que la entrega no exista.
4. Se registra la entrega en SQL Server.
5. El sistema responde con éxito o error.

## Calificación

1. El docente consulta entregas.
2. Selecciona una entrega.
3. Registra una nota.
4. SQL Server almacena la calificación.
5. El estudiante puede visualizar el resultado.

---

# Seguridad Implementada

* Validación de credenciales.
* Control de acceso por roles.
* Prevención de entregas duplicadas.
* Registro de auditoría.
* Validación de entradas mediante workflows.

---

# Mejoras Futuras

* Carga real de archivos PDF.
* Recuperación de contraseña.
* Administración completa de usuarios.
* Gestión avanzada de cursos.
* Reportes académicos.
* Panel administrativo.

---

# Autor

David Carrera

Proyecto académico desarrollado utilizando n8n, SQL Server y tecnologías web para la automatización de procesos académicos.

