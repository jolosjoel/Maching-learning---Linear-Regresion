# Proyecto de Predicción de Demanda con Regresión Lineal

## DESCRIPCION DEL PROYECTO
Este proyecto se basa en la metodología CRISP-DM y tiene como objetivo predecir la demanda del cliente utilizando datos históricos de ventas, que incluyen la demanda pronosticada, la demanda real del cliente, los inventarios en planta, las ventas reales y la producción actual.

Después de la obtención y comprensión de los datos, se recopiló la información en una base de datos llamada "Demanda2", la cual se obtuvo de diversas áreas de la empresa, como operaciones, finanzas y embarques a cliente. Durante el proceso de manipulación de la base de datos, se identificaron valores nulos, los cuales se eliminaron utilizando el siguiente código:

![image](https://github.com/jolosjoel/Maching-learning-Linear-Regresion/assets/45809759/2d34b378-4c58-48df-933f-015695891179)

Una vez que se limpió la base de datos, se calculó su tamaño, resultando en 21 variables con 45 instancias cada una.

![image](https://github.com/jolosjoel/Maching-learning-Linear-Regresion/assets/45809759/6ca26f9e-5fd5-488f-a72a-e136b73aebc7)

## Atributos Relevantes
A continuación, se describen los 21 atributos para una representación precisa de los datos:

- Fecha: Fecha real cuando se obtuvieron los datos, abarcando semanas desde la semana 1 a la semana 52 del 2022 y de la semana 1 a la semana 4 del 2023.
- Demanda: Demanda real compartida por el cliente por semana en la fecha correspondiente.
- Venta: Venta real por semana en la fecha correspondiente.
- Moldeo: Cantidad de piezas producidas por semana en la fecha correspondiente (primer proceso de producción).
- Visual: Cantidad de piezas inspeccionadas por semana en la fecha correspondiente (segundo proceso de producción).
- WIP: Inventario de piezas listas para maquinar por semana (proceso final).
- PT: Inventario de productos terminados por semana listos para ser enviados al cliente.
- Capacidad: Capacidad máxima de producción de piezas (Moldeo) por semana, basada en el número de máquinas asignadas al producto.
- Pronósticos: Los pronósticos del 1 al 12 se refieren al pronóstico de demanda compartido por el cliente con 12 semanas de anticipación a la fecha correspondiente.
- Promedio_Pronóstico: Es el promedio de los 12 pronósticos por semana.

## Análisis de Datos
Para una visualización más organizada de la demanda real, se representaron los datos en un histograma. Los resultados indican que la demanda real oscila entre 20,000 y 26,000 piezas por semana.

![image](https://github.com/jolosjoel/Maching-learning-Linear-Regresion/assets/45809759/203ad592-169f-4322-8d19-7ff751883d37)

## Modelado y Predicción
El proyecto utiliza el algoritmo de regresión lineal para predecir la demanda de los próximos 7 días, permitiendo al equipo de planificación asignar recursos de manera temprana para satisfacer las necesidades del cliente. Los datos se dividieron en dos conjuntos: entrenamiento y prueba.

- Variables de entrenamiento: (Promedio_Pronóstico, Ventas, Inventario, Pronóstico_1, Pronóstico_2, Pronóstico_3, WIP, Visual)
- Variable de prueba: (Demanda_real)
- Los resultados muestran que, a medida que aumentan las variables (Ventas, Pronóstico_1, Pronóstico_2 y Visual), la demanda real también aumenta. Por otro lado, a medida que aumentan las variables (Promedio_Pronóstico, Inventario, Pronóstico_3 y WIP), la demanda real disminuye.

![image](https://github.com/jolosjoel/Maching-learning-Linear-Regresion/assets/45809759/97e74aa8-7aff-4019-9f1a-0e52616a9f8e)

La predicción de la variable de demanda real arrojó un promedio de 22,309.44 piezas por semana. Además, se evaluó la precisión de la predicción mediante el coeficiente de determinación R^2, que dio como resultado un 73.74%.

![image](https://github.com/jolosjoel/Maching-learning-Linear-Regresion/assets/45809759/563fab67-dd77-448b-9edc-fe041565fb50)

![image](https://github.com/jolosjoel/Maching-learning-Linear-Regresion/assets/45809759/bfc57d13-ee82-41e0-ad87-3137b9a5096e)

## Conclusiones
Este algoritmo de predicción y regresión lineal contribuirá a mantener los inventarios más cercanos a las necesidades reales del cliente, evitando paros en la planta y fletes innecesarios. Además, facilitará la toma de decisiones y la distribución eficiente de los recursos para cumplir con la demanda del cliente.

En resumen, los resultados obtenidos en este proyecto son fundamentales para la toma de decisiones de la empresa, garantizando la producción de al menos 22,309 piezas por semana para mantener inventarios saludables y cumplir con los envíos al cliente de manera oportuna.

