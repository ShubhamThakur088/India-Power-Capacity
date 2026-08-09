**monthly_power_generation_analysis** project analyses monthly electricity generated data for a given country, source of power and for a given month and date range in the format `YYYY-MM`.

This application is integrated with **Ember Energy** API. It retrieves data from, transforms the data into structured tabular format using `Pandas` Library, filters the selected power source, performs statistical analysis, generates visualizations and exports yearly results into CSV files.

### Architecture Flow
1. **User Input**
   - Start Date (YYYY-MM)
   - End Date (YYYY-MM)
   - Country Code (3 letter format)
   - Source of power (Coal, Wind, Solar, Nuclear, Gas etc.)

2. **Data Ingestion**
   - Requests library of python sends HTTP get request to the Ember Energy monthly electricity-generation API.
   - API response is JSON.
   - `data` portion of the JSON response is converted into Pandas DataFrame.

3. **Data Processing**
   - Dataset contains the following attributes:
     - `entity`
     - `entity_code`
     - `date`
     - `series`
     - `generation_twh`

4. **Expolatory Analysis**
   - Monthly generation is analyzed over time.
   - Data is grouped conceptually grouped by year for year-wise comparison.
   - Following statistical measures are employed for each year:
       - Mean
       - Median
       - Variance
       - Standard Deviation
       - Quartile Ranges
5. **Output**
   - Filtered yearly datasets are exported to CSV files.
   - Further optional Azure Blob storage upload workflow is provided.
   
