#  App Música - Backend (API REST con Ktor)

Este repositorio contiene el código fuente del backend para una aplicación de gestión musical. Es una API RESTful desarrollada en **Kotlin** utilizando el framework **Ktor**, diseñada con una arquitectura limpia que separa los modelos de datos, la lógica de acceso (repositorios) y las rutas de la API.

##  Características Principales

* **Gestión de Artistas:** Endpoints para registrar, consultar y administrar información de artistas musicales.
* **Gestión de Álbumes:** Relación y administración de los álbumes pertenecientes a los artistas.
* **Gestión de Tracks (Pistas):** Control detallado de las canciones que componen cada álbum.
* **Seguridad y Serialización:** Configuración integrada para el manejo de JSON y directivas de seguridad para la API.
* **Patrón DTO:** Uso de *Data Transfer Objects* (DTOs) para aislar los modelos de la base de datos de los datos expuestos al cliente.

##  Tecnologías y Herramientas

* **Lenguaje:** [Kotlin](https://kotlinlang.org/)
* **Framework Backend:** [Ktor](https://ktor.io/)
* **Gestor de Dependencias y Construcción:** Gradle (Kotlin DSL)
* **Arquitectura:** Separación en capas (Rutas, Repositorios, DTOs, Modelos, Plugins).

## Estructura del Proyecto

El código fuente principal se encuentra en `src/main/kotlin/` y está organizado de la siguiente manera:

* `/models`: Contiene las entidades principales del dominio (`Artista.kt`, `Album.kt`, `Track.kt`).
* `/dtos`: Objetos de Transferencia de Datos utilizados para mapear las peticiones y respuestas HTTP.
* `/repositories`: Clases encargadas de encapsular la lógica de acceso y manipulación de la base de datos (`ArtistaRepository.kt`, etc.).
* `/routes`: Definición de los endpoints de la API REST para cada entidad.
* `/plugins`: Configuraciones clave del servidor Ktor, incluyendo:
  * `Routing.kt`: Enrutamiento global.
  * `Database.kt` / `DatabaseFactory.kt`: Conexión y configuración de la base de datos.
  * `Security.kt`: Capa de seguridad y autenticación.
  * `Serialization.kt`: Configuración para convertir objetos a JSON y viceversa.
* `Application.kt`: Punto de entrada principal donde se inicializa el servidor Ktor.

##  Requisitos Previos

Para ejecutar este proyecto en tu entorno local, necesitas:

1. Tener instalado el **Java Development Kit (JDK 11 o superior)**.
2. Un entorno de desarrollo como **IntelliJ IDEA** (recomendado para Kotlin/Ktor).
3. Una base de datos configurada (revisa `src/main/resources/application.conf` y `Database.kt` para las credenciales y el motor utilizado).

##  Cómo compilar y ejecutar

El proyecto utiliza el *Gradle Wrapper*, por lo que no necesitas tener Gradle instalado globalmente en tu sistema. Desde la terminal en la raíz del proyecto:

