# **Investigación sobre el Costo de una Instancia EC2 Bajo Demanda, Spot y Savings Plan (T3.medium)**

---

## **Especificaciones de la Instancia**
Para este análisis, se ha seleccionado una instancia de tipo **T3.medium**, cuyas características principales son:

- **Precio por hora (Bajo demanda):** 0.0416 USD
- **Precio por hora (Spot, estimado en us-east-1):** 0.015 USD
- **Precio por hora (Savings Plan 1 año, estimado en us-east-1):** 0.0261 USD
- **vCPUs:** 2
- **Memoria:** 4 GiB RAM
- **Almacenamiento:** Solo **EBS** (Elastic Block Store)
- **Red:** Hasta 5 gigabits por segundo

---

## **Cálculo del Costo Mensual**
### **1. Instancia Bajo Demanda**
Para determinar el costo mensual de la instancia bajo demanda, se multiplica el precio por hora por las horas en un mes:

- Horas en un mes: `24 horas/día * 30 días = 720 horas`
- Costo mensual: `0.0416 USD/hora * 720 horas = 29.95 USD`

### **2. Instancia Spot**
Si utilizamos una instancia Spot con un precio promedio de **0.015 USD por hora**, pero en un esquema donde se utiliza **24 horas al día, 5 días a la semana durante 4 semanas (20 días en total)**:

- Horas en un mes: `24 horas/día * 5 días/semana * 4 semanas = 480 horas`
- Costo mensual: `0.015 USD/hora * 480 horas = 7.20 USD`

### **3. Instancia con Savings Plan (1 año)**
Con un Savings Plan de **1 año**, el costo por hora se reduce a **0.0261 USD**:

- Costo mensual: `0.0261 USD/hora * 720 horas = 18.79 USD`
- Costo anual: `18.79 USD/mes * 12 meses = 225.48 USD`

Para determinar después de cuánto tiempo de uso bajo demanda se iguala el costo del Savings Plan:

- Tiempo necesario: `225.48 USD / 29.95 USD/mes = 7.53 meses`

Esto significa que, después de **aproximadamente 7.5 meses** usando la instancia bajo demanda, ya se habría pagado el costo equivalente a un **Savings Plan de 1 año**.

---

## **Factores Adicionales que Pueden Afectar el Costo**
Además del costo base de la instancia, existen otros factores que pueden influir en la facturación final:

### **1. Almacenamiento en Amazon EBS**
La instancia T3.medium no incluye almacenamiento persistente, por lo que es necesario añadir volúmenes **EBS**. Supongamos que se asigna un volumen **gp3 de 30 GiB**, cuyo costo promedio es **≈0.10 USD por GiB al mes**.

- Costo mensual de EBS: `30 GiB * 0.10 USD/GiB = 3 USD`

### **2. Tráfico de Red**
AWS cobra por el tráfico de salida a Internet. Las tarifas varían según la región y el volumen de datos transferidos. Si se transfieren **100 GB** de datos fuera de AWS, el costo estimado podría ser **≈9 USD/mes**.

### **3. Instantáneas de Amazon EBS**
Si se realizan **backups con instantáneas de EBS**, estos se cobran por el espacio utilizado. Por ejemplo, si una instantánea ocupa **10 GiB**, el costo mensual sería **≈0.05 USD por GiB**:

- Costo de instantáneas: `10 GiB * 0.05 USD/GiB = 0.50 USD`

---

## **Resumen del Costo Estimado Mensual**
| Concepto                          | Costo Bajo Demanda (USD) | Costo Spot (USD) | Costo Savings Plan (USD) |
|-----------------------------------|-------------------------|------------------|--------------------------|
| Instancia T3.medium              | **29.95**               | **7.20**        | **18.79**                |
| Almacenamiento EBS (30 GiB gp3)    | **3.00**                | **3.00**        | **3.00**                 |
| Tráfico de red (100 GB de salida)  | **9.00** (aprox.)       | **9.00**        | **9.00**                 |
| Instantáneas EBS (10 GiB)          | **0.50**                | **0.50**        | **0.50**                 |
| **Total estimado**                 | **42.45 USD/mes**       | **19.70 USD/mes** | **31.29 USD/mes**        |

---

## **Conclusión**
El costo mensual de una instancia **T3.medium** en **Amazon EC2 bajo demanda** es de **aproximadamente 29.95 USD**, mientras que el mismo uso en **Spot Instance** puede reducirse a **7.20 USD** si se ejecuta solo **5 días a la semana**. Usando un **Savings Plan de 1 año**, el costo se reduce a **18.79 USD/mes**, logrando un ahorro del **37% respecto al costo bajo demanda** sin sacrificar disponibilidad.

Después de **7.5 meses de uso bajo demanda**, el costo acumulado ya sería equivalente al pago del **Savings Plan de 1 año**, lo que hace que esta opción sea rentable para cargas de trabajo estables y predecibles.

Fuente de los precios: 
- [AWS Savings Plan Pricing](https://aws.amazon.com/ec2/pricing/reserved-instances/)
- [On-Demand](https://aws.amazon.com/es/ec2/pricing/on-demand/)
- [Reserved Instances](https://aws.amazon.com/es/ec2/pricing/reserved-instances/pricing/)

