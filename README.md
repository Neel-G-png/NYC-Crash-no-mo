# Crash NO! MO! - Urban Traffic Safety Project

## Project Overview

**Crash NO! MO!** is a groundbreaking project aimed at addressing the critical issue of traffic accidents in urban environments. It stands out by integrating real-time traffic and historical crash heatmaps into an interactive dashboard, providing a dual-layered view of traffic dynamics and safety risks. A unique and innovative aspect of this project is its consideration of road network graphs, such as intersection density and structure, as a critical feature for dynamically predicting crash hotspots. This integration ensures highly precise and actionable insights, empowering urban planners, policymakers, and the public to enhance traffic safety and reduce accident rates effectively.

---

`![Landing Screen](images/og_screen.png)`

---

## Motivation

The increasing frequency and impact of urban traffic accidents inspired this project. By utilizing vast data sources like NYC open traffic data, the project aims to enhance traffic safety, reduce economic losses, and save lives. The predictive model offers actionable insights for immediate traffic management and long-term urban planning.

---

## Data Sources

The project integrates multiple datasets to ensure comprehensive analysis:

1. **Historical Crash Data**:
   - Analyzed crash severity using factors like injuries and fatalities.
   - [Dataset Link](https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95/about_data)

2. **Road Network Data**:
   - Converted NetworkX format to DataFrame for analysis.
   - Analyzed road intersections, particularly T-intersections, for their role in accidents.
   - **This unique feature allows the model to dynamically predict crash hotspots by factoring in road network graph data.**
   - [Dataset Link](https://www.openstreetmap.org/)

3. **Weather Data**:
   - Collected temperature, precipitation, and weather conditions via APIs.
   - Enhanced predictions by incorporating weather-related variables.

4. **Infrastructural Data**:
   - Data on schools and parks helped understand pedestrian-heavy areas.
   - [Dataset Link](https://data.cityofnewyork.us/Education/School-Point-Locations/jfju-ynrr/about_data)

5. **Traffic Data**:
   - Analyzed traffic flow, density, and speed.
   - [Dataset Link](https://data.cityofnewyork.us/Transportation/DOT-Traffic-Speeds-NBE/i4gi-tjb9/about_data)

---

## Methodology

### 1. Data Cleaning and Integration
- Initial cleaning was performed using Apache Spark for speed and scalability.
- Dask handled complex data manipulations, including geospatial analysis and time-series evaluations.

### 2. Data Analysis
- **Spatial Analysis**: Identified accident-prone areas like Brooklyn using population density correlations.
- **Temporal Trends**: Fridays and specific months (May, November, December) showed higher accident rates.
- **Weather Analysis**: Accidents were less frequent during extreme weather conditions.

### 3. Predictive Modeling
- **K-Nearest Neighbors (KNN)**: Used for similarity-based predictions but struggled with large-scale data.
- **Random Forest**: Outperformed KNN with robust handling of imbalanced and nonlinear data. Implemented via DaskML for distributed training.

---

## Application Deployment

The project’s insights are visualized through an interactive dashboard built with **Streamlit**, offering real-time updates and predictive analytics.

### Key Features:
1. **Real-Time Traffic Heatmap**:
   - Displays real-time traffic conditions, including congestion and average speed.
   - Enables users to explore dynamic traffic conditions for targeted analysis.
     `![Real-Time Traffic Heatmap](images/traffic_heatmap.png)`

2. **Historical Crash Heatmap**:
   - Visualizes past accident data, highlighting areas with higher crash densities.
   - Enhances understanding of long-term trends and high-risk zones.
   - **Screenshot Placeholder: Insert historical crash heatmap screenshot here**  
     `![Historical Crash Heatmap](images/crash_heatmap.png)`

3. **Dynamic Crash Hotspot Prediction**:
   - Uniquely considers road network graph data, including intersection density, for dynamic predictions.
   - Provides deeper insights into accident-prone areas influenced by structural road features.

4. **Interactive Dashboard**:
   - Users can dynamically toggle map views and adjust conditions like weather or traffic density to refine predictions.
   - A clean, easy to understand dashboard will be created specifically for the data in focus on the data
     `![Interactive Dashboard](images/Dashboard.png)`

5. **Customizable Queries**:
   - Allows users to explore how factors like rain and high traffic influence accident probabilities.

6. **Predictive Insights**:
   - Machine learning models predict accident severity and risk zones based on integrated datasets.

7. **Statistical Tools**:
   - Correlation analyses and visualizations offer additional depth for exploring accident factors.

---

## Technology Stack

- **Data Processing**: Pandas, Dask, Apache Spark
- **Visualization**: Folium, Altair, Matplotlib
- **Geospatial Tools**: GeoPandas, Shapely
- **Dashboard Framework**: Streamlit
- **Machine Learning**: DaskML, scikit-learn (Random Forest, KNN)

---

## Challenges and Solutions

1. **Data Volume**:
   - Addressed with parallel processing via Dask.
2. **Real-Time Integration**:
   - Managed through optimized caching and error handling for API calls.

---

## Results

The application effectively predicts and visualizes traffic risks, offering a practical tool for urban safety management and policy-making. By combining real-time updates, predictive analytics, and user-friendly dashboards, it bridges the gap between data-driven insights and actionable urban planning.

---

## Conclusion

**Crash NO! MO!** successfully demonstrates the power of integrating big data analytics with predictive modeling to enhance urban traffic safety. The project's standout features—real-time traffic heatmaps, historical crash visualizations, and dynamic crash hotspot predictions using road network graphs—make it a comprehensive tool for improving traffic management and road safety. By fostering proactive accident prevention strategies, the application contributes significantly to safer urban environments.