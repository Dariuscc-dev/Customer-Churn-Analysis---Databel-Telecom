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
