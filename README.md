# 🎬 Netflix Shows Analytics Dashboard | Power BI Project

### 📌 Project Overview  
This project focuses on analyzing Netflix’s catalog of movies and TV shows using **Power BI**.  
The dashboard provides insights into **content type distribution**, **country-wise trends**, **ratings**, **release patterns**, and **genre popularity**.  

By combining **data cleaning, DAX calculations, and interactive visualization**, this project turns raw Netflix data into meaningful business insights that highlight trends and opportunities in the streaming landscape.

---

### 🧰 Tools & Technologies Used  
- **Power BI Desktop** — Data modeling & dashboard creation  
- **Power Query** — Data transformation and cleaning  
- **DAX (Data Analysis Expressions)** — For calculated columns & measures  
- **Dataset:** Netflix Movies and TV Shows (~2,000 records)

---

### 📊 Dashboard Features  
1. **KPI Cards** — Total Titles, Movies, TV Shows, Top Country, and Average Movie Duration  
2. **Donut Chart** — Distribution of Movies vs TV Shows  
3. **Bar Chart** — Top 10 Countries by Number of Titles  
4. **Line Chart** — Titles Released Over the Years  
5. **Treemap** — Genre Popularity  
6. **Stacked Bar Chart** — Ratings Distribution  
7. **Table/Matrix View** — Detailed information on each title  
8. **Slicers** — For filtering by Type, Country, Year, Rating, and Genre  

---

### 💡 Key Insights & Findings  
- **Movies dominate** the platform with around **70%** share, while **TV Shows** account for the remaining 30%.  
- **United States** produces the largest number of titles, followed by **India**, **UK**, and **Japan**.  
- **Drama**, **Comedy**, and **Action** are the most frequent genres across the catalog.  
- The **2018–2021 period** saw the highest surge in new releases — indicating Netflix’s global expansion drive.  
- Most titles are rated **TV-MA** and **TV-14**, suggesting a focus on mature audiences.  
- Average movie duration is around **100 minutes**, with many popular series having **2–4 seasons**.  

---

### 📈 Business Impact  
This dashboard helps uncover:  
- Content distribution across formats, genres, and countries  
- Opportunities for localization and genre diversification  
- Insights into production patterns to plan future content acquisitions  

---

### 🧮 Sample DAX Measures  
```DAX
Total Titles = COUNTROWS(Netflix_Data)

Total Movies = 
CALCULATE(COUNTROWS(Netflix_Data), Netflix_Data[Type] = "Movie")

Total TV Shows = 
CALCULATE(COUNTROWS(Netflix_Data), Netflix_Data[Type] = "TV Show")

Average Duration (Movies) = 
AVERAGEX(FILTER(Netflix_Data, Netflix_Data[Type] = "Movie"), VALUE(LEFT(Netflix_Data[Duration], FIND(" ", Netflix_Data[Duration]) - 1)))

Top Country = 
FIRSTNONBLANK(
    TOPN(1, SUMMARIZE(Netflix_Data, Netflix_Data[Country], "Count", COUNTROWS(Netflix_Data)), [Count], DESC),
    Netflix_Data[Country]
)
```

---

### 🧩 How to Run the Project  
1. **Clone this repository**  
   ```bash
   git clone https://github.com/your-username/netflix-shows-analytics-powerbi.git
   cd netflix-shows-analytics-powerbi
   ```
2. **Open the Power BI file**  
   - Option A: Open `pbix/Netflix_Shows_Analytics.pbix` directly in Power BI Desktop  
   - Option B: Import the CSV dataset (`data/Netflix_Data_2000.csv`) → Recreate visuals  
3. **Explore the Dashboard**  
   - Use slicers for **Type**, **Country**, **Year**, and **Genre**  
   - Interact with charts to view country and genre trends  


### 🏆 Results  
- Created an **interactive Power BI dashboard** visualizing 2,000+ Netflix titles  
- Derived insights into **genre trends, release year patterns, and country-level distributions**  
- Built reusable **DAX measures** for performance tracking and dynamic filtering  
- Strengthened understanding of **data visualization design principles**  

### 🧠 Learnings  
- Data cleaning & transformation using **Power Query**  
- Advanced **DAX expressions** and measure creation  
- Designing **interactive dashboards** with bookmarks and slicers  
- Communicating insights visually and effectively  

### 📬 Contact  
**Author:** Deepansh Raina  
- 💼 GitHub: [https://github.com/your-username](https://github.com/your-username)  
- 📧 Email: deepanshraina@example.com  
- 📊 Project: *Netflix Shows Analytics Dashboard (Power BI)*  

