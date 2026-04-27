# IBM Data Analyst Capstone Project: Developer Survey Analysis

This repository contains the data preparation methodology and final dashboard visualizations for the IBM Data Analyst Capstone Project. The project analyzes Stack Overflow survey data to identify current technology usage, future industry trends, and developer demographics.

---

## 🏗️ Methodology: Data Preparation

The primary challenge of this project involved processing multi-select survey responses. Participants often selected multiple technologies for a single question, resulting in semicolon-separated strings (e.g., `Java;Python;SQL`). 

To ensure accurate analysis without overwhelming system resources, the following steps were taken:

### 1. Handling Multi-Select Columns
To prevent a combinatorial explosion of rows—which occurs if multiple multi-select columns are exploded simultaneously—the data was split into **eight separate "mini-dataframes"**:
* **Explosion Strategy**: Each technology category (Languages, Databases, Platforms, and Webframes) for both "Worked With" and "Want to Work With" was isolated and exploded into individual rows.
* **Complexity Control**: This approach avoided the $O(N \cdot M^K)$ row generation issue, ensuring the dataset remained clean and the processing time manageable.

### 2. Data Cleaning & Label Trimming
* **Duplicate Removal**: Duplicate rows were identified and removed to maintain data integrity.
* **Label Mapping**: For better dashboard aesthetics, long categorical strings were mapped to shorter aliases (e.g., shortening "Bachelor's degree (B.A., B.S., B.Eng., etc.)" to "**Bachelor**").

---

## 📊 Dashboard Insights

### 1. Current Technology Usage
Visualizes the current landscape of the developer ecosystem:
* **Top Languages**: **JavaScript** leads the market (14,943 users), followed by **SQL** and **HTML/CSS**.
* **Top Databases**: **PostgreSQL** is the most utilized database (11,514), significantly ahead of **MySQL** and **SQLite**.
* **Cloud Platforms**: **AWS**, **Google Cloud**, and **MS Azure** are the dominant industry leaders.

### 2. Future Technology Trends
Highlights where the industry is heading based on developer aspirations:
* **Desired Languages**: **JavaScript** and **SQL** remain top priorities, with high interest in **TypeScript** and **Python**.
* **Desired Databases**: **PostgreSQL** remains the most "wanted" database (12,193), with **Redis** and **MongoDB** showing strong future momentum.
* **Frameworks**: **React** and **Node.js** are the most sought-after web frameworks for future projects.

### 3. Demographics
A breakdown of the survey's global respondent profile:
* **Age**: The largest demographic is the **25-34** age group (41.3%), followed by **35-44** (27.3%).
* **Education**: The majority of developers hold a **Bachelor's degree** (8,629) or a **Master's degree** (5,000).
* **Global Reach**: Participation spans the globe, with high concentrations in North America, Europe, and India.

---

## 🛠️ Tech Stack
* **Language**: Python (Pandas)
* **Environment**: Jupyter Notebook
* **Visualization**: Dashboarding software (IBM Cognos)
* **Data Source**: Stack Overflow Developer Survey Data
