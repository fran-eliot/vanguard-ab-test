# 📊 Vanguard A/B Test – Proyecto de Experimento Digital

## 👥 Autores
- Fran Ramírez Martín
- Fred Mpeso
- Andrés Muñoz

## 🧠 Descripción del proyecto

Este proyecto analiza un experimento A/B llevado a cabo por el equipo de Customer Experience de **Vanguard**, una de las gestoras de inversión más importantes de EE.UU.

El objetivo del experimento fue evaluar si un **nuevo diseño de la interfaz digital**, acompañado de mensajes contextualizados durante el proceso online, conseguía **mejorar la experiencia de usuario** y **aumentar la tasa de finalización** del proceso online en comparación con el diseño anterior.

---

## 📁 Estructura del repositorio

vanguard-ab-test/
├── data/
│ ├── raw/ # Datos originales descargados
│ └── processed/ # Datos limpios y fusionados
├── kanban/ # Enlace al tablero de Trello
├── notebooks/ # Notebooks principales del análisis
├── PowerBI/ # Dashboard de PowerBI
├── slides/ # Presentación final (enlace)
├── src/ # Funciones reutilizables en .py
├── README.md # Este archivo
└── requirements.txt # Librerías necesarias


---

## 🧾 Datasets utilizados

| Dataset                       | Descripción |
|-------------------------------|-------------|
| `df_final_demo`               | Información demográfica y relación con Vanguard (edad, género, saldo, llamadas, logins…) |
| `df_final_web_data_pt_1/2`    | Navegación digital: pasos realizados por los usuarios, con timestamp |
| `df_final_experiment_clients` | Información de pertenencia al grupo de control o test |

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
  Proporción de clientes que alcanzan el paso de confirmación.

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

> Link al dashboard interactivo: [Enlace aquí](#)

---

## 📂 Presentación final

> Link a Canva: [Enlace aquí](#)


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

1. Clonar el repositorio
2. Crear un entorno virtual (opcional)
3. Instalar dependencias con:  
   `pip install -r requirements.txt`
4. Ejecutar los notebooks en orden numérico dentro del directorio `notebooks/`

---

## 📄 Licencia

Este proyecto ha sido desarrollado en el contexto del Bootcamp de Data Analytics en Ironhack.

