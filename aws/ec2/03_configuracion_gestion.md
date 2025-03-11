# Configuración y Gestión de Instancias EC2

## Métodos de lanzamiento de instancias

- **Consola de AWS**: Interfaz gráfica para configurar y lanzar instancias.
- **AWS CLI**: Comandos de línea para automatización.
- **AWS SDKs**: Para lanzar instancias desde aplicaciones.
- **CloudFormation y Terraform**: Infraestructura como código para automatización.

## Conexión a instancias (SSH, RDP, EC2 Instance Connect)

- **SSH** para instancias Linux.
- **RDP** para instancias Windows.
- **EC2 Instance Connect** permite conectarse sin necesidad de claves SSH.
- **AWS Systems Manager Session Manager** para acceso seguro sin exponer puertos.

## Administración con AWS Systems Manager

- **Run Command**: Ejecutar comandos remotos.
- **Patch Manager**: Aplicación de parches de seguridad automatizada.
- **Session Manager**: Acceso seguro sin claves SSH o RDP.
- **State Manager**: Aplicación de configuraciones recurrentes.

## Estados de instancia

| Estado | Descripción |
|--------|------------|
| Pending | Inicializando la instancia. |
| Running | La instancia está en ejecución. |
| Stopped | La instancia está detenida, pero su volumen EBS persiste. |
| Terminated | La instancia ha sido eliminada permanentemente. |
| Hibernated | Estado en el que se conserva la RAM en disco. |