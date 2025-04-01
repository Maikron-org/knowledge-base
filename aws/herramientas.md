# Introducción a AWS CloudFormation y AWS CLI

Amazon Web Services (AWS) ofrece herramientas potentes para gestionar infraestructura como código y acceder programáticamente a sus servicios. En este resumen veremos dos herramientas fundamentales: **CloudFormation** y **AWS CLI**.

---

## AWS CloudFormation

### ¿Qué es CloudFormation?

AWS CloudFormation es un servicio que permite **modelar y aprovisionar recursos de AWS usando archivos de texto** en formatos JSON o YAML.

### Conceptos clave

- **Stack**: Conjunto de recursos definidos en una plantilla (ej. EC2, S3, Lambda, etc.).
- **Plantilla (template)**: Documento en JSON/YAML que describe la infraestructura deseada.
- **Recursos (resources)**: Componentes que se aprovisionarán (única sección obligatoria).
- **Parámetros, Salidas (outputs)** y **Funciones intrínsecas** permiten personalizar y conectar recursos.

### Estructura básica de una plantilla

```yaml
Description: Mi infraestructura
Resources:
  MiBucket:
    Type: AWS::S3::Bucket
```

### Ventajas

- Infraestructura reproducible y escalable.
- Control de versiones (IaC).
- Automatización de despliegues y actualizaciones.
- Protección de recursos críticos con `DeletionPolicy: Retain`.

### Buenas prácticas

- Utilizar nombres aleatorios o dejar que CloudFormation genere nombres únicos.
- Configurar plantillas con múltiples versiones.
- Usar `Change Sets` para visualizar diferencias antes de aplicar cambios.
- Complementar con herramientas como:
  - **AWS SAM**: Ideal para funciones Lambda.
  - **Serverless Framework**: Más compacto y sencillo.
  - **AWS CDK**: Infraestructura con lenguajes como TypeScript, Python, Java.

---

## AWS CLI

### ¿Qué es la CLI de AWS?

AWS CLI es una interfaz de línea de comandos que permite **gestionar servicios de AWS directamente desde tu terminal**.

### Instalación

- Descargar desde: [https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- Verificar con:

```bash
aws --version
```

### Configuración de perfiles

```bash
aws configure
# O usar múltiples perfiles:
aws configure --profile dev
```

Esto genera los archivos:

- `~/.aws/config`: configuración general.
- `~/.aws/credentials`: claves de acceso.

### Acceso programático

- Crear un usuario IAM con acceso programático.
- Obtener `Access Key ID` y `Secret Access Key`.
- Definir región por defecto (`us-east-1`, `eu-west-1`, etc.) y formato de salida (`json`, `yaml`, `text`).

### Uso de perfiles

```bash
aws s3 ls --profile dev
```

### Buenas prácticas

- No usar el perfil por defecto para todo.
- Evitar codificar claves en los scripts.
- Rotar periódicamente las claves de acceso.