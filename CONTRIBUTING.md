# Guía de contribución

Este documento define las buenas prácticas para trabajar en el repositorio y mantener un flujo de desarrollo ordenado.

## Ramas del proyecto

El proyecto utiliza las siguientes ramas:

- `main`: rama principal y estable.
- `dev`: rama de desarrollo.
- `feature/<nombre>`: ramas para nuevas funcionalidades.
- `hotfix/<nombre>`: ramas para correcciones rápidas.

## Crear una nueva funcionalidad

Para trabajar en una nueva funcionalidad, se debe crear una rama desde `dev`:

git checkout dev
git pull origin dev
git checkout -b feature/nombre-del-cambio

Luego se realizan los cambios necesarios y se registran con commits.

## Crear una corrección

Para corregir un error, se debe crear una rama de tipo `hotfix`:

git checkout main
git pull origin main
git checkout -b hotfix/nombre-del-error

## Commits

Los commits deben ser claros y representar un cambio específico.

Formato recomendado:

tipo: descripcion breve del cambio

Tipos sugeridos:

- `feat`: nueva funcionalidad.
- `fix`: corrección de error.
- `style`: cambios visuales o de formato.
- `docs`: cambios en documentación.
- `chore`: tareas de configuración o mantenimiento.

Ejemplos:

- `feat: agrega seccion de pipeline`
- `fix: corrige enlace del sitio`
- `style: actualiza colores principales`
- `docs: agrega guia de contribucion`

## Pull requests

Los cambios deben integrarse mediante pull request.

Antes de crear un pull request, se recomienda revisar:

- Que los archivos modificados funcionen correctamente.
- Que los commits sean claros.
- Que no existan archivos innecesarios.
- Que no se incluyan claves, contraseñas o datos sensibles.

El pull request debe explicar brevemente:

- Qué cambio se realizó.
- Por qué se realizó.
- Qué archivos principales fueron modificados.

## Flujo de merge

El flujo recomendado es:

1. Las ramas `feature` se integran hacia `dev`.
2. La rama `dev` se integra hacia `main` cuando el cambio está listo.
3. Las ramas `hotfix` se integran hacia `main` y luego se actualiza `dev`.

## Estructura de carpetas

La estructura base del proyecto es:

- `.github/workflows/`: configuración de GitHub Actions.
- `assets/`: archivos CSS y JavaScript.
- `index.html`: página principal del sitio.
- `README.md`: descripción general del proyecto.
- `CONTRIBUTING.md`: guía de trabajo colaborativo.
- `CHANGELOG.md`: registro de cambios.
- `LICENSE.md`: licencia del proyecto.

## Buenas prácticas

- Trabajar siempre en ramas separadas.
- No modificar directamente `main`.
- Usar nombres de ramas descriptivos.
- Escribir commits breves y claros.
- Revisar los cambios antes de subirlos.
- Mantener actualizada la documentación.
- No subir archivos sensibles al repositorio.