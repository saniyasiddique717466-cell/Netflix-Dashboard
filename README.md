# Netflix Content Analysis Dashboard | Power BI

An interactive Netflix Content Analysis Dashboard built using Microsoft Power BI to analyze Netflix movies and TV shows across content type, release year, country, genre, rating, and content addition trends.

## Dashboard Overview

The dashboard provides insights into:

- Total number of Netflix titles
- Movies vs TV Shows distribution
- Content added over the years
- Content released by year
- Movies vs TV Shows by release year
- Top countries producing Netflix content
- Most common content ratings
- Top genres
- Average movie duration

Interactive slicers allow users to filter the dashboard by Rating, Release Year, Type, and Country.

## Tools & Technologies

- Microsoft Power BI
- Power Query
- DAX
- Data Cleaning & Transformation
- Data Visualization
- CSV Dataset

## Dataset

The dataset contains Netflix titles with the following fields:

| Column | Description |
|---|---|
| `show_id` | Unique identifier for each title |
| `type` | Movie or TV Show |
| `title` | Title of the content |
| `director` | Director of the title |
| `cast` | Cast members |
| `country` | Country or countries associated with the title |
| `date_added` | Date the title was added to Netflix |
| `release_year` | Original release year |
| `rating` | Content rating |
| `duration` | Movie duration or number of seasons |
| `listed_in` | Genre or category |
| `description` | Description of the content |

## Data Preparation

The raw dataset was cleaned and transformed using Power Query.

Key transformations included:

- Removed malformed/error records
- Corrected data types
- Converted `date_added` into a date field
- Extracted `Year Added`
- Split `duration` into Duration Number and Duration Unit
- Prepared country and genre fields for analysis
- Preserved valid missing values
- Created fields required for dashboard analysis

## DAX Measures

### Total Titles

```DAX
Total Titles =
DISTINCTCOUNT(netflix_titles[show_id])
Movies
Movies =
CALCULATE(
    [Total Titles],
    netflix_titles[type] = "Movie"
)
TV Shows
TV Shows =
CALCULATE(
    [Total Titles],
    netflix_titles[type] = "TV Show"
)
Average Movie Duration
Avg Movie Duration =
CALCULATE(
    AVERAGE(netflix_titles[Duration Number]),
    netflix_titles[type] = "Movie"
)
Total Countries
Total Countries =
DISTINCTCOUNT(netflix_titles[country])
Dashboard Visualizations

The dashboard includes:

Movies vs TV Shows Donut Chart
Content Added by Year
Content Released by Year
Movies vs TV Shows by Release Year
Top 10 Countries
Top 10 Ratings
Top 10 Genres
KPI Cards for key metrics
Interactive Filters

The dashboard includes slicers for:

Rating
Release Year
Type
Country

These filters dynamically update the dashboard visuals.

Key Business Questions

The dashboard was designed to answer questions such as:

How many titles are available on Netflix?
What is the distribution between Movies and TV Shows?
How has Netflix content addition changed over time?
Which years produced the most content?
Which countries contribute the most titles?
What are the most common content ratings?
Which genres appear most frequently?
How does content distribution differ between Movies and TV Shows?
What is the average duration of Netflix movies?
Dashboard Design

The dashboard uses a Netflix-inspired visual theme with:

Dark background
Netflix red accents
White and light-gray typography
Interactive slicers
KPI cards
Data visualization charts
Netflix-themed background imagery
Skills Demonstrated
Data Analysis
Business Intelligence
Power BI
Power Query
DAX
Data Cleaning
Data Transformation
Data Modeling
KPI Development
Data Visualization
Dashboard Design
Exploratory Data Analysis
Project Objective

The objective of this project was to transform raw Netflix content data into an interactive Business Intelligence dashboard that makes content trends, distributions, and patterns easier to analyze.

This project demonstrates the practical use of Power Query, DAX, data transformation, and visualization techniques to convert raw data into meaningful business insights.

Project Structure
Netflix-PowerBI-Dashboard/
│
├── Netflix_Dashboard.pbix
├── netflix_titles.csv
├── Dashboard.png
└── README.md
Author

Saniya Begum

Aspiring Data Analyst & Data Scientist

Skills: Python, SQL, Power BI, DAX, Power Query, Data Analysis, Data Visualization
