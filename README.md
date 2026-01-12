🎬 Netflix – Content Insights Dashboard
📌 Project Overview

This project analyzes Netflix’s content catalog to uncover trends in content growth, maturity ratings, genres, geographic distribution, and cast presence over time. Using Databricks and Delta Lake, I designed an end-to-end analytics pipeline and built an executive-style dashboard that presents curated, high-impact insights rather than raw counts.

The final output is a Netflix-style content insights dashboard focused on clarity, storytelling, and business relevance.

🏗️ Architecture & Data Pipeline

The project follows a Medallion Architecture approach:

Bronze Layer

Ingested raw Netflix CSV data into Databricks

Preserved source structure for traceability

Silver Layer

Cleaned and standardized data

Fixed data quality issues caused by column misalignment (e.g., ratings appearing as durations, numeric values in country fields)

Applied domain whitelisting for controlled fields such as:

type (Movie, TV Show)

rating (TV-MA, TV-14, PG-13, etc.)

Parsed and normalized array-based fields:

Genres

Countries

Cast members

Derived analytical attributes:

Content duration value & unit

Year added

Gold Layer

Created analytics-ready tables and views

Optimized for dashboard performance and filter consistency

Supported dimensional analysis by genre, country, rating, and cast

📊 Dashboard Highlights

The final dashboard (built using Databricks SQL Lakeview) provides:

Key Metrics

Total Titles: 8.81K

Movies: 6.13K

TV Shows: 2.68K

Content Growth Over Time

Area chart showing Netflix’s rapid expansion post-2016

Highlights peak content acquisition and recent slowdown

Content by Maturity Rating

Distribution of titles across maturity ratings

Reveals Netflix’s strong focus on TV-MA and TV-14 content

Most Popular Genres

Top genres such as International Movies, Dramas, and Comedies

Reflects global and diverse content strategy

Top Content Producing Countries

United States, India, and the United Kingdom as major contributors

Demonstrates Netflix’s global production footprint

Top Cast Presence Over Time

Trend analysis of selected prominent cast members

Shows how talent presence evolves across years

🎨 Design & Visualization Approach

Avoided cluttered visuals and redundant charts

Focused on storytelling and hierarchy, not just counts

Used:

Area charts for growth

Bar charts for distributions

Line charts for trends

Chose to bind filters directly at the visual level instead of global widgets to reduce complexity and improve control

Designed the dashboard for executive consumption: clean layout, limited colors, and clear titles

🛠️ Tools & Technologies

Databricks

Delta Lake

Databricks SQL (Lakeview Dashboards)

SQL

Medallion Architecture (Bronze / Silver / Gold)

💡 Key Learnings

Real-world datasets often contain schema drift and misaligned values that must be handled defensively

Data quality rules (whitelisting, validation) are critical for trustworthy analytics

Good dashboards prioritize clarity and intent over visual quantity

Tool limitations (e.g., lack of small multiples in Lakeview) require thoughtful design trade-offs
