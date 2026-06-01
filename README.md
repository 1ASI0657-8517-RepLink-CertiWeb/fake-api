# RepLink Fake API

Una API REST simulada basada en **JSON Server** para el proyecto CertiWeb. Proporciona datos de usuarios, reservas de autos e información de vehículos para desarrollo y pruebas.

---

## Tabla de Contenidos

- [Descripción General](#descripción-general)
- [Instalación Local](#instalación-local)
- [Despliegue en Render](#despliegue-en-render)
- [Estructura de Datos](#estructura-de-datos)
- [Endpoints Disponibles](#endpoints-disponibles)
- [Ejemplos de Uso](#ejemplos-de-uso)

---

## Descripción General

Esta es una fake API basada en [JSON Server](https://github.com/typicode/json-server) que simula un backend REST para la aplicación CertiWeb. Permite realizar operaciones CRUD (Create, Read, Update, Delete) sobre datos de:

- **Usuarios**: Información de clientes registrados
- **Reservaciones**: Registro de reservas de vehículos
- **Administradores**: Credenciales de administrador
- **Autos**: Catálogo de vehículos disponibles

---

## Estructura de Datos

### Users (Usuarios)
```json
{
  "id": 1,
  "name": "Carlos Rodriguez",
  "email": "dd@gmail.com",
  "password": "dddd",
  "plan": "Anual"
}
```

**Campos disponibles**: `id`, `name`, `email`, `password`, `plan`

---

### Reservations (Reservas)
```json
{
  "id": 1,
  "userId": 2,
  "reservationName": "Fernando Gago",
  "reservationEmail": "xahid43956@uforks.com",
  "imageUrl": "https://i.ibb.co/3mQ08Tyb/nissan3.jpg",
  "brand": "nissan",
  "model": "Kicks Play",
  "licensePlate": "2A4-GH2",
  "inspectionDateTime": "2025-05-16T16:00:00.000Z",
  "price": "1000",
  "status": "accepted"
}
```

**Campos disponibles**: `id`, `userId`, `reservationName`, `reservationEmail`, `imageUrl`, `brand`, `model`, `licensePlate`, `inspectionDateTime`, `price`, `status`

**Estados válidos**: `pending`, `accepted`, `rejected`

---

### Admin User (Administrador)
```json
{
  "id": 1,
  "name": "admin",
  "email": "adminEMAIL@gmail.com",
  "password": "admin"
}
```

**Campos disponibles**: `id`, `name`, `email`, `password`

---

### Cars (Autos)
```json
{
  "id": 1,
  "title": "tOYOTA",
  "owner": "Fernando Gago",
  "ownerEmail": "xahid43956@uforks.com",
  "year": 2022,
  "brand": "nissan",
  "model": "Kicks Play",
  "description": "veraniooooooooooooo",
  "pdfCertification": "",
  "imageUrl": "https://i.ibb.co/3mQ08Tyb/nissan3.jpg",
  "price": "1000",
  "licensePlate": "2A4-GH2",
  "originalReservationId": 1
}
```

**Campos disponibles**: `id`, `title`, `owner`, `ownerEmail`, `year`, `brand`, `model`, `description`, `pdfCertification`, `imageUrl`, `price`, `licensePlate`, `originalReservationId`

---

## Endpoints Disponibles

### Users (Usuarios)
| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | `/api/v1/users` | Obtener todos los usuarios |
| GET | `/api/v1/users/:id` | Obtener un usuario por ID |
| POST | `/api/v1/users` | Crear un nuevo usuario |
| PUT | `/api/v1/users/:id` | Actualizar un usuario |
| PATCH | `/api/v1/users/:id` | Actualización parcial de usuario |
| DELETE | `/api/v1/users/:id` | Eliminar un usuario |

### Reservations (Reservas)
| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | `/api/v1/reservations` | Obtener todas las reservas |
| GET | `/api/v1/reservations/:id` | Obtener una reserva por ID |
| POST | `/api/v1/reservations` | Crear una nueva reserva |
| PUT | `/api/v1/reservations/:id` | Actualizar una reserva |
| PATCH | `/api/v1/reservations/:id` | Actualización parcial de reserva |
| DELETE | `/api/v1/reservations/:id` | Eliminar una reserva |

### Admin User (Administrador)
| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | `/api/v1/admin_user` | Obtener información del admin |
| GET | `/api/v1/admin_user/:id` | Obtener admin por ID |
| PUT | `/api/v1/admin_user/:id` | Actualizar información del admin |

### Cars (Autos)
| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | `/api/v1/cars` | Obtener todos los autos |
| GET | `/api/v1/cars/:id` | Obtener un auto por ID |
| POST | `/api/v1/cars` | Crear un nuevo auto |
| PUT | `/api/v1/cars/:id` | Actualizar un auto |
| DELETE | `/api/v1/cars/:id` | Eliminar un auto |

---

## Parámetros de Query

JSON Server soporta varios parámetros de query útiles:

**Búsqueda/Filtrado**
```
GET /api/v1/users?name=Carlos
GET /api/v1/reservations?status=accepted&userId=2
```

**Paginación**
```
GET /api/v1/users?_page=1&_limit=10
```

**Ordenamiento**
```
GET /api/v1/reservations?_sort=price&_order=desc
```

**Búsqueda de rango**
```
GET /api/v1/reservations?price_gte=1000&price_lte=2000
```

---

## Importante

- Esta es una **API simulada** para desarrollo y pruebas
- Los datos se resetean cada vez que se reinicia el servidor
- Para producción, considera usar una base de datos real como MongoDB, PostgreSQL, etc.
- Esta API no tiene autenticación implementada por defecto
- Los datos en `db.json` son datos de prueba/demostración

---

## Recursos Adicionales

- [JSON Server Documentación](https://github.com/typicode/json-server)
- [Render Documentación](https://render.com/docs)
- [HTTP Methods](https://developer.mozilla.org/es/docs/Web/HTTP/Methods)

---

**Última actualización**: Junio 2026  
**Versión**: 1.0.0

