# Legume Nutrient Dashboard

The **Legume Nutrient Dashboard** is an interactive visualization tool developed for a STAT 386 final project.  
It uses USDA FoodData Central API data (Foundation Foods) to collect, clean, and visualize nutrient profiles for legume products.  
The project includes a full API ingestion pipeline, nutrient extraction logic, a cleaning pipeline, and a Streamlit dashboard for exploration.

---

The project retrieves data from the USDA FoodData Central API, focusing on:
Category: "Legumes and Legume Products"
Data type: "Foundation" foods only

The data pipeline is implemented inside main.py and includes the following stages:

### **1. Install dependencies**

This project uses **uv** for environment and dependency management:

```bash
uv sync
uv run pytest
```

### **2. Generate the cleaned dataset**
The main script calls the USDA API, extracts nutrients, cleans and formats the data, and outputs:
legus_cleaned.csv
Run:
uv run python main.py
This requires an api.txt file stored in the project root containing a valid USDA API key.

### **3. Launch the Streamlit app**
uv run streamlit run src/final_project_demo/streamlit_app.py

The project retrieves data from the USDA FoodData Central API, focusing on:
Category: "Legumes and Legume Products"
Data type: "Foundation" foods only

The data pipeline is implemented inside main.py and includes the following stages:

## **Dashboard Features (Streamlit)**
The dashboard loads the cleaned dataset and provides three main interactive components.
### **1. Legume Selector**
Choose a legume category from the sidebar.

### **2. Radar Chart**
Displays average nutrient content for:
Protein
Fat
Carbs
Starch
Iron
Magnesium
Phosphorus
Potassium
Sodium
Zinc
Copper
Manganese
This allows comparison across nutrient groups visually.

### **3. Correlation Heatmap**
An interactive Plotly heatmap showing nutrient correlations across all legumes.

### **4. Dataset Preview
A full data table of the cleaned dataset for transparency and exploration.

### **Technologies Used
Python 3.11+
Streamlit (dashboard)
pandas (data manipulation)
requests (API calls)
regex (nutrient and category extraction)
seaborn & matplotlib (bar chart & heatmap)
plotly (interactive Streamlit visualizations)
uv (environment & dependency management)