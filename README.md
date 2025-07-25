# 📊 Vanguard A/B Test – Proyecto de Experimento Digital

![Python](https://img.shields.io/badge/python-3.10-blue)
![Jupyter](https://img.shields.io/badge/Jupyter_Notebooks-%E2%9C%94-orange)
![Pandas](https://img.shields.io/badge/Pandas-1.5%2B-lightgrey)
![License: Educational](https://img.shields.io/badge/license-Educational-informational)
![Last Commit](https://img.shields.io/github/last-commit/fran-eliot/vanguard-ab-test)
![Repo Size](https://img.shields.io/github/repo-size/fran-eliot/vanguard-ab-test)

---

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

- 🔍 Eliminación de valores nulos y duplicados
- 🧮 Conversión de tipos (`datetime`, `category`, etc.)
- 🔗 Fusión de datasets en un único dataframe
- 🧪 Filtrado de registros inválidos (sin pasos digitales)
- ⚠️ Gestión de outliers (edad, saldo, duración)
- 🧱 Creación de KPIs adicionales

---

## 📐 Métricas calculadas

- ✅ `conversion_rate`: usuarios que alcanzan el paso final (`step_15`)
- 🧭 `unique_steps_count`: pasos únicos realizados
- 🔁 `total_steps_count`: pasos totales (incluyendo repeticiones)
- ⏱️ `total_duration`: tiempo entre primer y último paso
- ⏱️ `avg_time_between_steps`: tiempo medio entre pasos consecutivos

---

## ✂️ Análisis de outliers

- Se identificaron usuarios con sesiones abiertas durante días
- Se filtró la muestra por duración total (`p77` ≈ 8600 seg)
- Esto permitió análisis más representativos sin distorsión de KPIs

---

## 🧪 Hipótesis planteadas

1. ✅ **El nuevo diseño mejora la tasa de finalización** (p < 0.001)
2. ✅ **Mayor número de pasos únicos en Test** (Mann-Whitney U, p < 0.001)
3. ❌ **No hay diferencias significativas por perfil** (edad, antigüedad)
4. ✅ **El grupo Test navega más rápido** (p < 0.001)
5. ✅ **Navegación más eficiente en Test** (más pasos sin mayor duración)
6. ✅ **Fluidez superior en Test** (tiempo medio por paso menor)

---

## 📌 Principales KPIs

| KPI                       | Descripción |
|---------------------------|-------------|
| ✅ Tasa de finalización   | Finaliza el proceso (`step_15`) |
| 🧭 Pasos únicos           | Distintos pasos completados |
| 🔁 Pasos totales          | Incluye repeticiones y retrocesos |
| ⏱️ Duración total         | Tiempo total del proceso |
| ⏱️ Tiempo medio por paso  | Tiempo promedio entre pasos |
| 👥 Segmentación           | Análisis por edad, antigüedad y género |

---

## 📊 Visualización en Power BI

> 📎 [Abrir dashboard interactivo localmente con PowerBI Desktop](./PowerBI/vanguard_dashboard.pbix)
    ⚠️ Requiere Power BI Desktop para visualizarlo.

---

## 🗣️ Presentación del proyecto

> 🎤 [Ver presentación resumen (PDF)](./slides/Vanguard%20AB-Test.pdf)

---

## 📌 Conclusiones generales

### ✅ Impacto positivo del rediseño

- Tasa de finalización Test: **68%**, Control: **64%**
- Mejora significativa (*p* < 0.001)

### 🧠 Cambios en el comportamiento digital

- Más pasos únicos y navegación más fluida en Test
- No reduce duración total, pero mejora la experiencia

### 👥 Diferencias por perfil

- Jóvenes (18–30) y nuevos clientes: mayor beneficio
- Usuarios veteranos: menor efecto

### 🧩 Robustez analítica

- Filtrado de outliers por duración
- Uso de tests estadísticos adecuados según distribución

---

## 📌 Recomendaciones finales

| Recomendación                                | Motivo                                                       |
|---------------------------------------------|--------------------------------------------------------------|
| ✅ **Desplegar el nuevo diseño**             | Mejora probada en tasa de finalización y experiencia digital |
| 📊 **Monitorizar por segmentos**             | Detectamos mayor efecto en jóvenes y perfiles recientes      |
| 🧪 **Ampliar test a procesos similares**     | El enfoque funciona y puede trasladarse a otros journeys     |
| 🧠 **Complementar con análisis cualitativo** | Para entender por qué ciertos perfiles no mejoran tanto      |

---

## 🛠️ Librerías utilizadas

- `pandas`, `numpy`, `scipy.stats`, `statsmodels`
- `matplotlib`, `seaborn`, `plotly`
- `Jupyter Notebooks`

---

## 🚀 Cómo ejecutar este proyecto

```bash
git clone https://github.com/fran-eliot/vanguard-ab-test.git
cd vanguard-ab-test
python -m venv venv && source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Luego, abre y ejecuta los notebooks en orden desde el directorio `notebooks/`.

---

## 👥 Autores

- [Fran Ramírez](https://github.com/fran-eliot)  
- Fred Mpeso  
- [Andrés Muñoz](https://github.com/andreuti)

---

## 📄 Licencia

Proyecto desarrollado para el **Bootcamp de Data Analytics – Ironhack**, con fines educativos. No representa a la empresa Vanguard ni está destinado a uso comercial.