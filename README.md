# 🚀 Proyecto Docker para Entornos Locales

Este repositorio centraliza **stacks de Docker Compose** para levantar rápidamente servicios comunes de desarrollo.
La meta es que no tengas que instalar nada manualmente, solo levantar contenedores y empezar a trabajar.

---

## ✔ Requisitos
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) instalado y en ejecución.
- Conocimientos básicos de Docker (opcional, pero recomendable).

---

## ⚡ Uso Rápido
1. **Clona el repositorio**
    ```bash
    git clone https://github.com/Edro08/docker.git
    ```
2. Entra a la carpeta del servicio que quieras usar (por ejemplo database u open-webui).
3. Configura variables de entorno
   - Si existe un .env ajusta las variables según necesites.
4. Levanta el stack
    ```bash
    docker compose up -d
    ```
5. Detén el stack
    ```bash
    docker compose down
    ```
6. Ver logs en tiempo real
    ```bash
    docker compose logs -f
    ```

---

## 🐳 Stacks Disponibles

### 🔹 Database
Stack de bases de datos para desarrollo local.
- **Incluye:**
  - MySQL 8
  - PostgreSQL 16
- **Puertos expuestos:**
  - MySQL → `localhost:3306`
  - PostgreSQL → `localhost:5432`
- **Persistencia:** Los datos se almacenan en volúmenes de Docker y no se pierden al reiniciar contenedores.
- **Configuración:** Usuarios, contraseñas y nombres de base definidos en el archivo `.env`.

### 🔹 Open WebUI
Stack para experimentar con modelos de lenguaje mediante una interfaz web.
- **Incluye:**
  - Contenedor `open-webui`
  - PostgreSQL para almacenamiento de datos
- **Puerto expuesto:**
  - Open WebUI → `localhost:3000`
- **Persistencia:** Los datos se guardan en volúmenes para no perder la configuración.
- **Configuración:** Variables de entorno definidas en `.env`.

### 🔹 Keycloak
Stack para autenticación y gestión de identidades (SSO).
- **Incluye:**
  - Contenedor `Keycloak 26.3.5`
  - Base de datos `MySQL 8`
- **Puerto expuesto:**
  - Keycloak → `localhost:8080`
  - MySQL → `localhost:3306`
- **Persistencia:** Los datos de MySQL se almacenan en volumen Docker (mysql-data) y no se pierden al reiniciar contenedores.
- **Configuración:** Variables de entorno definidas en `.env`.
- **Uso previsto:** Pruebas de login, OAuth2 y gestión de usuarios en entornos locales.

---

## 🚨 **Avisos:**
- Este proyecto es para uso en entornos locales o de desarrollo. 
- No uses credenciales reales de producción. 
- Su uso en producción es bajo tu propia responsabilidad.

