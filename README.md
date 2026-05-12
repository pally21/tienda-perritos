<<<<<<< HEAD
# Tienda de Alimentos para Perritos 🐶

Aplicación de ejemplo en 3 capas usando Docker y Docker Compose:

- Frontend: HTML + JavaScript (Nginx)
- Backend: Node.js + Express
- Base de datos: MySQL

## Requisitos

- Docker Desktop instalado

## Estructura del proyecto

```text
.
├── docker-compose.yml
├── frontend
│   ├── Dockerfile
│   ├── index.html
│   └── app.js
├── backend
│   ├── Dockerfile
│   ├── package.json
│   └── server.js
└── db
    └── init.sql
```

## Cómo ejecutar

1. Abrir una terminal en la carpeta del proyecto
2. Ejecutar:

```bash
docker compose build
docker compose up -d
```

3. Abrir en el navegador:

- Frontend: http://localhost:8080
- Backend (API): http://localhost:3001/api/productos

4. Para detener los contenedores:

```bash
docker compose down
```

## Notas

- La base de datos se inicializa automáticamente con el script `db/init.sql` en el primer arranque.
- Puedes modificar el frontend y backend, reconstruir y volver a levantar los contenedores.
=======
# 🐶 Tienda de Alimentos para Perritos

**ISY1101 - Introducción a Herramientas DevOps | DuocUC 2025**

## Descripción
CRUD de productos con pipeline CI/CD completo: Docker + GitHub Actions + Amazon ECR + AWS EC2.

## Estructura
├── frontend/   → Nginx + HTML/JS
├── backend/    → Node.js + Express + MySQL2
├── db/         → MySQL 8
├── docker-compose.yml
└── .github/workflows/   → 3 pipelines CI/CD
## Ejecución local
```bash
docker-compose up --build
# Abrir http://localhost
```

## Pipeline CI/CD
Se activa con push a la rama **deploy**:
1. Build imagen Docker
2. Push a Amazon ECR
3. Deploy automático en EC2 vía AWS SSM

## Secrets requeridos en GitHub
| Secret | Descripción |
|--------|-------------|
| AWS_ACCESS_KEY_ID | Credencial AWS |
| AWS_SECRET_ACCESS_KEY | Credencial AWS |
| AWS_SESSION_TOKEN | Token sesión |
| AWS_REGION | Ej: us-east-1 |
| ECR_REGISTRY | URL base ECR |
| ECR_REPO_URL_FRONTEND | URL repo frontend |
| ECR_REPO_URL_BACKEND | URL repo backend |
| ECR_REPO_URL_DB | URL repo database |
| EC2_FRONTEND_INSTANCE_ID | ID instancia frontend |
| EC2_BACKEND_INSTANCE_ID | ID instancia backend |
| EC2_DB_INSTANCE_ID | ID instancia database |
| EC2_DB_PRIVATE_IP | IP privada EC2 DB |

## Autores
- [Tu nombre] - [Tu RUT]
- [Nombre compañero] - [RUT]
>>>>>>> 8c14f5bdcdcf24325a9e813f62dc1fd9b380a3b1
# deploy
