# test-manager-library-3413974-page

> **Prueba técnica · Ficha ADSO 3413974**
> Horario: de **9:15 a. m. a 3:00 p. m.** (15:00). Después, **feria de presentación** de cada proyecto.

Este repositorio contiene el sitio público estático de presentación de *Manager Library*. Es
independiente de la API y de la base de datos.

## Stack y desarrollo guiado por especificación

| Capa | Tecnología |
|---|---|
| Frontend de gestión | React |
| Backend | PHP con Laravel |
| Sitio público | HTML y CSS estáticos |

Se conservan las historias, reglas, contrato API y modelo de datos del spec. La prueba evalúa cómo
se aplica SDD (*Spec-Driven Development*) al stack tecnológico definido.

## Ejecutar en Docker

Desde la raíz del proyecto, inicia el servicio público con Docker Compose:

```powershell
docker compose --env-file infra\.env -f infra\compose.yaml up --build -d page
```

Abre <http://localhost:8080>. El contenedor ofrece `GET /health`, que responde `200 ok`; no ejecuta
solicitudes ni requiere que la API esté activa.

También puedes construir y ejecutar la imagen desde esta carpeta:

```powershell
docker build -t manager-library-page .
docker run --rm -p 8080:80 manager-library-page
```

## Los seis repositorios

| Repositorio | Responsabilidad |
|---|---|
| [`docs`](https://github.com/code-sena/test-manager-library-3413974-docs) | Spec y decisiones SDD |
| [`api`](https://github.com/code-sena/test-manager-library-3413974-api) | Backend Laravel |
| [`app`](https://github.com/code-sena/test-manager-library-3413974-app) | Frontend React |
| [`page`](https://github.com/code-sena/test-manager-library-3413974-page) | Sitio público estático |
| [`infra`](https://github.com/code-sena/test-manager-library-3413974-infra) | Docker Compose y PostgreSQL |
| [`tool`](https://github.com/code-sena/test-manager-library-3413974-tool) | Sembrador de datos de demostración |
