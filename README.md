# Proyecto: Identificación de Operadores Ineficaces – CallMeMaybe

## Contexto del proyecto

CallMeMaybe es un servicio de telefonía virtual que distribuye un gran volumen de llamadas entre operadores de sus clientes.

El objetivo de la empresa es identificar operadores ineficaces para poder mejorar su desempeño mediante capacitación o reasignación de tareas.

- Un operador se considera ineficaz cuando presenta:
- Alta proporción de llamadas entrantes perdidas
- Tiempos de espera elevados
- Bajo número de llamadas salientes en comparación con otros operadores

Este proyecto analiza los datos del sistema para detectar operadores con bajo rendimiento. 

## Objetivo del análisis

Los objetivos principales del proyecto son:

- Explorar los datos del sistema CallMeMaybe
- Construir métricas por operador para evaluar su desempeño
- Identificar operadores potencialmente ineficaces
- Validar estadísticamente los resultados

Se considera operador ineficaz a aquellos que se encuentran en el peor 10% en métricas de desempeño. 

## Datos utilizados

Se utilizaron dos conjuntos de datos principales:

telecom_dataset_new.csv
Contiene estadísticas diarias de llamadas por operador y cliente, incluyendo:

- Duración de llamadas
- Llamadas perdidas
- Dirección de llamadas (interna o externa)
- Tiempos de espera

telecom_clients.csv
Incluye información sobre las cuentas de clientes.

El dataset contiene aproximadamente:

- 59,902 registros de llamadas
- 732 clientes 

## Análisis Exploratorio de Datos (EDA)

Se realizó un análisis exploratorio para comprender el comportamiento de las llamadas.

Gráficos generados:

- Histograma de duración de llamadas
- Gráfico circular de llamadas internas vs externas
- Número de llamadas por día

Principales hallazgos:

- Alta variabilidad en la duración de llamadas
- Uso frecuente de llamadas internas entre operadores 

## Métricas por operador

- Se calcularon métricas clave para evaluar el desempeño:
- Total de llamadas por operador
- Porcentaje de llamadas perdidas
- Tiempo promedio de espera

Criterio de identificación:
Operadores dentro del peor 10% en porcentaje de llamadas perdidas o tiempo de espera fueron clasificados como potencialmente ineficaces. 

## Resultados

Se identificaron:

208 operadores potencialmente ineficaces (10% del total)

Patrones observados:

- Algunos operadores presentan hasta 100% de llamadas perdidas
- Tiempos de espera superiores a 30–100 segundos

Ejemplos de operadores con bajo desempeño:
- 909308
- 932246 

Pruebas estadísticas

Se aplicó la prueba Mann–Whitney U para validar los resultados.

Resultados:

Tiempo de espera
p-value = 4.05e-18

Porcentaje de llamadas perdidas
p-value = 1.21e-85

Ambos resultados son estadísticamente significativos, lo que confirma que los operadores identificados tienen un desempeño inferior al resto. 


## Conclusiones

- El 10% de los operadores concentra el peor rendimiento
- La ineficiencia detectada es estadísticamente significativa
- El patrón observado no es aleatorio 


## Recomendaciones

Para mejorar la eficiencia del sistema se recomienda:

- Capacitación para operadores con bajo desempeño
- Monitoreo mensual utilizando percentiles
- Implementar alertas automáticas por tiempos de espera elevados
- Revisar la carga laboral de operadores críticos 


## Tecnologías utilizadas

- Python
- Pandas
- Matplotlib / Seaborn
- SciPy (pruebas estadísticas)
- Jupyter Notebook

## Autor

María de Lourdes Martínez Ruvalcaba

Bootcamp Data Analyst – TripleTen
