# Introducción a Amazon DynamoDB

**Amazon DynamoDB** es un servicio de base de datos NoSQL totalmente gestionado que ofrece almacenamiento rápido y flexible para cualquier escala. Está diseñado para manejar grandes volúmenes de datos con baja latencia y alta disponibilidad.

## Conceptos clave

### Tabla

Una **tabla** es la unidad principal de almacenamiento en DynamoDB, similar a una tabla en bases de datos tradicionales. Cada tabla almacena un conjunto de elementos (filas).

> Ejemplo:  
> Una tabla llamada `Usuarios` puede almacenar información como ID, nombre y correo electrónico.

### Ítem

Un **ítem** es un conjunto de atributos que representan una sola entrada en una tabla. Es el equivalente a una fila.

> Ejemplo:  
> Un ítem en la tabla `Usuarios` puede tener: `{ "ID": 1, "Nombre": "Ana", "Correo": "ana@example.com" }`

### Atributo

Un **atributo** es una unidad individual de datos dentro de un ítem (similar a una columna en bases de datos relacionales).

> Ejemplo:  
> En el ítem anterior, `Nombre` y `Correo` son atributos.

### Clave primaria

La **clave primaria** identifica de forma única a cada ítem en una tabla. Puede ser:

- **Clave de partición** (Partition key): valor único que determina la ubicación del ítem.
- **Clave compuesta**: combinación de clave de partición y clave de ordenamiento (Sort key).

### Índices

Los **índices secundarios** permiten realizar consultas adicionales:

- **Global Secondary Index (GSI)**: permite consultar atributos distintos a la clave primaria.
- **Local Secondary Index (LSI)**: permite ordenar datos con una clave de orden adicional.

## Características principales

- **Alto rendimiento y baja latencia**.
- **Escalabilidad automática** con capacidad aprovisionada o bajo demanda.
- **Alta disponibilidad** con replicación automática en múltiples zonas de disponibilidad.
- **Integración con otros servicios** como Lambda, API Gateway, y más.
- **Control de acceso granular** mediante IAM.
- **Streams** para capturar cambios en tiempo real.

## Buenas prácticas

- 📌 Definir bien la clave primaria y los índices para evitar cuellos de botella.
- 🚫 Evitar lecturas y escrituras excesivas en la misma clave de partición.
- 📊 Usar **provisión bajo demanda** si la carga es impredecible.
- 🔐 Aplicar políticas IAM estrictas para limitar el acceso a las tablas.

## Casos de uso

- Aplicaciones web y móviles con requisitos de latencia milisegundos.
- Juegos en tiempo real.
- IoT (Internet of Things).
- Sistemas de catálogos o gestión de usuarios.
- Almacenamiento de sesiones o tokens.

