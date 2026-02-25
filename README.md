# Customer Churn Analysis - Databel Telecom

**Tech Stack:** Power BI, DAX, Data Modeling, Data Visualization.

---

## 📄 Problem Statement
Databel (a fictional telecom company from a DataCamp and Microsoft case study) had a serious issue: **almost 27% of their customers were churning.**

My goal for this project wasn't just to report that number, but to dive deep into the data to figure out why people were leaving and what could be done to stop it.

---

## 🛠 How I did it (Personal workflow)
I went hands-on with the dataset from start to finish:

* **Data Validation:** I ran a quick Data Check to ensure data integrity (making sure unique vs. total customers made sense).
* **Writing DAX:** I built out the core measures needed, like the exact **Churn Rate**, total lost customers, and averages for extra charges.
* **Slicing and Dicing:** Created custom calculated columns to segment the user base (age brackets, contract types, and tiered monthly data usage).
* **Telling the Story:** Designed a multi-page interactive dashboard to guide the user from high-level overviews to nitty-gritty details.

---

## 💡 Technical Highlight: Clean DAX
To keep the model scalable and readable, I avoided nested `IF` statements when grouping data. Instead, I used `SWITCH(TRUE())`:

```dax
Grouped Consumption = 
SWITCH(
    TRUE(),
    'Databel - Data'[Avg Monthly GB Download] < 5, "Less than 5 GB",
    'Databel - Data'[Avg Monthly GB Download] >= 5 && 'Databel - Data'[Avg Monthly GB Download] < 10, "Between 5 & 10 GB",
    'Databel - Data'[Avg Monthly GB Download] >= 10, "10 or more GB"
)

---

## 📈 Key Insights
After the analysis, three main things stood out:

1.  **Competitors vs. Support:** People leave mostly for competitor offers, but bad customer support is often the final straw. There is a direct correlation: more support calls = higher churn probability.
2.  **The Month-to-Month Trap:** Customers on monthly plans show a massive **46% churn rate**, while yearly contracts only show 6%.
3.  **The Senior Demographic:** Users classified as "Senior" have a noticeably higher churn rate compared to the under-30 crowd.

---

## 📂 Want to check it out?
If you'd like to interact with the dashboard or look under the hood at my data model, you can find the `.pbix` files in this repository.

---

# 🇪🇸 Versión en Español

## Análisis de Churn de Clientes - Databel Telecom

**Stack Tecnológico:** Power BI, DAX, Modelado de Datos, Visualización de Datos.

---

## 📄 Planteamiento del Problema
[cite_start]Databel (una empresa ficticia de telecomunicaciones de un caso de estudio de DataCamp y Microsoft [cite: 65]) enfrentaba un problema crítico: **casi el 27% de sus clientes abandonaban la compañía (churn).**

[cite_start]Mi objetivo no era solo reportar la cifra, sino profundizar en los datos para identificar las causas del abandono y proponer soluciones estratégicas basándome en mi formación en marketing y análisis[cite: 28, 30].

---

## 🛠 Metodología (Flujo de trabajo)
Gestioné el dataset de principio a fin:

* **Validación de Datos:** Verificación de integridad para asegurar que la relación entre clientes únicos y totales fuera coherente.
* **Escritura de DAX:** Creé las medidas core, como la **Tasa de Churn** exacta, total de clientes perdidos y promedios de cargos adicionales.
* **Segmentación:** Utilicé columnas calculadas para agrupar usuarios por rangos de edad, tipo de contrato y niveles de consumo de datos.
* **Storytelling Visual:** Diseñé un dashboard interactivo de varias páginas para guiar al usuario desde una visión general hasta los detalles específicos de la fuga de clientes.

---

## 💡 Highlight Técnico: DAX Limpio
Para mantener el modelo escalable y legible, evité el uso de múltiples `IF` anidados al agrupar datos, optando por la función `SWITCH(TRUE())`:

```dax
Grouped Consumption = 
SWITCH(
    TRUE(),
    'Databel - Data'[Avg Monthly GB Download] < 5, "Menos de 5 GB",
    'Databel - Data'[Avg Monthly GB Download] >= 5 && 'Databel - Data'[Avg Monthly GB Download] < 10, "Entre 5 y 10 GB",
    'Databel - Data'[Avg Monthly GB Download] >= 10, "10 GB o más"
)
