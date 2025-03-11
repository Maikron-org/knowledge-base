# Tipos de Instancias de EC2

## Clasificación de instancias por familia

| Familia | Ejemplos | Uso Recomendado |
|---------|---------|----------------|
| General Purpose | M5, T3, M6a, M7i | Servidores web, bases de datos pequeñas, entornos de desarrollo. |
| Compute Optimized | C5, C6g, C7i | Análisis en tiempo real, servidores de juegos. |
| Memory Optimized | R5, R6i, X2gd | Bases de datos en memoria, cachés de alto rendimiento. |
| Storage Optimized | I3, D2, I4i | Bases de datos NoSQL, almacenamiento de big data. |
| Accelerated Computing | P4, G5, Inf2 | Machine learning, renderizado gráfico. |
| Instancias Especiales | Mac2, HPC6a, Bare Metal | Desarrollo de macOS, cargas de trabajo de HPC. |

## Cómo elegir la mejor instancia

| Factor | Recomendación |
|--------|--------------|
| Requerimientos de CPU y Memoria | **General Purpose (M5, M6a, M7i)** para cargas equilibradas, **Compute Optimized (C5, C6i, C7i)** para alta CPU, **Memory Optimized (R6i, R7g, X2gd)** para alta memoria. |
| Tipo de almacenamiento | **Storage Optimized (I4i, D3, H1)** para almacenamiento de alto rendimiento. |
| GPU o aceleración | **P5, G5, Inf2** para aprendizaje profundo, **Inf1, Trn1** para inferencia de IA. |
| Costo vs. rendimiento | **T3, T4g (Burstable Performance)** para costo bajo, **Spot Instances** para cargas intermitentes. |
| Optimización de red | **M6in, C6in** para alto rendimiento de red. |


## 🔗 Recursos Adicionales

- 📄 [Tipos de instancias EC2](https://docs.aws.amazon.com/ec2/latest/instancetypes/)  