# microservices-orchestrator

Este repositorio contiene la orquestación de un sistema basado en microservicios que incluye un frontend y dos servicios
principales: `user-service` y `post-service`. El objetivo del proyecto es ofrecer una arquitectura desacoplada y
modular, permitiendo el despliegue y desarrollo independiente de cada componente.

## 🧱 Estructura del repositorio

```
microservices-orchestrator/
│
├── frontend/ # Aplicación frontend (React + Tailwind + Vite)
├── user-service/ # Servicio de usuarios (Node.js + TypeScript)
├── post-service/ # Servicio de posts (Java + Spring Boot)
├── docker-compose.yml
└── .gitmodules # Configuración de los submódulos
```

## 🚀 Cómo ejecutar el proyecto

### 1. Clonar el repositorio

Este repositorio utiliza submódulos para los servicios y el frontend. Asegúrate de clonarlo con la opción `--recursive`:

```bash
git clone --recursive https://github.com/TFG-maria/microservices-orchestrator.git
```

Si ya has clonado el repo sin `--recursive`, puedes inicializar y actualizar los submódulos con:

```bash
git submodule update --init --recursive
```

### 2. Levantar los servicios

Este proyecto está orquestado con Docker Compose. Para iniciar todos los servicios:

```bash
docker-compose up --build
```

Esto levantará:

- El frontend accesible en http://localhost:5173

- El servicio de usuarios (user-service) en http://localhost:3001

- El servicio de posts (post-service) en http://localhost:8080

> Asegúrate de tener Docker y Docker Compose instalados.

## 📦 Comandos útiles por subrepositorio

### 🔧 user-service (Node.js + Express)

Ubicación: `./user-service`

Instalación local:

```bash
npm install
```

Ejecución local:

```bash
npm run dev
```

Build:

```bash
npm run build
```

### 📰 post-service (Java + Spring Boot)

Ubicación: `./post-service`

Build y ejecución:

```bash
./mvnw spring-boot:run
```

O bien con Docker:

```bash
docker build -t post-service .
docker run -p 8080:8080 post-service
```

### 🌐 frontend (React + Vite)

Ubicación: `./frontend`

Instalación local:

```bash
npm install
```

Ejecución local:

```bash
npm run dev
```

Build de producción:

```bash
npm run build
```

## 🛠️ Notas

- Cada servicio tiene su propio README.md con información más detallada sobre endpoints, dependencias y estructura
  interna.

- Este proyecto está pensado para usarse tanto en desarrollo como en producción gracias al uso de Docker.

- Para producción puedes usar plataformas como Railway, Netlify o servicios en la nube con soporte para contenedores como Azure.

## 📄 Licencia

Este proyecto está licenciado bajo los términos del archivo LICENSE de cada submódulo.

