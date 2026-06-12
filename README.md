# Gestor de Tareas

Backend desarrollado usando **Node.js** y **Express** para crear un CRUD de tareas.
La informacion se guarda en un archivo JSON

---

## Descripcion

La API permite manejar una lista de tareas usando distintos métodos HTTP:

* `GET` para obtener datos
* `POST` para crear una tarea
* `PUT` para actualizar una tarea completa
* `PATCH` para actualizar solo algunos campos
* `DELETE` para remover una tarea

---

## Requisitos

Antes de ejecutar el proyecto, es necesario tener instalado:

```bash
Node.js
npm
```

---

## Instalacion de dependencias

Desde la carpeta principal del proyecto, ejecutar:

```bash
npm install
```

---

## Inicio del servidor

Para inciar el servidor en modo desarrollo:

```bash
npm run dev
```

El servidor se ejecuta en:

```text
http://localhost:3000
```

---

# Rutas de la API

## Listar tareas

```http
GET /api/v1/tasks
```

Devuelve todas las tareas

---

## Obtener detalle de una tarea

```http
GET /api/v1/tasks/:id
```

Busca una tarea usando un id

---

## Registrar una tarea

```http
POST /api/v1/tasks
```

Ejemplo de envio de datos:

```json
{
  "title": "Hacer la documentación",
  "description": "Completar el README del proyecto",
  "priority": "mid"
}
```

---

## Actualizar todos los datos de la tarea (requiere enviar todos los campos)

```http
PUT /api/v1/tasks/:id
```

Ejemplo:

```json
{
  "title": "Corregir documentación",
  "description": "Revisar endpoints y ejemplos",
  "priority": "high",
  "completed": false
}
```

---

## Cambiar solo algo de la tarea

```http
PATCH /api/v1/tasks/:id
```

Ejemplo:

```json
{
  "completed": true
}
```

---

## Borra una tarea

```http
DELETE /api/v1/tasks/:id
```

Elimina la tarea usando el id recibido
---

# Ruta de prueba

## Estado de la API

```http
GET /health
```

Para comprobar si el servidor esta activo o no, o incluso si tiene algun error interno

---

# Ejemplo de datos

```json
{
  "id": "uuid",
  "title": "Nombre de la tarea",
  "description": "Detalle de la tarea",
  "priority": "low",
  "completed": false,
  "createdAt": "2026-06-06T20:00:00.000Z",
  "updatedAt": "2026-06-06T20:00:00.000Z"
}
```

---

# Campos

| Campo         | Descripcion                                    |
| ------------- | -----------------------------------------------|
| `id`          | Identificador para cada tarea                  |
| `title`       | Nombre de la tarea                             |
| `description` | Descripcion de la tarea                        | 
| `priority`    | Nivel de prioridad: `low`, `mid` o `high`      |
| `completed`   | Booleano que indica si la tarea fue finalizada |
| `createdAt`   | Fecha de creacion de la tarea                  |
| `updatedAt`   | Fecha de la ultima actualizacion               |
