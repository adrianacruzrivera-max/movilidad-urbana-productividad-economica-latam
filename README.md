# Movilidad urbana y productividad económica en Latinoamérica – Sprint 5

Este repositorio contiene el análisis realizado durante el Sprint 5 para evaluar cómo la movilidad urbana se relaciona con la productividad económica en las principales ciudades latinoamericanas.

Se trabaja con dos datasets: `tomtom_traffic` (TomTom Traffic Index), con registros de congestión por ciudad, y `oecd_city_economy` (OECD Cities), con PIB per cápita, desempleo, PM2.5 y población. Ambos requieren limpieza de nombres de columnas, conversión de fechas y corrección de formatos numéricos (separadores de miles, comas decimales y símbolo `%`). La muestra final queda en **15 ciudades de 7 países para el año 2024**, las únicas de las 387 ciudades de TomTom que tienen datos económicos en la OECD.

## 📂 Contenido del repositorio

- `notebooks/S5_ladb_mobility_economy_project_student_final_limpio.ipynb`
  → Notebook principal con carga y exploración, limpieza, filtrado de 2024, agregación del tráfico por ciudad, unión con los datos económicos, visualizaciones, conclusiones y resumen ejecutivo.
- `data/ladb_mobility_economy_2024_clean.csv`
  → Dataset final limpio: 15 filas (una por ciudad) y 14 columnas.
- `README.md`
  → Descripción del proyecto.

## ▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/adrianacruzrivera-max/movilidad-urbana-productividad-economica-latam/blob/main/notebooks/S5_ladb_mobility_economy_project_student_final_limpio.ipynb)

O:

1. Abre el archivo `.ipynb` en GitHub
2. Haz clic en **Open in Colab**

## 📘 Cómo reproducir el análisis

1. Abre `notebooks/S5_ladb_mobility_economy_project_student_final_limpio.ipynb`
2. Ejecuta las celdas en orden
3. Los datasets originales (`tomtom_traffic.csv` y `oecd_city_economy.csv`) no están incluidos en el repositorio. El notebook los lee desde `/datasets/`, por lo que debes ajustar esas rutas a tu entorno (por ejemplo, `/data/` o un enlace público)
4. Al final, el notebook exporta `ladb_mobility_economy_2024_clean.csv`

## 🧠 Objetivo del análisis

- Identificar problemas de calidad de datos y construir un pipeline de limpieza reproducible
- Resumir la congestión vehicular por ciudad y año
- Unir movilidad y economía mediante un `INNER JOIN` por `city` y `year`
- Analizar distribuciones, valores atípicos y la relación entre congestión y PIB per cápita
- Generar insights para priorizar inversiones en infraestructura de transporte

## 🔎 Hallazgos principales

- Ciudad de México presenta el mayor retraso promedio por congestión (`jams_delay` ≈ 2.833).
- No hay una relación clara entre congestión y PIB per cápita (correlación ≈ 0,28, con una muestra pequeña).
- En esta muestra, la congestión se asocia más con la población (ρ ≈ 0,86) que con el ingreso (ρ ≈ 0,21).
- Bogotá tiene el `traffic_index_live` más alto (≈ 37,61 frente a un promedio de ≈ 22,10) y un PIB per cápita por debajo de la mediana, por lo que se propone como caso prioritario de estudio.
- El PIB de Santiago en 2024 (2.277 USD) parece un error de captura de la fuente y no se corrigió, para mantener la trazabilidad.
