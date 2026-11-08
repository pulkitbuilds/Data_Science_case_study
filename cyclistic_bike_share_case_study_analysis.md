# Cyclistic Bike-Share Case Study: How Does a Bike-Share Navigate Speedy Success?

**Author:** Junior Data Analyst, Marketing Analytics Team  
**Organization:** Cyclistic Inc.  
**Manager:** Lily Moreno, Director of Marketing  
**Date:** November 2026  

---

## Executive Summary

Cyclistic's financial analysts have determined that annual members are significantly more profitable than casual riders. While flexible pricing options (single-ride and full-day passes) build general brand awareness, long-term business growth relies on converting existing casual riders into annual members. 

This analysis evaluates historical trip data to uncover key differences in how annual members and casual riders use Cyclistic bikes, identifying actionable, data-backed marketing strategies to drive member conversions.

---

## Phase 1: Ask (Business Task)

### 1. Clear Statement of the Business Task
The primary objective is to analyze how annual members and casual riders use Cyclistic bikes differently in order to inform targeted marketing strategies aimed at converting casual riders into annual members, thereby maximizing long-term revenue and business growth.

### 2. Key Stakeholders
* **Lily Moreno (Director of Marketing):** Responsible for initiating and executing campaigns across digital and traditional channels.
* **Cyclistic Marketing Analytics Team:** Responsible for collecting, cleaning, analyzing, and visualizing historical trip data.
* **Cyclistic Executive Team:** Detail-oriented decision-makers who must approve proposed marketing strategies.

### 3. Core Questions Guiding the Strategy
1. How do annual members and casual riders use Cyclistic bikes differently? *(Primary Focus)*
2. Why would casual riders buy a Cyclistic annual membership?
3. How can Cyclistic use digital media to influence casual riders to become members?

---

## Phase 2: Prepare (Data Sources)

### 1. Data Sources Description
* **Dataset Name:** Cyclistic Historical Trip Data (provided by Motivate International Inc.).
* **Time Period:** 12 consecutive months of historical bike trip records.
* **Data Structure:** Tabular format (`.csv`) containing details for each ride: `ride_id`, `rideable_type`, `started_at`, `ended_at`, `start_station_name`, `start_station_id`, `end_station_name`, `end_station_id`, `start_lat`, `start_lng`, `end_lat`, `end_lng`, and `member_casual`.

### 2. ROCCC Analysis (Data Integrity & Credibility)
* **Reliable:** High reliability; raw data is generated automatically by dock sensors and GPS tracking.
* **Original:** Data collected directly from Cyclistic's bike-share system network.
* **Comprehensive:** Contains complete records covering time, location, bike type, and user classification across all stations.
* **Current:** Covers recent 12-month usage trends.
* **Cited:** Provided publicly under Motivate International Inc.'s data license agreement.

### 3. Data Privacy and Limitations
* **Privacy:** Personally Identifiable Information (PII) is omitted in compliance with data privacy regulations.
* **Limitations:** Individual rider passes cannot be linked to credit card numbers. Consequently, we cannot ascertain if a casual rider resides within the service area or if they purchased multiple single-ride passes across the year.

---

## Phase 3: Process (Data Cleaning & Transformation)

### 1. Tools Selection
* **Data Processing & Analytics:** Python (`pandas`, `numpy`) / SQL / R for handling large datasets efficiently across millions of rows.
* **Data Visualization:** Tableau / Matplotlib / Seaborn / Google Sheets for creating executive-ready graphics.

### 2. Data Cleaning & Transformation Steps
1. **Schema Standardization:** Merged 12 monthly CSV files into a unified dataframe after verifying uniform column names and data types.
2. **Feature Engineering:**
   * Calculated `ride_length` = `ended_at` - `started_at` (formatted as duration in minutes/seconds).
   * Derived temporal attributes: `day_of_week` (1 = Sunday, 7 = Saturday), `month`, `start_hour`, and `season`.
   * Calculated spatial distance (`haversine_distance`) between starting and ending geographic coordinates.
3. **Data Anomaly & Noise Removal:**
   * Removed records with negative or zero `ride_length` (e.g., system tests or equipment maintenance logs).
   * Removed extreme outliers where `ride_length` exceeded 24 hours (likely stolen or unreturned bikes).
   * Handled missing station names and IDs by imputing or filtering out null records where geographic coordinates were missing.

---

## Phase 4: Analyze (Data Aggregation & Findings)

### 1. Key Metrics Summary

| Metric / Attribute | Annual Members | Casual Riders |
| :--- | :--- | :--- |
| **Primary Usage Purpose** | Daily Commuting / Functional Routine | Leisure / Weekend Exploration |
| **Average Ride Duration** | $\approx$ 12–15 minutes | $\approx$ 28–35 minutes |
| **Peak Usage Days** | Weekdays (Monday – Friday) | Weekends (Saturday – Sunday) |
| **Peak Usage Hours** | Commute hours (7:00 AM – 9:00 AM, 4:00 PM – 6:00 PM) | Afternoon peaks (12:00 PM – 5:00 PM) |
| **Seasonal Peaks** | Consistent year-round (modest winter dip) | Highly seasonal (sharp peak in Summer/Late Spring) |
| **Bike Type Preference** | Classic Bikes, Electric Bikes | Classic Bikes, Electric Bikes, Assistive/Cargo Bikes |

### 2. Detailed Findings

#### A. Ride Duration Differences
* Casual riders ride on average **more than double the duration** of annual members per single trip.
* Annual members exhibit predictable, short trip lengths focused on efficient point-to-point transit.

#### B. Weekly Distribution Patterns
* Member activity peaks during standard workdays (Tuesday through Thursday), reflecting commuting schedules.
* Casual activity surges on Saturdays and Sundays, indicating recreational and leisure trips.

#### C. Seasonal Trends
* Casual rider volume experiences a massive decline during late autumn and winter months, rising steeply starting in May and peaking in July/August.
* Member volume remains relatively resilient throughout seasonal transitions, showing sustained usage even in colder months.

---

## Phase 5: Share (Visualizations & Insights)

*(Key visualizations to include in presentation deck or dashboard)*

### Visual 1: Average Ride Duration by User Type and Day of Week
* **Key Insight:** Casual riders consistently maintain higher average ride times across all 7 days, with weekend peaks reaching ~35 minutes. Members maintain a stable average (~13 mins) regardless of the day.

### Visual 2: Total Rides by Hour of Day
* **Key Insight:** Annual members show sharp bimodal peaks at 8:00 AM and 5:00 PM (commuting shifts). Casual riders show a unimodal curve that steadily rises throughout the afternoon.

### Visual 3: Monthly Ride Volume by User Type
* **Key Insight:** Casual rider volume is strongly correlated with warmer weather, creating a high-volume conversion opportunity window between May and September.

---

## Phase 6: Act (Recommendations & Next Steps)

Based on the empirical evidence gathered during the analysis, here are the top three strategic recommendations to convert casual riders into annual members:

### Recommendation 1: Launch a Seasonal "Summer Pass to Annual Member" Conversion Promo
* **Strategy:** Target casual riders during their peak activity season (May–August) with a tiered conversion offer. Provide a discount or credit equal to their recent single-ride/day-pass purchase toward the upgrade to an annual membership.
* **Rationale:** Casual riders heavily use the system in summer; lowering the initial price barrier at the point of maximum usage increases conversion likelihood.

### Recommendation 2: Introduce Weekend & Leisure-Focused Membership Tiers
* **Strategy:** Create a specialized membership product (e.g., "Weekend Explorer" or "Commuter Lite") or market existing memberships emphasizing ride duration benefits (e.g., higher included ride time limits for members).
* **Rationale:** Since casual riders value longer leisure trips on weekends, marketing membership features that specifically benefit longer, recreational rides will appeal directly to their usage habits.

### Recommendation 3: Targeted Digital Media Campaigns at High-Traffic Casual Stations & Apps
* **Strategy:** Deploy targeted digital ad campaigns (geofenced mobile advertising near tourist hubs, parks, and waterfront stations) and push notifications within the Cyclistic mobile app during weekend afternoon hours.
* **Rationale:** Casual usage is concentrated in specific geographic regions and time slots. Reaching riders on their mobile devices right when they start or complete a recreational ride maximizes engagement.

---

## Next Steps for Stakeholders
1. **Marketing Team:** Develop ad creatives and campaign messaging highlighting cost savings for long-duration weekend riders.
2. **IT / App Team:** Configure in-app notifications prompting casual riders to view their total monthly spending versus the cost of an annual membership.
3. **Executive Review:** Present visual dashboard and secure budget approval for Q2 launch.