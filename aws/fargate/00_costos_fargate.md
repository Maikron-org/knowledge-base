# **Estimación de costos en AWS Fargate**

Se utilizó https://calculator.aws/#/createCalculator/Fargate

AWS Fargate es un servicio sin servidor que permite ejecutar contenedores sin administrar servidores directamente. Su modelo de precios se basa en los recursos asignados a las **tareas (ECS Tasks) o pods (EKS Pods)**, incluyendo **vCPU, memoria y almacenamiento efímero**.

## **Configuración utilizada en la estimación**
- **Sistema operativo:** Linux  
- **Arquitectura de CPU:** x86  
- **Número de tareas/pods:** 4 por día  
- **Duración promedio:** 1 día por tarea/pod (24 horas)  
- **Cantidad de vCPU por tarea/pod:** 2  
- **Memoria asignada por tarea/pod:** 4 GB  
- **Almacenamiento efímero:** 20 GB (los primeros 20 GB son gratuitos)  

## **Cálculo del consumo mensual**
### **Número total de tareas o pods por mes**
4 tareas por día * (730 horas en un mes / 24 horas en un día) = 121.67 tareas/mes

### **Consumo de vCPU**
121.67 tareas * 2 vCPU * 24 horas * 0.04048 USD/hora = 236.41 USD

### **Consumo de memoria**
121.67 tareas * 4 GB * 24 horas * 0.004445 USD/GB-hora = 51.92 USD

### **Almacenamiento efímero**  
No genera costo adicional ya que el uso no supera los **20 GB gratuitos por tarea**.

## **Costo total mensual de AWS Fargate**
- **Costo por vCPU:** 236.41 USD  
- **Costo por memoria:** 51.92 USD  
- **Costo total:** **288.33 USD por mes**

