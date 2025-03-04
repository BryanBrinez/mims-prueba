# mims-prueba

## Objetivo
Evaluar el desarrollo de microservicios utilizando NestJS, manejo de bases de datos, contenedores con Docker, y la implementación de soluciones backend.

## Descripción del Proyecto
### Sistema de Gestión de Pedidos
Esta API permite gestionar pedidos en un e-commerce utilizando una arquitectura basada en microservicios. Incluye las siguientes funcionalidades:

### Microservicio de Autenticación (`auth-ms`)
- Registro de usuario (nombre, email, contraseña hasheada).
- Autenticación con JWT.
- Obtención de la información del usuario autenticado.

### Microservicio de Pedidos (`orders-ms`)
- Creación de pedidos asociados a un usuario.
- Listado de pedidos por usuario.
- Actualización del estado de un pedido (pendiente, en proceso, completado).

### Gateway (`gateway`)
- Actúa como punto de entrada para la comunicación con los microservicios.
- Manejo de autenticación y autorización.

## Requerimientos Técnicos
- **NestJS**: Framework utilizado para la implementación de los microservicios.
- **Base de Datos**: PostgreSQL, manejado con Prisma.
- **Mensajería**: Comunicación entre microservicios mediante NATS.
- **Docker**: Configuración del proyecto para su ejecución en contenedores con `docker-compose`.
- **Documentación**: API documentada con Swagger.

## Instalación y Ejecución
### Prerrequisitos
- Tener instalado [Docker](https://www.docker.com/) y asegurarse de que el servicio está en ejecución.
- Clonar el repositorio incluyendo los submódulos:
  ```sh
  git clone --recurse-submodules https://github.com/BryanBrinez/mims-prueba
  ```
- Acceder al directorio del proyecto:
  ```sh
  cd mims-prueba
  ```

### Levantar los servicios con Docker Compose
Ejecuta el siguiente comando para iniciar todos los microservicios junto con la base de datos:
```sh
docker-compose up --build
```
Esto levantará los contenedores de `auth-ms`, `orders-ms`, `gateway`, PostgreSQL y NATS.

### Acceder a la API
- **Gateway**: [http://localhost:3000](http://localhost:3000)
- **Documentación Swagger**: [http://localhost:3000/docs](http://localhost:3000/docs)

### Apagar los servicios
Para detener los contenedores, ejecuta:
```sh
docker-compose down
```

## Estructura del Proyecto
```
/mims-prueba
│── auth-ms/        # Microservicio de autenticación
│── orders-ms/      # Microservicio de pedidos
│── gateway/        # API Gateway
│── docker-compose.yml  # Configuración para levantar los servicios
│── README.md       # Instrucciones del proyecto
```

## Entrega
- Enlace al repositorio en GitHub/GitLab.
- Archivo `README.md` con instrucciones de instalación y ejecución.

