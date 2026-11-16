# Proyecto DevOps - Simulación de reservas médicas

## Descripción

Este proyecto consiste en una aplicación web estática que simula el proceso de solicitud de horas médicas para un centro de atención.

La interfaz está desarrollada utilizando HTML y CSS, y se ejecuta mediante un servidor web Nginx dentro de un contenedor Docker.

El proyecto tiene fines académicos y no realiza reservas médicas reales ni almacena información de pacientes.

## Tecnologías utilizadas

- **HTML5:** estructura y contenido de la interfaz.
- **CSS3:** estilos y presentación visual.
- **Nginx:** servidor web para entregar los archivos estáticos.
- **Docker:** construcción y ejecución de contenedores.
- **Docker Compose:** administración del servicio.
- **Git y GitHub:** control de versiones y almacenamiento del código fuente.

## Estructura del proyecto

```
proyecto-devops/
├── src/
│   ├── index.html
│   └── styles.css
├── Dockerfile
├── docker-compose.yml
├── .env.example
├── .gitignore
└── README.md
```

## Requisitos previos

Para ejecutar el proyecto se necesita:

- Windows, Linux o macOS.
- Docker Desktop instalado y funcionando.
- Docker Compose disponible desde la terminal.

## Instalación y ejecución

### 1. Obtener el proyecto

Clonar el repositorio desde GitHub:

```
git clone URL_DEL_REPOSITORIO
```

Ingresar a la carpeta del proyecto:

```
cd proyecto-devops
```

### 2. Configurar las variables de entorno

Crear una copia del archivo de ejemplo:

```
cp .env.example .env
```

En Windows PowerShell también se puede utilizar:

```
Copy-Item .env.example .env
```

El archivo `.env` contiene la configuración local del proyecto. Actualmente define el puerto en el que se publicará el servicio.

### 3. Construir e iniciar el servicio

Ejecutar:

```
docker compose up -d --build
```

Este comando construye la imagen a partir del Dockerfile y crea e inicia el contenedor en segundo plano.

### 4. Acceder a la aplicación

Abrir el navegador en la siguiente dirección:

```
http://localhost:8080
```

La aplicación será servida por Nginx desde el interior del contenedor.

## Comandos de administración

Consultar el estado del contenedor:

```
docker compose ps
```

Consultar los registros del servicio:

```
docker compose logs
```

Detener y eliminar el contenedor y la red del proyecto:

```
docker compose down
```

La imagen construida se conserva después de ejecutar `docker compose down`.

## Seguridad

Se consideran las siguientes medidas básicas:

- No publicar credenciales ni información sensible en el repositorio.
- Mantener el archivo `.env` excluido mediante `.gitignore`.
- Publicar únicamente `.env.example` como plantilla de configuración.
- Evitar incorporar datos personales o información real de pacientes.
- Utilizar datos ficticios durante las pruebas de la interfaz.

## Alcance del proyecto

La aplicación corresponde a una simulación visual de solicitud de horas médicas. No cuenta con una base de datos, autenticación de usuarios ni procesamiento real de reservas.

Su objetivo es demostrar la implementación de una aplicación web estática y su ejecución mediante tecnologías de contenerización.

## Autoría


|Diego Jara Carrasco |Proyecto académico desarrollado como parte de la evaluación de DevOps.|
|---|---|
