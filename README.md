# 📊 Vanguard A/B Test – Proyecto de Experimento Digital

## 🧠 Descripción del proyecto

Este proyecto analiza un experimento A/B llevado a cabo por el equipo de Customer Experience de **Vanguard**, una de las gestoras de inversión más importantes de EE.UU.

El objetivo del experimento fue evaluar si un **nuevo diseño de la interfaz digital**, acompañado de mensajes contextualizados durante el proceso online, conseguía **mejorar la experiencia de usuario** y **aumentar la tasa de finalización** del proceso online en comparación con el diseño anterior.

---

## 📁 Estructura del repositorio

\`\`\`plaintext
vanguard-ab-test/
├── data/
│   ├── raw/         # Datos originales descargados
│   └── processed/   # Datos limpios y fusionados
├── kanban/          # Tablero de seguimiento (Trello)
├── notebooks/       # Jupyter Notebooks con el análisis
├── PowerBI/         # Dashboard interactivo en Power BI
├── slides/          # Presentación final
├── src/             # Funciones auxiliares reutilizables
├── README.md        # Este archivo
└── requirements.txt # Librerías necesarias
\`\`\`

---

## 🧾 Datasets utilizados

| Dataset                        | Descripción |
|--------------------------------|-------------|
| \`df_final_demo\`                | Información demográfica y relación con Vanguard (edad, género, saldo, llamadas, logins...) |
| \`df_final_web_data_pt_1/2\`     | Trazabilidad digital: pasos realizados por cada cliente con timestamp |
| \`df_final_experiment_clients\`  | Grupo asignado en el experimento (control o test) |

---

## 🎯 Objetivos del análisis

- 🧪 **Evaluar el impacto del nuevo diseño** en la tasa de finalización del proceso online.
- 📊 **Explorar diferencias de comportamiento** digital entre usuarios del grupo control y test.
- 📉 **Analizar la interacción paso a paso**, el abandono y el comportamiento por perfil de cliente.
- 📈 **Realizar test de hipótesis** para validar estadísticamente las diferencias encontradas.
- 📌 **Ofrecer recomendaciones finales** basadas en datos reales y visualizaciones claras.

---

## 📌 Principales KPIs analizados

- ✅ **Tasa de finalización del proceso online**  
  Proporción de usuarios que alcanzan el paso de confirmación.

- 🧭 **Número de pasos únicos completados por cliente**  
  Cuántos pasos distintos (`step_1`, `step_2`…) ha alcanzado cada cliente.

- 🔁 **Número total de pasos realizados** (incluyendo repeticiones y retrocesos)  
  Cuántas veces un cliente navegó entre pasos, incluso si repitió alguno.

- ⏱️ **Duración total del proceso**  
  Tiempo en segundos entre el primer y el último `process_step` registrado para un cliente.

- ⏱️ **Tiempo medio por paso**  
  Tiempo promedio (en segundos) entre pasos consecutivos de un mismo cliente.

- 🧓 **Segmentación de resultados por edad, género, saldo, antigüedad...**  
  Comparación de comportamiento y resultados entre distintos perfiles.

---

## 🧪 Hipótesis planteadas

1. **H₀**: La tasa de finalización es igual en Test y Control  
   **H₁**: La tasa de finalización es mayor en el grupo Test

2. **H₀**: No hay diferencia en los pasos únicos completados  
   **H₁**: El grupo Test completa más pasos distintos que el grupo Control

3. **H₀**: El rediseño impacta igual a todos los perfiles  
   **H₁**: El efecto varía según edad y/o antigüedad del cliente.

4. **H₀**: El tiempo total del proceso es igual en ambos grupos  
   **H₁**: El grupo Test completa el proceso en menos tiempo

5. **H₀**: No hay diferencia en el número total de pasos (con repeticiones) entre grupos  
   **H₁**: El grupo Test necesita menos pasos totales para completar el proceso

6. **H₀**: No hay diferencia en el tiempo medio por paso entre grupos  
   **H₁**: El grupo Test navega más rápido entre pasos


---

## 📊 Visualización en PowerBI

> 🧭 Visualización interactiva del análisis:  
> [Abrir dashboard en Power BI](./PowerBI/vanguard_dashboard.pbix)

---

## 📂 Presentación final

> 🎤 Presentación resumida del proyecto:  
> [Ver en Canva](#)

---

## 🛠️ Librerías utilizadas

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scipy.stats`
- `statsmodels`
- `plotly`
- `Jupyter Notebooks`

---

## 🚀 Cómo ejecutar este proyecto

1. Clona el repositorio  
   \`git clone https://github.com/tuusuario/vanguard-ab-test.git\`

2. (Opcional) Crea un entorno virtual  
   \`python -m venv venv && source venv/bin/activate\`

3. Instala las dependencias  
   \`pip install -r requirements.txt\`

4. Ejecuta los notebooks en orden desde el directorio \`notebooks/\`

---

## 👥 Autores

- [Fran Ramírez](https://github.com/fran-eliot)  
- Fred Mpeso  
- [Andrés Muñoz](https://github.com/andreuti)  

---

## 📄 Licencia

Proyecto desarrollado como parte del **Bootcamp de Data Analytics – Ironhack**, con fines educativos y no comerciales.

