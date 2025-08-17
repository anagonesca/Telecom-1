# Análisis de Churn de Clientes en TelecomX

## Descripción del Proyecto
Este proyecto es el resultado del análisis que realicé sobre el **churn** (abandono) de clientes en **TelecomX**. Usé Google Colab (`TelecomX_LATAM.ipynb`) y trabajé con **Python** junto con bibliotecas como *Pandas, NumPy, Matplotlib* y *Seaborn*.  

Los datos provienen de un archivo JSON alojado en GitHub. A lo largo del notebook me enfoqué en: extracción, transformación, limpieza, análisis exploratorio y visualizaciones para entender qué variables influyen más en el abandono de clientes.  

El dataset contiene información demográfica, servicios contratados, tipo de contrato, métodos de pago y costos asociados. Aunque en esta primera versión no entrené modelos predictivos, preparé un CSV (`datos_tratados.csv`) que queda listo para usarse en futuros análisis de Machine Learning.  

---

## Estructura del Repositorio
- **`TelecomX_LATAM.ipynb`**: Notebook principal con todo el análisis. Incluye:
  - Extracción de datos desde la URL:  
    `https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json`
  - Transformación y limpieza: normalización de JSON, conversión de tipos, creación de columnas derivadas como `DailyCharges`.  
  - Análisis exploratorio de variables demográficas, servicios, contratos y costos.  
  - Visualizaciones: gráfico de pastel de churn, heatmap de combinaciones categóricas y boxplots para tenure y cargos mensuales.  
- **`datos_tratados.csv`**: Archivo CSV con los datos ya procesados, pensado para modelado predictivo.  
- **README.md**: Este archivo, donde explico cómo usar el proyecto y qué hallazgos encontré.  

---

## Requisitos
Para correr el notebook necesitas:  

- **Python 3.8+**  
- Dependencias:  
  ```bash
  pip install pandas numpy matplotlib seaborn requests

---
* Entorno recomendado: **Jupyter Notebook** o **Google Colab**.

---

## Instrucciones de Uso

1. **Clonar el repositorio**:

   ```bash
   git clone https://github.com/anagonesca/Telecom-1.git
   cd Telecom-1
   ```
2. **Abrir el notebook**:

   * Local: `jupyter notebook TelecomX_LATAM.ipynb`
   * Google Colab: subir el `.ipynb` o abrir el enlace directo.
3. **Ejecutar las celdas**: El notebook está ordenado para correrse paso a paso. Necesitas conexión a internet para leer el JSON desde la URL.
4. **Explorar resultados**: Revisa gráficos (pastel, heatmap, boxplots) y el CSV exportado.
5. **Extender el análisis**: Usa `datos_tratados.csv` para entrenar modelos de Machine Learning (regresión logística, árboles de decisión, etc.).

---

## Estructura del Notebook

1. **Extracción de Datos**: Carga del JSON y revisión inicial.
2. **Transformación y Limpieza**: Normalización, conversión de tipos, creación de `DailyCharges`.
3. **Análisis Exploratorio**:

   * Variables numéricas: `Tenure`, `ChargesMonthly`, `ChargesTotal`, `DailyCharges`.
   * Variables categóricas: `Gender`, `Contract`, `InternetService`, entre otras.
   * Proporción de churn: 71% No, 26% Yes, 3% N/A.
4. **Visualizaciones**:

   * Gráfico de pastel para proporción de churn.
   * Heatmap de churn por género, contrato e Internet.
   * Boxplots de `Tenure` y `ChargesMonthly`.
5. **Exportación**: Generación del archivo `datos_tratados.csv`.

---

## Hallazgos Clave

* **Tasa de churn**: 26% de abandono y 3% de datos N/A.
* **Factores influyentes**:

  * Clientes nuevos (bajo `Tenure`) se van más rápido.
  * Los contratos mes a mes tienen mucho más churn que los de largo plazo.
  * Los servicios de Internet (DSL y fibra) aparecen con más abandono.
  * Clientes con cargos mensuales altos tienden a desertar más (aunque habría que confirmarlo con correlaciones).
* **Visualizaciones**: Los boxplots muestran que quienes abandonan tienen menor permanencia y, en muchos casos, cargos más altos.

---

## Recomendaciones (basadas en este análisis)

* Incentivar contratos anuales o bianuales con descuentos.
* Mejorar la experiencia de Internet (agregar valor con seguridad, soporte, etc.).
* Revisar los casos N/A en churn para mejorar la calidad de los datos.
* Seguir con modelos predictivos usando `datos_tratados.csv`.

---

## Limitaciones

* No incluí la matriz de correlación completa.
* Los 224 casos N/A pueden sesgar los resultados.
* Falta aplicar un modelo predictivo en esta versión del notebook.

---

## Próximos Pasos

* Calcular correlaciones para validar relaciones.
* Entrenar modelos de Machine Learning (Logistic Regression, Random Forest, etc.).
* Segmentar mejor clientes (ej. por edad, dependientes, senior citizens).

---

## Contacto

Si quieres comentar, contribuir o dar feedback, puedes escribirme directamente en GitHub: [anagonesca](https://github.com/anagonesca).

---

**Última actualización**: 17 de agosto de 2025
**Autor**: [anagonesca](https://github.com/anagonesca)

