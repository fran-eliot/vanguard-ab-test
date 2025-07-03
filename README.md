# 📊 Vanguard A/B Test – Proyecto de Experimento Digital

![Status](https://img.shields.io/badge/status-Finalizado-brightgreen)
![Python](https://img.shields.io/badge/python-3.10-blue)
![Notebooks](https://img.shields.io/badge/jupyter-Notebook-orange)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Last Commit](https://img.shields.io/github/last-commit/fran-eliot/vanguard-ab-test)
![Repo Size](https://img.shields.io/github/repo-size/fran-eliot/vanguard-ab-test)

## 🧠 Descripción del proyecto

Este proyecto analiza un experimento A/B llevado a cabo por el equipo de Customer Experience de **Vanguard**, una de las gestoras de inversión más importantes de EE.UU.

El objetivo fue evaluar si un **nuevo diseño digital**, junto con mensajes contextualizados durante el proceso online, mejoraba la **experiencia de usuario** y **aumentaba la tasa de finalización** respecto al diseño anterior.

---

## 🎯 Objetivos del análisis

- 🧪 Evaluar el impacto del nuevo diseño en la tasa de finalización del proceso online.
- 📊 Explorar diferencias de comportamiento digital entre usuarios de los grupos Control y Test.
- 📉 Analizar la interacción paso a paso, abandono y comportamiento por perfil de cliente.
- 📈 Realizar tests de hipótesis para validar estadísticamente los hallazgos.
- 📌 Ofrecer recomendaciones basadas en datos reales y visualizaciones claras.

---

## 📁 Estructura del repositorio

```plaintext
vanguard-ab-test/
├── data/
│   ├── raw/         # Datos originales descargados
│   └── processed/   # Datos limpios y fusionados
├── notebooks/       # Jupyter Notebooks con el análisis
├── PowerBI/         # Dashboard interactivo
├── slides/          # Presentación final
├── src/             # Funciones auxiliares
├── README.md        # Este archivo
└── requirements.txt # Librerías necesarias
```

---

## 🧾 Datasets utilizados

| Dataset                        | Descripción |
|--------------------------------|-------------|
| `df_final_demo`                | Datos demográficos y relación con Vanguard (edad, género, saldo, etc.) |
| `df_final_web_data_pt_1/2`     | Trazabilidad digital: pasos realizados por cliente con timestamp |
| `df_final_experiment_clients`  | Grupo asignado (Control o Test) |

---

## 🧹 Limpieza y preparación de datos

- 🔍 **Valores nulos y duplicados**: eliminación o imputación según relevancia.
- 🧮 **Conversión de tipos**: fechas (`datetime`), categorías (`category`), etc.
- 🔗 **Fusión de datasets**: unión de las tres fuentes en un único dataframe.
- 🧪 **Filtrado de registros no válidos**: usuarios sin pasos digitales.
- ⚠️ **Tratamiento de outliers**: detección y gestión en `saldo`, `edad`, `duración`.
- 🧱 **Variables adicionales**: KPIs como número de pasos, duración, agrupación por edad.

---

## 📐 Métricas calculadas

- ✅ `conversion_rate`: usuarios que alcanzan el paso final (`step_15`).
- 🧭 `unique_steps_count`: número de pasos distintos realizados.
- 🔁 `total_steps_count`: pasos totales, incluidas repeticiones.
- ⏱️ `total_duration`: tiempo entre primer y último paso.
- ⏱️ `avg_time_between_steps`: tiempo medio entre pasos consecutivos.

Se calcularon por grupo experimental (Test / Control) y se usaron en los análisis estadísticos y visualizaciones.

---

## ✂️ Análisis de outliers y limpieza final

Antes de los tests estadísticos:

- Se identificaron valores extremos en duración (`> 8.600 seg`, percentil 77).
- Se decidió **filtrar solo por duración total**, para no generar inconsistencias en KPIs.
- Esta muestra filtrada permitió realizar análisis más representativos y robustos.

---

## 🧪 Hipótesis planteadas

1. **H₀**: La tasa de finalización es igual en Test y Control  
   **H₁**: Es mayor en el grupo Test

2. **H₀**: No hay diferencia en los pasos únicos completados  
   **H₁**: El grupo Test completa más pasos

3. **H₀**: El rediseño impacta igual a todos los perfiles  
   **H₁**: El efecto varía por edad y/o antigüedad

4. **H₀**: El tiempo total es igual en ambos grupos  
   **H₁**: El grupo Test tarda menos

5. **H₀**: El número total de pasos es igual  
   **H₁**: El grupo Test necesita menos pasos

6. **H₀**: El tiempo medio por paso es igual  
   **H₁**: El grupo Test navega más rápido

---

## 📊 Visualización en Power BI

> 📎 [Abrir dashboard interactivo](./PowerBI/vanguard_dashboard.pbix)

---

## 🗣️ Presentación del proyecto

> 🎤 [Ver presentación final (PDF)](./slides/Vanguard%20AB-Test.pdf)

---

## 🛠️ Librerías utilizadas

- `pandas`, `numpy`, `scipy.stats`, `statsmodels`
- `matplotlib`, `seaborn`, `plotly`
- `Jupyter Notebooks`

---

## 🚀 Cómo ejecutar este proyecto

1. Clona el repositorio:  
   ```bash
   git clone https://github.com/tuusuario/vanguard-ab-test.git
   ```

2. (Opcional) Crea un entorno virtual:  
   ```bash
   python -m venv venv && source venv/bin/activate
   ```

3. Instala las dependencias:  
   ```bash
   pip install -r requirements.txt
   ```

4. Ejecuta los notebooks en orden desde el directorio `notebooks/`

---

## 👥 Autores

- [Fran Ramírez](https://github.com/fran-eliot)  
- Fred Mpeso  
- [Andrés Muñoz](https://github.com/andreuti)

---

## 📄 Licencia

Proyecto desarrollado como parte del **Bootcamp de Data Analytics – Ironhack**, con fines educativos y no comerciales.