# Project Overview

This project integrates Citi Bike and NYC Subway data to explore their relationships through ETL (Extract, Transform, Load), data merging, and visualization. The workflow is divided into three notebooks to ensure modularity, collaboration, and clarity. The analysis focuses on transforming raw data into actionable insights with visualizations and geospatial analyses.

---

## Code Artefact

The zip file containes the following:
1. **Citi_Bike_Notebook.ipynb**
2. **nyc_subway_info.ipynb**
3. **Master_File.ipynb**
4. **citi_bike.json**

---

## Workflow Overview

### Separate Analysis Notebooks

#### Citi_Bike_Notebook
- **Data Loading**: Loads Citi Bike data from the citi_bike_merged_with_date_time JSON file.
- **MongoDB Storage**: Stores raw data in a MongoDB Docker container for preprocessing.
- **ETL Process**: Cleans and transforms the data to make it analysis-ready.
- **PostgreSQL Storage**: Saves the cleaned data into a PostgreSQL Docker container.

#### nyc_subway_info
- **Data Loading**: Loads NYC subway data from various sources.
- **MongoDB Storage**: Stores raw data in a MongoDB Docker container for initial processing.
- **ETL Process**: Cleans and transforms subway data.
- **PostgreSQL Storage**: Saves the cleaned data into a PostgreSQL Docker container.

### Master Notebook
- **Data Retrieval**: Loads processed tables from PostgreSQL.
- **Data Merging**: Cleans and combines Citi Bike and subway datasets within MongoDB.
- **Final Storage**: Saves the merged dataset into PostgreSQL.
- **Visualization**: Creates advanced visualizations like heatmaps, scatter plots, and dashboards to explore station density, proximity, and usage trends.

---

## Libraries and Dependencies

### Data Manipulation:
- `pandas`, `numpy`, `pandas.io.sql`

### Visualization:
- `matplotlib`, `seaborn`, `plotly`, `folium`

### Database Interaction:
- `sqlalchemy`, `pymongo`, `psycopg2`

### Utilities:
- `json`, `requests`, `scipy`, `IPython`


---

## Usage Instructions

### Prerequisites
- Install Python 3.x and Jupyter Notebook.
- Set up MongoDB and PostgreSQL servers as Docker containers.
- Install the required Python libraries using `pip install` Libraries to install are in the notebooks.

### MongoDB Setup
1. Start the MongoDB Docker container.
2. Use the following configuration in code:
   ```python
   # Connect to MongoDB
   client = MongoClient("mongodb://%s:%s@127.0.0.1" % ("<username>", "<password>"))  # Replace with authentication details
   database = client['as_is_in_code']
   collection = database['as_is_in_code']
   ```

### PostgreSQL Setup
1. Start the PostgreSQL Docker container.
2. Use the following configuration in code:
   ```python
   conn = psycopg2.connect(
       dbname="<dbname>",  # Replace with your dbname
       user="<username>",   # Replace with your username
       password="<password>",  # Replace with your password
       host="localhost",
       port="5432"
   )
   ```

### Running the Code
1. **Citi_Bike_Notebook.ipynb**:
   - Load Citi Bike data from JSON files.
   - Perform ETL and save data to MongoDB and PostgreSQL.
2. **nyc_subway_info.ipynb**:
   - Load subway data.
   - Perform ETL and save data to MongoDB and PostgreSQL.
3. **Master_File.ipynb**:
   - Retrieve processed data from PostgreSQL.
   - Merge and clean the data in MongoDB.
   - Save the final merged dataset to PostgreSQL.
   - Run visualization cells to generate insights.

---

## Authors

This project was collaboratively developed by:
- **Lathifa Jaffer Diang'a**: Responsible for Citi Bike data analysis and visualizations.
- **Emmanuella Anita Odiaka**: Handled subway data processing, analysis and visualizations. 

The final project mapping, database integrations, analysis and visualisations were done collaboratively between the both of us.

---

## Acknowledgments

We would like to thank the following resources and tools for their contributions:
- Citi Bike and NYC Subway for making their data publicly available.
- MongoDB and PostgreSQL for robust database solutions.
- Docker for simplifying environment setup.
- Python libraries like `pandas`, `matplotlib`, and `seaborn` for simplifying data processing and visualization also, `folium` and `plotly` for interactive visualisations.

---

This project demonstrates a comprehensive ETL pipeline, data merging, and exploratory analysis of two interconnected datasets. It showcases how combining datasets and leveraging database technologies can provide deeper insights into urban transportation systems.

