# Introducción a IAM

**AWS Identity and Access Management (IAM)** es un servicio de Amazon Web Services que permite gestionar de forma segura el acceso a los recursos de AWS. Con IAM puedes crear y administrar usuarios, grupos, roles y políticas para controlar quién puede acceder a qué recursos dentro de tu cuenta de AWS.

## Conceptos clave

### Usuario

Un **usuario** representa una persona o aplicación que interactúa con AWS. Puede tener acceso programático (mediante claves) o acceso a la consola (usuario y contraseña).

> Ejemplo:  
> Crear un usuario llamado `desarrollador1` para acceder a la consola con permisos específicos.

### Grupo

Un **grupo** es una colección de usuarios. Las políticas se asignan al grupo, y los usuarios heredan los permisos automáticamente.

> Ejemplo:  
> Un grupo llamado `Administradores` puede tener permisos de acceso total a todos los servicios de AWS.

### Política (Policy)

Una **policy** es un documento en formato JSON que define los permisos que se otorgan o deniegan a un usuario, grupo o rol.

> Ejemplo:  
> La política `AmazonS3ReadOnlyAccess` permite solo lectura sobre los buckets de S3.

### Rol

Un **rol** es una entidad que puede ser asumida temporalmente por servicios, usuarios o identidades federadas para acceder a recursos con permisos definidos.

> Ejemplo:  
> Un servidor EC2 puede asumir un rol que le da acceso temporal a un bucket S3 sin usar credenciales fijas.

### Password Policy

Permite establecer reglas para la creación de contraseñas seguras (longitud mínima, uso de mayúsculas, números, caducidad, etc.).

> Ejemplo:  
> Requerir que todas las contraseñas tengan al menos 8 caracteres y contengan un número.

### Identity Provider

Permite integrar identidades externas (como Google Workspace, Active Directory) para usar autenticación federada con IAM.

> Ejemplo:  
> Usuarios de una empresa pueden iniciar sesión en AWS con sus cuentas de Google mediante OpenID Connect.

## Características principales

- **Gestión de identidades centralizada** para controlar accesos.
- **Permisos granulares** gracias al uso de políticas JSON.
- **Acceso temporal seguro** mediante roles.
- **Soporte para MFA (Multi-Factor Authentication)** para mayor seguridad.
- **Auditoría y seguimiento** con CloudTrail.

## Buenas prácticas

- 🛡️ **Principio de menor privilegio**: otorgar solo los permisos necesarios para realizar tareas.
- 👥 Usar **grupos** para asignar permisos, no directamente a usuarios.
- 🔐 Activar **MFA** para usuarios con privilegios elevados.
- 🚫 Evitar usar el **usuario root** para tareas diarias.
- 🔄 Establecer una **política de contraseñas** para fortalecer la seguridad.

## Casos de uso

- Controlar acceso a servicios como S3, EC2, RDS, etc.
- Dar acceso a desarrolladores, administradores o aplicaciones.
- Permitir acceso federado a empleados mediante identidad externa.
- Crear roles para servicios que necesitan interactuar entre sí.
