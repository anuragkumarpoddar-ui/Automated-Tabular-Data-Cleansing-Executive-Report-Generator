# 📊 Automated Tabular Data Cleansing & Executive Report Generator

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Manipulation-150458.svg)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Data%20Visualization-11557c.svg)
![Tkinter](https://img.shields.io/badge/Tkinter-GUI-orange.svg)

## 📌 Project Overview
The **Automated Tabular Data Cleansing & Executive Report Generator** (`CorporateReportBuilder`) is a Python-based desktop application designed to streamline ad-hoc data analysis and executive reporting[cite: 1]. 

In corporate environments, raw datasets frequently suffer from formatting inconsistencies—such as numeric values stored as strings with comma separators, unstandardized categorical text, and missing values[cite: 1]. This tool automates the ingestion, sanitization, aggregation, and visualization of raw tabular files (`.csv`, `.xlsx`, `.xls`), enabling users to generate clean summary tables and publication-ready charts through an intuitive graphical interface without writing a single line of code[cite: 1].
<img width="1370" height="910" alt="Screenshot 2026-10-23 005321" src="https://github.com/user-attachments/assets/cb8f4962-08a9-4480-9406-e4217ab27f33" />


---

## ✨ Key Features

### 1. Intelligent Data Ingestion & Heuristic Type Detection
* **Multi-Format Support:** Seamlessly loads both CSV (`.csv`) and Microsoft Excel (`.xlsx`, `.xls`) datasets[cite: 1].
* **Instant Metadata Profiling:** Automatically extracts and displays dataset dimensions (row and column counts) alongside a complete list of column headers upon ingestion[cite: 1].
* **Heuristic Numeric Recognition:** Goes beyond standard data-type checking by scanning `object` (string) columns and identifying numeric-like columns (where at least 60% of the records or a minimum threshold of rows can be safely parsed as numbers after stripping formatting)[cite: 1].

### 2. Automated Data Cleansing Pipeline
* **String Standardization:** Automatically cleans categorical grouping columns by stripping leading/trailing whitespaces and standardizing values to `Title Case` to prevent duplicate grouping keys caused by casing or spacing typos[cite: 1].
* **Safe Numeric Coercion:** Strips comma separators (e.g., converting `"12,000"` to `12000.0`), coerces corrupted or non-convertible entries into `NaN`, and automatically drops null records prior to aggregation to ensure mathematical integrity[cite: 1].

### 3. Dynamic Aggregation & Report Building
* **Interactive GroupBy Engine:** Allows dynamic selection of categorical grouping dimensions and numeric target metrics via auto-populated dropdown menus[cite: 1].
* **Comprehensive Statistical Functions:** Supports **Sum**, **Mean / Average**, **Median**, **Max**, **Min**, and **Count** aggregations[cite: 1].
* **Formatted Live Preview:** Automatically sorts results in descending order by metric value and renders them in a scrollable `Treeview` table with standardized thousand-separator and two-decimal precision (`1,234.56`)[cite: 1].

### 4. Executive Chart Builder
* **Embedded Canvas:** Uses Matplotlib's `FigureCanvasTkAgg` backend to render interactive visualizations directly inside the application window[cite: 1].
* **Multiple Chart Types:** Supports **Bar** (horizontal), **Column** (vertical), **Line** (with data markers), and **Pie** charts (with automated percentage labels)[cite: 1].
* **Smart Visual Slicing:** Automatically limits Bar, Column, and Line charts to the **Top 10** categories and Pie charts to the **Top 6** categories to prevent label overlapping and maintain executive readability[cite: 1].

### 5. One-Click Export System
* **Tabular Exports:** Exports the cleansed, aggregated summary report directly to the source file's directory as either an Excel workbook (`report_output.xlsx`) or a CSV file (`report_output.csv`)[cite: 1].
* **High-Resolution Visuals:** Saves the generated visualization as a high-resolution PNG (`chart_output.png` at **200 DPI**), ready for immediate inclusion in slide decks or executive summaries[cite: 1].

---

## 🛠️ Tech Stack & Dependencies
* **Language:** Python 3.x[cite: 1]
* **GUI Framework:** `tkinter` (`ttk`, `filedialog`, `messagebox`)[cite: 1]
* **Data Manipulation:** `pandas`, `openpyxl` (for Excel I/O operations)[cite: 1]
* **Data Visualization:** `matplotlib` (`TkAgg` backend)[cite: 1]

---


## 📖 How to Use (Workflow)
1.Select & Read File: Click Browse to choose a .csv, .xlsx, or .xls file from your local machine, then click Read to load the dataset and view its structure in the File Info panel[cite: 1].

2.Configure Aggregation:

Choose a categorical column from the Group By (Text column) dropdown[cite: 1].

Select your desired calculation from the Aggregation dropdown (Sum, Mean, Median, Max, Min, Count)[cite: 1].

Choose a metric column from the Value (Numeric column) dropdown[cite: 1].

3.Preview & Export Report: Click Preview Report to cleanse the data and populate the summary table[cite: 1]. Select your preferred format (Excel (.xlsx) or CSV (.csv)) and click Export Report[cite: 1].

4.Generate & Export Visuals: Select a visualization style (Bar, Column, Pie, or Line) and click Preview Chart[cite: 1]. Click Export Chart (PNG) to save a high-DPI image to your working directory[cite: 1].

## 📂 Project Architecture

├── CorporateReportBuilder (Main Application Class)

│   ├── _build_ui()              # Initializes Tkinter frames, dropdowns, Treeview, and chart containers

│   ├── _safe_numeric_convert()  # Strips formatting characters and coerces strings to numeric values

│   ├── browse_file()            # Handles OS file selection dialog

│   ├── read_file()              # Loads data, profiles shape/columns, and runs heuristic column classification

│   ├── preview_report()         # Executes string cleansing, null removal, GroupBy aggregation, and sorting

│   ├── _render_table()          # Formats floats and updates the Tkinter Treeview widget

│   ├── preview_chart()          # Slices top N records and renders Matplotlib figures onto the GUI canvas

│   ├── export_report()          # Writes aggregated DataFrames to .xlsx or .csv in the source directory

│   └── export_chart()           # Exports the active Matplotlib figure as a 200 DPI .png file

## 🔮 Future Enhancements
Multi-Level Grouping: Support grouping by multiple categorical columns simultaneously.

Custom Filtering: Add pre-aggregation filter controls (e.g., date range pickers or value thresholds).

Automated PDF/PPTX Generation: Bundle both the summary table and chart into a single downloadable PDF executive summary.

## 👨‍💻 Author
**Anurag Kumar Poddar**  
Data Analyst | Python | SQL | Power BI | Data Visualization

🔗 [GitHub Profile](https://github.com/anuragkumarpoddar-ui)  
🔗 [LinkedIn Profile](https://www.linkedin.com/in/anurag-kumar-poddar-51239596/)

---
⭐ If you find this project useful, feel free to explore the repository!
