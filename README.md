# 📊 Análisis de Datos de Denuncias Policiales (SIDPOL)

Este proyecto automatiza el procesamiento, análisis y reporte en hojas de excel de indicadores de delitos, en base a datos de denuncias policiales (SIDPOL), con tablas y graficos, facilitando la detección de focos críticos y optimizando el análisis de incidencia delictiva a nivel nacional.
## 🎯 Objetivos del Proyecto

El análisis se centra en los siguientes pilares estratégicos:

### 1. Procesamiento y Limpieza de Datos
- **Carga de Datos:** Importación de la base histórica consolidada (`Base_datos_SIDPOL_diciembre_2025.xlsx`).
- **Estandarización:** Nombre de los encabezados, modalidades delictivas para asegurar el mejor entendimiento para el análisis temporal (2018-2025).

### 2. Análisis de Tendencias Temporales (Gráficos de Líneas)
- **Evolución Histórica:** Visualización de la trayectoria de denuncias desde 2018 hasta 2025 mediante `sns.lineplot`.
- **Análisis Específico:** Comparativa del comportamiento delictivo anual frente al comportamiento en periodos críticos (Cuatrimestre Septiembre-Diciembre).

### 3. Evaluación Comparativa Regional (Barras Horizontales)
- **Cálculo de Variación:** Determinación de la variación porcentual interanual (2024 vs 2025) por cada departamento del Perú.
- **Identificación de Focos:** Muestra cómo han cambiado los delitos en las distintas regiones del Perú entre el año 2024 y el 2025.

### 4. Automatización de Reportes con Buffers
- **Eficiencia en Memoria:** Uso de `io.BytesIO` para procesar gráficas en memoria, insertándolas directamente en Excel sin generar archivos temporales en disco.
- **Reporte principal:** Generar de forma automatizada un archivo de Excel `reporte_sidpol.xlsx`.

## 🛠️ Tecnologías Utilizadas

* **Pandas & NumPy:** Procesamiento de DataFrames y cálculo de variaciones estadísticas.
* **Seaborn & Matplotlib:** Creación de gráficos de líneas (tendencias) y barras horizontales (comparativas).
* **XlsxWriter:** Motor para la construcción del reporte Excel e inserción de objetos de memoria (Buffers).

## 📋 Estructura del Reporte Final (`reporte_sidpol.xlsx`)

El archivo generado organiza la información de manera profesional en las siguientes pestañas:

* 📑 **Reporte_Delitos y Reporte_Delitos_Sep_Dic:** Tablas detalladas con el conteo por modalidad desde 2018 a 2025, acompañadas de gráficos de líneas que visualizan la evolución de las denuncias para identificar picos de criminalidad y tendencias de largo plazo.

* 📑 **Grafico_Total_Delitos**: Gráfico de líneas de series temporales con múltiples ejes (escalas independientes). Representa la evolución anual de los delitos durante el periodo 2018-2025.

* 📑 **Gráficos por Modalidad:** Hojas individuales para **Corrupción, Estafa, Extorsión, Homicidio, Hurto, Robo, Secuestro, Violación y Otros**.
    * Cada hoja incluye una tabla con el conteo regional, la variación porcentual y el gráfico de barras horizontales correspondiente.

## 🚀 Instalación y Requisitos

Para ejecutar el proyecto, instala las librerías necesarias:

```bash
pip install pandas numpy matplotlib seaborn xlsxwriter openpyxl jinja2
```

## ⚙️ Uso

1. Coloca el archivo Base_datos_SIDPOL_diciembre_2025.xlsx en el mismo directorio que el notebook.
2. Abre y ejecuta todas las celdas de Denuncia_SIDPOL.ipynb.
3. Al finalizar, el script generará el archivo reporte_sidpol.xlsx listo para su análisis.

**Autor: Johan GV**