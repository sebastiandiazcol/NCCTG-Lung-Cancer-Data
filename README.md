Aquí tienes el README en formato Markdown listo para ser copiado y pegado en tu repositorio.

-----

# 📊 Análisis de Datos de Cáncer de Pulmón del NCCTG

[](https://www.google.com/search?q=/)

## **Descripción del Proyecto**

Este proyecto de ciencia de datos presenta un análisis exploratorio (EDA) y de supervivencia del conjunto de datos **NCCTG Lung Cancer Data**, originado por el National Cancer Institute de EE.UU. El objetivo principal es investigar la supervivencia de pacientes con cáncer de pulmón y la influencia de variables demográficas, clínicas y de estado funcional. El análisis se ha realizado en R y se enfoca en comprender la estructura de los datos y las relaciones entre variables clave como el tiempo de supervivencia, el sexo y el estado funcional.

-----

## **Tabla de Contenidos**

1.  [Estructura de Datos](https://www.google.com/search?q=%23estructura-de-datos)
2.  [Análisis Exploratorio de Datos (EDA)](https://www.google.com/search?q=%23an%C3%A1lisis-exploratorio-de-datos-eda)
      * [Características Generales](https://www.google.com/search?q=%23caracter%C3%ADsticas-generales)
      * [Distribución de Variables](https://www.google.com/search?q=%23distribuci%C3%B3n-de-variables)
      * [Análisis de Supervivencia](https://www.google.com/search?q=%23an%C3%A1lisis-de-supervivencia)
3.  [Conclusiones](https://www.google.com/search?q=%23conclusiones)
4.  [Entorno de Replicación](https://www.google.com/search?q=%23entorno-de-replicaci%C3%B3n)

-----

## **Estructura de Datos**

El conjunto de datos contiene 228 observaciones y 9 variables, las cuales incluyen información demográfica y clínica de pacientes. A continuación se detallan las variables clave:

| Variable | Descripción | Tipo de Dato |
| :--- | :--- | :--- |
| `inst` | ID de la institución médica. | Numérico |
| `time` | Tiempo de seguimiento en días hasta la muerte o censura. | Numérico |
| `status` | Estado vital (0: Vivohttps://www.google.com/search?q=/Censurado, 1: Fallecido). | Numéricohttps://www.google.com/search?q=/Categórico |
| `age` | Edad del paciente en años. | Numérico |
| `sex` | Género del paciente (0: Femenino, 1: Masculino). | Numéricohttps://www.google.com/search?q=/Categórico |
| `ph.ecog` | Índice de estado funcional del ECOG. | Numéricohttps://www.google.com/search?q=/Categórico |
| `ph.karno` | Índice de Karnofsky del paciente. | Numérico |
| `meal.cal` | Ingesta calórica diaria. | Numérico |
| `wt.loss` | Pérdida de peso en los últimos 6 meses (lbs). | Numérico |

-----

## **Análisis Exploratorio de Datos (EDA)**

### **Características Generales**

  * **Población:** La muestra de 228 pacientes tiene una edad promedio de 62.4 años, lo que los sitúa en el rango de "adultos mayores" según la OMS. Las edades oscilan entre 39 y 82 años.
  * **Género:** Hay una notable desproporción de género, con un **60.5%** de pacientes masculinos (138) y un **39.5%** de pacientes femeninos (90).
  * **Valores Faltantes:** Se identificaron valores faltantes significativos en dos variables:
      * `meal.cal` (ingesta calórica): más del 20% de los datos están ausentes, con mayor prevalencia en mujeres.
      * `wt.loss` (pérdida de peso): más del 5% de los datos están ausentes, con mayor prevalencia en hombres.
  * **Estado de Salud:** La mayoría de los pacientes presentaban un buen estado funcional, con una alta concentración de puntuaciones del índice de Karnofsky (KPS) alrededor de 80-90.

### **Distribución de Variables**

  * **Edad:** La distribución de la edad es similar a una campana, con la mayoría de los pacientes entre 50 y 75 años. Los pacientes que fallecieron tuvieron una edad media ligeramente mayor (aprox. 70 años) que los que sobrevivieron (aprox. 65 años).
  * **Tiempo de Supervivencia (`time`):** La mayoría de los eventos de fallecimiento se concentraron en los primeros 500 días de seguimiento.
  * **Pérdida de Peso (`wt.loss`):** La mayoría de los pacientes no experimentaron una pérdida de peso significativa.
  * **Ingesta Calórica (`meal.cal`):** La mayor parte de los pacientes consumieron menos de 1500 calorías diarias.

### **Análisis de Supervivencia**

  * **Supervivencia General:** La curva de Kaplan-Meier muestra una disminución gradual en la probabilidad de supervivencia con el tiempo, con un intervalo de confianza que se amplía, lo que indica mayor incertidumbre en la estimación para períodos más largos.
  * **Supervivencia por Sexo:** El análisis estratificado revela que el **sexo es un factor pronóstico significativo**. Las mujeres mostraron una mediana de supervivencia significativamente mayor que los hombres (`p-valor < 0.05`), sugiriendo una mejor tasa de supervivencia en este grupo.
  * **Censura:** La distribución de casos censurados (pacientes que no fallecieron durante el estudio) no parece estar significativamente influenciada por el sexo. El número de censuras se incrementó notablemente entre los 150 y 300 días de seguimiento.

-----

## **Conclusiones**

  * El tiempo de seguimiento promedio para los pacientes que fallecieron fue de 283 días, significativamente menor que los 363 días para los pacientes vivos al final del estudio.
  * El sexo del paciente emerge como una variable crítica en el pronóstico de supervivencia, con las mujeres demostrando una supervivencia más prolongada en comparación con los hombres.
  * La alta tasa de valores faltantes en `meal.cal` y `wt.loss` podría requerir un manejo cuidadoso (imputación, exclusión, etc.) antes de realizar análisis predictivos más avanzados.
  * Los datos indican que los pacientes de mayor edad y los hombres podrían tener un pronóstico más reservado en términos de supervivencia.

-----

## **Entorno de Replicación**

Para replicar este análisis, se requiere el uso de las siguientes librerías de R:

```r
# Cargar las librerías
library(knitr)
library(autoReg)
library(kableExtra)
library(DataExplorer)
library(extrafont)
library(dlookr)
library(summarytools)
library(corrplot)
library(survival)
library(survminer)
library(powerSurvEpi)
library(rms)
library(sm)
library(tidyverse)
library(condSURV)
```
