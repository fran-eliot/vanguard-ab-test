# 📊 Vanguard A/B Test – Proyecto de Experimento Digital

![Python](https://img.shields.io/badge/python-3.10-blue)
![Jupyter](https://img.shields.io/badge/Jupyter_Notebooks-%E2%9C%94-orange)
![Pandas](https://img.shields.io/badge/Pandas-1.5%2B-lightgrey)
![License: Educational](https://img.shields.io/badge/license-Educational-informational)
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

- Se detectaron usuarios que dejaban el proceso abierto durante días, generando valores extremos.
- Se identificaron valores extremos en duración (`> 8.600 seg`, percentil 77).
- Se decidió **filtrar solo por duración total**, para no generar inconsistencias en KPIs.
- Esta muestra filtrada permitió realizar análisis más representativos y robustos.

---

## 🧪 Hipótesis planteadas

1. **H₀**: La tasa de finalización es igual en Test y Control  
   ✅ Rechazada → Test tiene una mayor tasa de finalización (test z-proporciones, p < 0.05)
   **H₁**: Es mayor en el grupo Test

2. **H₀**: No hay diferencia en los pasos únicos completados  
   ✅ Rechazada → El grupo Test visita más pasos distintos (Mann-Whitney U)
   **H₁**: El grupo Test completa más pasos

3. **H₀**: El rediseño impacta igual a todos los perfiles  
   ❌ No rechazada → No hay diferencias significativas por edad o antigüedad
   **H₁**: El efecto varía por edad y/o antigüedad

4. **H₀**: El tiempo total es igual en ambos grupos  
   ✅ Rechazada → Test completa el proceso en menos tiempo
   **H₁**: El grupo Test tarda menos

5. **H₀**: El número total de pasos es igual
   ✅ Rechazada → El grupo Test navega con mayor eficiencia
   **H₁**: El grupo Test necesita menos pasos

6. **H₀**: El tiempo medio por paso es igual  
   ✅ Rechazada → El grupo Test muestra mayor fluidez
   **H₁**: El grupo Test navega más rápido

---

## 🧾 Análisis detallado

Se emplearon:

- Histogramas, boxplots y distribuciones

- Tests estadísticos no paramétricos (U de Mann-Whitney, Kruskal-Wallis)

- Test de proporciones para tasa de conversión

- Segmentaciones por edad, género y saldo

---

## 📌 Principales KPIs

| KPI                       | Definición |
|---------------------------|------------|
| ✅ Tasa de finalización   | ¿Finalizó el proceso? |
| 🧭 Pasos únicos           | Pasos distintos alcanzados |
| 🔁 Total de pasos         | Incluye repeticiones y retrocesos |
| ⏱️ Duración total         | Tiempo entre primer y último paso |
| ⏱️ Tiempo medio por paso  | Fluidez del proceso |
| 👥 Segmentación           | Comparativa por perfil de cliente |

---

## 📊 Visualización en Power BI

> 📎 [Abrir dashboard interactivo localmente con PowerBI Desktop](./PowerBI/vanguard_dashboard.pbix)

---

## 🗣️ Presentación del proyecto

> 🎤 [Ver presentación resumida del proyecto (PDF)](./slides/Vanguard%20AB-Test.pdf)

---

## 🎯 Conclusiones finales

- ✅ El rediseño mejora significativamente la tasa de conversión

- ⏱️ Se reduce la duración total y el número de pasos necesarios

- 🧭 El flujo es más fluido e intuitivo

- 👤 No se observaron diferencias significativas entre perfiles

- 💡 Recomendación: desplegar el rediseño y seguir monitorizando la interacción digital

---

## 🛠️ Librerías utilizadas

- `pandas`, `numpy`, `scipy.stats`, `statsmodels`
- `matplotlib`, `seaborn`, `plotly`
- `Jupyter Notebooks`

---

## 🚀 Cómo ejecutar este proyecto

1. Clona el repositorio:  
   ```bash
   git clone https://github.com/fran-eliot/vanguard-ab-test.git
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

- Proyecto desarrollado como parte del **Bootcamp de Data Analytics – Ironhack**, con fines estrictamente educativos.

- No está destinado para uso comercial ni representa a la empresa Vanguard.