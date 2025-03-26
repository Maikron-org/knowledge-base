# Introducción a Amazon S3

Amazon Simple Storage Service (Amazon S3) es un servicio de almacenamiento de objetos escalable, seguro y altamente disponible que permite almacenar y recuperar cualquier cantidad de datos desde cualquier lugar.

## Conceptos clave

### Bucket

Un **bucket** es el contenedor principal en Amazon S3. Todos los objetos (archivos) se almacenan dentro de un bucket. Cada bucket tiene un nombre único a nivel global y se crea en una región específica.

> Ejemplo:  
> Un bucket llamado `mi-sitio-web` puede contener imágenes, archivos HTML, videos y más.

### Objeto

Un **objeto** es la unidad básica de almacenamiento en S3. Cada objeto consiste en:

- **Datos** (por ejemplo, un archivo .jpg o .txt)
- **Clave (key)**: el nombre único que identifica al objeto dentro del bucket.
- **Metadatos**: información adicional sobre el objeto (tipo de archivo, codificación, etc.).

> Ejemplo:  
> En el bucket `mi-sitio-web`, un objeto podría tener la clave `imagenes/logo.png`.

## Características principales

- **Almacenamiento de objetos**: ideal para archivos, imágenes, videos, backups, etc.
- **Alta durabilidad**: diseñado para ofrecer una durabilidad del 99.999999999% (11 nueves).
- **Escalabilidad automática**: sin necesidad de administrar la infraestructura.
- **Control de acceso**: mediante políticas de bucket, listas de control de acceso (ACLs) y AWS IAM.
- **Versionado**: permite conservar versiones anteriores de un objeto.
- **Eventos y notificaciones**: integración con Lambda, SNS, SQS y otros servicios.
- **Clases de almacenamiento**: optimizadas para distintos casos de uso (Standard, Intelligent-Tiering, Glacier, etc.).

## Casos de uso

- Almacenamiento de archivos estáticos (por ejemplo, para sitios web).
- Backups y recuperación ante desastres.