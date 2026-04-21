# Proppia — community health files

Este repositorio contiene los archivos de configuración que GitHub aplica por default a los repositorios de la organization [`Proppia`](https://github.com/orgs/Proppia) que no definan los suyos propios.

## Contenido

- `profile/README.md` — Landing de la organization ([github.com/Proppia](https://github.com/Proppia)).
- `PULL_REQUEST_TEMPLATE.md` — Template default para pull requests.
- `SECURITY.md` — Política de reporte de vulnerabilidades.
- `CONTRIBUTING.md` — Guía para colaboradores, incluyendo setup de commit signing.

## Cómo funciona

GitHub reconoce el repo `.github` de cada organization y lo usa como fallback: si un repo no tiene su propio `PULL_REQUEST_TEMPLATE.md`, se usa el que vive aquí. Cada repo puede sobrescribir estos defaults creando su propia versión del archivo.

## Contribuciones

Cambios a estos archivos se proponen vía pull request.
