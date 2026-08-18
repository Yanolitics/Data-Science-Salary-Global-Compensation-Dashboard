# 📊 Data Science Salary & Global Compensation Dashboard

Welcome to my career analytics repository! This project presents an end-to-end analytical tool and interactive executive dashboard engineered to evaluate global data science compensation, geographic salary disparities, and role-specific market rates.

Operating under the name **Yanolitics**, I developed this project to demonstrate how raw transactional workforce data can be transformed into high-impact, diagnostic career intelligence assets using advanced **Microsoft Excel** techniques—including dynamic array formulas, multi-criteria filtering, rigorous data validation, and custom visual layers.

---

## 🗺️ High-Level Project Workflow

The project follows a decoupled spreadsheet modeling workflow to ensure formula efficiency, clean interaction design, and optimal reporting speed:
`[Raw 2023 Job Logs]` ➔ `[Data Structuring & Cleaning]` ➔ `[Dynamic Array Modeling]` ➔ `[Data Validation Controls]` ➔ `[Interactive Executive Dashboard]`

---

## 🛠️ Stage-by-Step Project Breakdown

### 1. Data Ingestion & Schema Structuring
* **Purpose:** Loading and structuring raw global data science job records into normalized Excel Table structures (`jobs`).
* **Source Attributes:** Job titles, base/annual salaries (`salary_year_avg`), employment schedule types, geographic locations, and required tech stacks.
* **Data Hygiene:** Excluded zero-value records (`jobs[salary_year_avg] <> 0`) and sanitized schedule entries to prevent skewed metric calculations.

<!-- IMAGE PLACEHOLDER 1: Dataset Overview -->
<img width="850" height="400" alt="Raw Dataset and Table Structure" src="INSERT_YOUR_IMAGE_OR_GIF_URL_HERE" />
> **📸 Asset Recommendation:** Take a crisp screenshot showing the structured `jobs` Excel table with formatted column headers and numeric styling.

---

### 2. Analytical Engine: Dynamic Array & Logic Modeling
* **Purpose:** Building flexible calculation backends using advanced Excel logic to serve dynamic cross-filtering requirements.
* **Core Formula Architectures Implemented:**
  * **Multi-Criteria Median Salary Formula:** Evaluates median compensation dynamically across active selection filters (Job Title, Country, and Schedule Type).
    ```excel
    =MEDIAN(
      IF(
        (jobs[job_title_short]=A2)*
        (jobs[job_country]=country)*
        (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
        (jobs[salary_year_avg]<>0),
        jobs[salary_year_avg]
      )
    )
    ```
  * **Dynamic Unique Schedule Extractor:** Uses spill arrays (`#`) combined with string parsing to isolate standalone schedule types while filtering out noise.
    ```excel
    =FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
    ```

<!-- IMAGE PLACEHOLDER 2: Background Formula Calculation Tables -->
<img width="850" height="450" alt="Background Analytical Calculation Tables" src="INSERT_YOUR_IMAGE_OR_GIF_URL_HERE" />
> **📸 Asset Recommendation:** Take a screenshot of your background/working calculation sheet showcasing the dynamic array results and spill ranges (`J2#`).

---

### 3. User Interface & Data Validation Layer
* **Purpose:** Restricted UI input controls ensuring zero formula breakage and smooth visual exploration for end users.
* **Interaction Strategy:**
  * Applied **Excel Data Validation** linked directly to dynamic spill ranges for `Job Title`, `Country`, and `Schedule Type`.
  * Prevented invalid user entries, standardized parameter inputs, and eliminated broken calculation states.

<!-- GIF PLACEHOLDER 3: Interactive Data Validation Dropdowns -->
<img width="425" height="400" alt="Data Validation Dropdown Mechanics" src="INSERT_YOUR_GIF_URL_HERE" />
> **🎥 Asset Recommendation:** Record a 5-second GIF demonstrating clicking through the `Job Title` and `Country` drop-down menus and watching the values update cleanly.

---

### 4. Visual Layer: Interactive Executive Dashboard
* **Purpose:** Delivering visual market intelligence to job seekers, HR leaders, and analysts to drive data-backed negotiation strategies.
* **Visual Interface Modules:**
  * **Global Compensation Heatmap:** Interactive Excel Map Chart visualizing median salary distribution across international markets.
  * **Role-Based Salary Spectrum Bar Chart:** Sorted horizontal chart isolating compensation differences between entry, analyst, and engineering roles.
  * **Dynamic Parameter Cards:** KPI callouts driven by multi-criteria array formulas responding to user drop-downs in real time.

<!-- GIF PLACEHOLDER 4: Full Interactive Dashboard in Action -->
<img width="850" height="550" alt="Interactive Salary Dashboard Overview" src="INSERT_YOUR_GIF_URL_HERE" />
> **🎥 Asset Recommendation:** Record a short, high-quality GIF interacting with the full dashboard—changing drop-downs and showing both the bar chart and map updating simultaneously.

---

## 📊 Strategic Business Insights Uncovered

Through deep multi-variable exploration, this dashboard revealed notable compensation patterns that inform strategic career decisions:

🚨 **The Senior/Engineer Salary Cliff:** Across all geographic regions, Data Engineers and Senior Data Scientists command a **35%–50% median salary premium** over Data Analyst and Business Intelligence roles. Strategic skill positioning toward engineering frameworks yields higher direct revenue returns than pure reporting specializations.

* **Geographic Arbitrage Opportunities:** US and select European markets maintain significant baseline lead margins in average annual compensation, providing explicit targets for remote-first negotiations.
* **Schedule Type Valuation:** Contract and full-time configurations exhibit distinct median distributions depending on the target country, highlighting the importance of evaluating total compensation based on local schedule types.

---

## ⚡ Tech Stack & Core Concepts Demonstrated

* **Analytics Engine:** Microsoft Excel (Advanced Formulas & Dynamic Arrays)
* **Modeling Paradigms:** Multi-Criteria `MEDIAN(IF())` Logic, Array Filtering (`FILTER`), String Searching (`ISNUMBER/SEARCH`), Range Spill Operations (`#`).
* **UI & Validation:** Excel Data Validation Rules, Form Control Integration, Dynamic Range Binding.
* **Visualization Layer:** Geographic Map Charts, Horizontal Sorted Bar Charts, Executive KPI Formatting.
* **Core Business Domains:** Compensation Benchmarking, Talent Acquisition Analytics, Geographic Market Arbitrage.

---

## 👨‍💻 About the Developer

I’m Timothy, a certified data analyst with a deep background in managing rigid data structures and corporate compliance within the financial sector. I pivoted into data analytics because I am passionate about engineering reliable data solutions, unraveling complex business problems, and delivering clear, actionable metrics to stakeholders.

I thrive on building optimized models, writing clean documentation, and creating intuitive visual architectures that help business leaders make rapid, data-backed operational decisions.
