# Retail Location Optimization in Bengaluru

A geospatial data science project that identifies optimal retail locations in Bengaluru using OpenStreetMap data and machine learning.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Technical Stack](#technical-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Data Sources](#data-sources)
- [Methodology](#methodology)
- [Results](#results)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)


## Project Overview
This project analyzes geospatial data to recommend optimal retail store locations in Bengaluru by evaluating:

- Competitor density (existing stores)
- Road network accessibility
- Synthetic population metrics

The system combines OpenStreetMap data with machine learning (K-Means clustering and Random Forest regression) to generate actionable insights.

## Features
✔ **Competitor Hotspot Analysis** - Identifies market saturation zones  
✔ **Accessibility Scoring** - Evaluates location connectivity  
✔ **ML-Powered Predictions** - Forecasts sales potential  
✔ **Interactive Visualization** - Folium-powered interactive maps  
✔ **Robust Pipeline** - Automatic timeout handling (10-min max for heavy computations)  

## Technical Stack
**Core Technologies:**
- Python 3.8+
- OSMnx 1.0+
- GeoPandas 0.10+
- Scikit-learn 1.0+

**Key Libraries:**
```python
import osmnx as ox          # Geospatial data extraction
import geopandas as gpd     # Spatial operations  
import folium               # Interactive mapping
from sklearn.ensemble import RandomForestRegressor  # ML modeling

**Installation** 
Clone the repository:

bash
git clone https://github.com/ankitrajkumawat/retail-location-optimization.git
cd retail-location-optimization
Set up virtual environment:

bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate    # Windows
Install dependencies:

bash
pip install -r requirements.txt
Usage
Run the complete analysis:

bash
python bangalore_retail_analysis.py
Outputs:

Terminal logs showing analysis progress

optimal_locations.html - Interactive map with:

Competitor locations (red)

Cluster centers (blue)

Recommended locations (green)

Customization Options:

python
# Change business type (default: 'cafe')
competitors = get_competitors(poi_type='restaurant')

# Adjust timeout (seconds)
nodes = analyze_road_network(G, timeout=300)  
Data Sources
Data Type	Source	Extraction Method
City Boundaries	OpenStreetMap	OSMnx geocode_to_gdf
Road Networks	OSMnx	graph_from_place
Business Locations	OSM 'amenity' tags	features_from_place
Methodology
Data Collection

Bengaluru boundary polygon

Road network graph

Competitor locations (e.g., cafes)

Feature Engineering

python
# Key features created
features = {
    'distance_to_competitor': min_dist,  # Meters
    'road_centrality': 0.82,            # 0-1 score  
    'population_density': 4500           # People/km²
}
Machine Learning

K-Means for competitor clustering

Random Forest for sales potential prediction

Results
Sample Output:

Location Coordinates	Sales Score	Key Factors
12.9716°N, 77.5946°E	84.2	Low competition, high accessibility
12.9258°N, 77.5268°E	76.5	Emerging neighborhood
https://i.imgur.com/mno678.png

Future Enhancements
Integrate real population data from census

Add traffic pattern analysis

Develop Streamlit web interface

Include rental price estimates

Contributing
Contributions are welcome! Please:

Fork the repository

Create your feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add some amazing feature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request
