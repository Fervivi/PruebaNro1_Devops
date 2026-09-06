# Mi primer pipeline de despliegue

Este repositorio contiene un sitio web estático utilizado para implementar y demostrar un flujo básico de trabajo DevOps usando Git, GitHub y GitHub Actions.

El objetivo del proyecto es aplicar control de versiones, trabajo colaborativo mediante ramas y pull requests, y automatización de despliegue hacia un servidor web.

## Tecnologías utilizadas

- HTML
- CSS
- JavaScript
- Git
- GitHub
- GitHub Actions
- AWS EC2
- Apache HTTP Server

## Estructura del proyecto

.
├── .github/
│   └── workflows/
│       └── deploy.yml
├── assets/
│   ├── app.js
│   └── style.css
├── index.html
├── README.md
├── CONTRIBUTING.md
├── CHANGELOG.md
└── LICENSE.md

## Estrategia de ramificación

Para este proyecto se utiliza una estrategia basada en GitFlow, ya que permite separar el trabajo estable del desarrollo activo y facilita la colaboración entre integrantes.

Las ramas principales son:

- `main`: contiene la versión estable del proyecto.
- `dev`: contiene los cambios en desarrollo antes de pasar a producción.
- `feature/<nombre>`: se utiliza para desarrollar nuevas funcionalidades.
- `hotfix/<nombre>`: se utiliza para corregir errores urgentes.

Esta estrategia permite mantener ordenado el flujo de trabajo, revisar cambios antes de integrarlos y asegurar trazabilidad en el código.

## Flujo de trabajo

El flujo de trabajo definido para el proyecto es el siguiente:

1. Crear una rama desde `dev` para trabajar una nueva funcionalidad.
2. Realizar cambios en los archivos del proyecto.
3. Registrar los cambios mediante commits claros.
4. Subir la rama al repositorio remoto.
5. Crear un pull request para revisar e integrar los cambios.
6. Fusionar los cambios hacia `dev` o `main`, según corresponda.
7. Ejecutar el workflow de GitHub Actions para validar o desplegar el proyecto.

## Convención de nombres de ramas

Se utilizan los siguientes formatos:

- `feature/nombre-del-cambio`
- `hotfix/nombre-del-error`

Ejemplos:

- `feature/pagina-principal`
- `feature/estilos-web`
- `hotfix/correccion-texto`

## Convención de commits

Los mensajes de commit deben ser claros y describir el cambio realizado.

Ejemplos:

- `feat: agrega estructura principal de la pagina`
- `style: mejora estilos del sitio`
- `fix: corrige texto de bienvenida`
- `docs: actualiza documentacion del proyecto`

## GitHub Actions

El proyecto incluye un workflow ubicado en `.github/workflows/deploy.yml`.

Este workflow automatiza el proceso de despliegue del sitio. Su función principal es copiar los archivos del proyecto hacia un servidor EC2 y publicarlos en Apache.

El workflow utiliza secretos configurados en GitHub para conectarse al servidor de forma segura:

- `AWS_SSH_KEY`
- `AWS_HOST`
- `AWS_USER`

## Despliegue

El despliegue se realiza hacia una instancia EC2 con Apache instalado.

El proceso general es:

1. GitHub Actions descarga el código del repositorio.
2. Se configura la conexión SSH usando los secretos del repositorio.
3. Se copian los archivos `index.html` y la carpeta `assets` al servidor.
4. Los archivos se publican en `/var/www/html`.
5. Se reinicia Apache para mostrar la nueva versión del sitio.

## Evidencia del pipeline

Cada cambio visible en la página web sirve como evidencia de que el flujo funciona correctamente. Al modificar el sitio, subir los cambios y ejecutarse el workflow, la nueva versión debe aparecer publicada en el servidor.

## Integrantes

- Fernando Villalobos

## Licencia

Este proyecto se distribuye bajo la licencia MIT. Revisa el archivo `LICENSE.md` para más información.