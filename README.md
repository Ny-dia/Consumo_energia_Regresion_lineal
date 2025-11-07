# ⚡ Predicción de Consumo de Energía con Regresión Lineal

## 💡 Descripción del Proyecto

Este proyecto es un análisis de Machine Learning que utiliza el algoritmo de **Regresión Lineal Múltiple** para modelar y predecir el **Consumo de Energía (PE)** de una planta, basándose en variables ambientales.

El objetivo fue seleccionar el subconjunto óptimo de variables predictoras que maximizara el rendimiento predictivo y la **confiabilidad** del modelo, mitigando el problema de la **Multicolinealidad**.

---

## 🛠️ Tecnologías y Requisitos

Este proyecto fue desarrollado en **Python** dentro de un entorno **Jupyter Notebook**.

| Categoría | Librerías |
| :--- | :--- |
| **Análisis de Datos** | `pandas`, `numpy` |
| **Visualización** | `matplotlib.pyplot`, `seaborn`, `plotly.express` |
| **Machine Learning/Estadística** | `sklearn`, `statsmodels` (para OLS y VIF) |

### Requisitos de Instalación

Puedes instalar las dependencias clave usando `pip`:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels plotly
````

-----

## 🚀 Uso y Ejecución

El análisis completo está contenido en el cuaderno de Jupyter `Consumo_energia_Regresion_lineal.ipynb`.

1.  **Clonar el repositorio:**
    ```bash
    git clone [https://github.com/Ny-dia/Consumo_energia_Regresion_lineal.git](https://github.com/Ny-dia/Consumo_energia_Regresion_lineal.git)
    ```
2.  **Abrir el Notebook:**
    ```bash
    jupyter notebook Consumo_energia_Regresion_lineal.ipynb
    ```

-----

## 📊 Metodología del Análisis y Resultados Clave

El flujo de trabajo se centró en la creación de tres modelos de regresión lineal y su validación:

### Fases Clave

1.  **Exploración de Datos (EDA):** Uso de `sns.pairplot` para visualizar distribuciones, relaciones entre variables y posibles problemas de correlación/multicolinealidad.
2.  **División de Datos:** El dataset se dividió con un `test_size=0.3` (30% para prueba).
3.  **Modelado y Evaluación (OLS):** Se crearon y compararon tres modelos:
      * **Modelo 0 (Completo):** Incluyendo `AT, V, AP, RH`.
      * **Modelo 1 (Viento/Humedad):** Incluyendo `V, RH`.
      * **Modelo 2 (Temperatura/Presión):** Incluyendo `AT, AP`.
4.  **Validación de Multicolinealidad:** Cálculo del **Factor de Inflación de Varianza (VIF)** para evaluar la estabilidad de los coeficientes.
5.  **Análisis de Residuos:** Inspección gráfica de los residuos para confirmar la **Homocedasticidad** (varianza constante del error).

### Conclusiones del Modelo Ganador (Modelo 2)

El **Modelo 2** (usando **AT** y **AP**) fue seleccionado como el mejor debido a su balance entre poder predictivo y confiabilidad estadística.

| Métrica | Valor del Modelo 2 | Justificación |
| :--- | :--- | :--- |
| **R² (Uncentered)** | **1.000** | Máximo poder explicativo. |
| **VIF (AT, AP)** | **7.80** | Nivel aceptable de multicolinealidad ($\text{VIF} < 10$). |
| **Relación Predictiva** | $\text{PE} = -1.9713 \cdot \text{AT} + 0.4866 \cdot \text{AP}$ | Muestra que **AT** es el predictor más fuerte (efecto negativo). |
| **Residuos** | Gráfico Homocedástico | El gráfico de dispersión de residuos indica que no hay heterocedasticidad, validando las suposiciones del OLS. |

-----

## 🧑 Autor

  * **Ny-dia** - [Enlace a tu perfil de GitHub](https://www.google.com/search?q=https://github.com/Ny-dia)

<!-- end list -->

```
```
