# AWS y el Cómputo en la Nube

## Introducción a AWS

### ¿Qué es el cómputo en la nube?

La computación en la nube es la distribución de recursos de tecnologías de la información (TI) a través de Internet bajo un esquema de pago por uso. Esto permite a las organizaciones acceder a servicios como almacenamiento, bases de datos, servidores, redes, software y más, sin necesidad de adquirir o mantener infraestructura física.

### Ventajas del cómputo en la nube

- **Cambio de costos iniciales por costos variables**  
  En lugar de realizar grandes inversiones en infraestructura, se paga solo por lo que se utiliza.

- **Eliminación del mantenimiento de centros de datos**  
  AWS se encarga de operar y mantener la infraestructura física.

- **Escalabilidad**  
  Se puede ajustar la capacidad de recursos según la demanda, sin necesidad de planear con anticipación.

- **Mayor velocidad y agilidad**  
  Es posible desplegar recursos en minutos, lo que permite experimentar e innovar rápidamente.

- **Economías de escala**  
  AWS optimiza los recursos para miles de clientes, lo que reduce los costos operativos.

- **Alcance global**  
  AWS cuenta con centros de datos en múltiples regiones del mundo, lo que permite ofrecer servicios con baja latencia a usuarios en diferentes ubicaciones.

## Infraestructura de AWS

### Regiones

Las regiones de AWS son ubicaciones geográficas físicas donde AWS agrupa sus centros de datos. Cada región está compuesta por al menos dos zonas de disponibilidad. Los clientes pueden elegir la región que mejor se adapte a sus necesidades en términos de latencia, cumplimiento normativo y redundancia.

> Ejemplos de regiones:  
> - us-east-1 (Norte de Virginia)  
> - eu-west-1 (Irlanda)  
> - ap-southeast-1 (Singapur)

### Zonas de disponibilidad (Availability Zones)

Una zona de disponibilidad (AZ) es uno o más centros de datos distintos dentro de una región, cada uno con alimentación eléctrica, refrigeración y redes redundantes. Las AZ están diseñadas para ser aisladas entre sí, pero conectadas con baja latencia, lo que permite alta disponibilidad y tolerancia a fallos.

### Edge Locations (Ubicaciones perimetrales)

Las ubicaciones perimetrales son centros de datos utilizados por servicios como Amazon CloudFront para entregar contenido con baja latencia a los usuarios finales. Estas ubicaciones están distribuidas globalmente y optimizan la entrega de contenido estático y dinámico, mejorando la experiencia del usuario.

