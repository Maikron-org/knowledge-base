# Elasticidad en AWS y Auto Scaling con EC2

La **elasticidad** es uno de los principios clave de la computación en la nube. Se refiere a la capacidad de adquirir recursos cuando los necesitas y liberarlos cuando ya no son necesarios, lo cual permite optimizar costos y responder a cambios en la demanda.

Este resumen cubre los temas vistos en el video, incluyendo el uso de instancias EC2, escalabilidad horizontal y vertical, balanceadores de carga y Auto Scaling Groups.

## Conceptos clave

### Elasticidad

- **Escalado vertical (vertical scaling)**: mejorar (o disminuir) los recursos de una instancia existente (CPU, RAM).
- **Escalado horizontal (horizontal scaling)**: agregar o quitar instancias completas en respuesta a la demanda.
- Escalar horizontalmente es la **mejor práctica** en arquitecturas modernas.

### EC2 (Elastic Compute Cloud)

Permite crear y administrar **servidores virtuales** en la nube.

> Ejemplo:  
> Lanzar una instancia EC2 con Amazon Linux y configurar un servidor de Node.js que escucha en el puerto 3000.


### Auto Scaling Group (ASG)

Permite escalar automáticamente el número de instancias EC2 en función de reglas definidas (como uso de CPU).

- Se define a partir de un **Launch Template** o una **AMI (imagen)**.
- Puede integrarse con un Load Balancer.
- Monitorea el estado de las instancias y las reemplaza si fallan.

> Ejemplo:  
> Escalar automáticamente de 1 a 4 instancias según el uso de CPU.

### User Data

Script que se ejecuta al lanzar una nueva instancia. Se usa para automatizar configuraciones como instalación de paquetes o despliegue de apps.

```bash
#!/bin/bash
echo "Starting Node.js Server"
cd /home/ec2-user/my-app
node hello-server.js
```

## Buenas prácticas

- 🧠 Usar escalado horizontal para soportar cargas variables.
- 🔁 Automatizar la creación de instancias con Launch Templates y User Data.
- 🔐 Limitar acceso directo a instancias mediante Security Groups.
- 🎯 Monitorear el estado de las instancias con Health Checks.
- 💸 Eliminar recursos cuando ya no se usen para evitar cargos innecesarios.

## Casos de uso

- Aplicaciones web que experimentan cambios de tráfico.
- Backend de juegos o aplicaciones móviles.
- Entornos de desarrollo que requieren alta disponibilidad.
- Sistemas que requieren alta escalabilidad y redundancia.

---

¿Sabías que los Load Balancers tienen costo, pero los Auto Scaling Groups no? Solo se paga por los recursos que se escalen, como instancias y volúmenes.

