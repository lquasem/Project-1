# Yelp Fusion API Calls for Bay Area Restaurants


Final version of code to extract the full dataset of Bay Area restaurants (within scope of project) from Yelp API. A set of coordinates are created then passed to Yelp API to return key attributes of matching restaurants. Two of the queries, shown as missing data upon closer analysis, undergo supplemental calls and results are added to the final raw dataset.

Though this version proved stable for use within the scope of this project, caution is necessary if applying to a new region for study. The main pitfall is choosing parameters that end up returning queries with over 1k results such as the two coordinates mentioned above (Yelp query results maxed at 1k). Minimizing the number of queries with this issue is crucial for best results. 

For this study the ideal parameters, determined using hypotenuse theory, were a pair of coordinates every 3 miles and a search radius 2.12 miles for each location. Hypotenuse theory ensures full coverage of the area but with minimal overlap, thereby reducing duplicate restaurant results.

Other limitations of Yelp API may be found in the directory labeled 'scrapped', where encountered issues demanded an alternate approach. These failed attempts are arranged into stages to show the evolution of the API call and may prove a useful reference if applying code to a new study.

Otherwise, for more information on final stable code, continue below:


### SETUP


JUPYTER WORKBOOKS

* coordinates_grid.ipynb - Creates grid of GPS coordinates covering the Bay Area, then stores in grid_coordinates2.csv

* calls_by_coord_ver2.ipynb - Makes API calls using coordinates in grid_coordinates2.csv and stores results in restaurant_data_coords3.csv. Note: 2 coordinates over 1k results max, warranting additional queries on the pair to ensure valid results were not missed (see below)

* calls_for_2_coords_rating_ver2.ipynb - Makes additional queries on the 2 coordinates identified above, with ratings sort adjustment which extracts Yelp's top 1k results for both and stores in restaurant_data_coords_ratings3.csv. Provides extra assurance that top restaurants in those busy areas are represented in final dataset.


RESOURCES

* grid_coordinates2.csv - Coordinates for a grid covering Bay Area with 3 mi intervals

* restaurant_data_coords3.csv - Raw dataset from Yelp API that contains all restaurants in Bay Area, except limited results from 2 coordinates.

* restaurant_data_coords_ratings3.csv - Raw dataset of the top-1k restaurants for each of the 2 coordinates with limited results in restaurants_data_coords3.csv



### METHODOLOGY


1. Run coordinates_grid.ipynb to create grid of coordinates. Bay Area boundaries are hard-coded  and can be replaced as desired. The interval between coordinates is also hard-coded and set to 3 miles (4.82803 km).

2. Run calls_by_coords_ver2.ipynb, which takes in coordinates_grid2.csv created in step 1, and makes Yelp API calls using hard-coded search radius of 2.12 miles. For each result in a query, the following information is extracted:

- restaurant name
- address/city/zipcode
- coordinates
- rating
- review count
- price level
- category array
- yelp id

3. calls_by_coords_ver2.ipynb in step 2 also tracks total restaurants count for each query. The dataframe is sorted at bottom of workbook for quick identification of any queries exceeding 1k results. If a significant % of queries exceeds the 1k max, a tighter search radius AND/OR set of coordinates may be required before restarting the API calls.

4. Given that only a fraction of 1% of coordinates in this example exceeded 1k, no amount of adjusting of parameters in original code will extract 100% of results in reasonable time. In this case, running call_by_coords_rating_ver2.ipynb will suffice in supplementing initial API calls. Other supplemental methods may be required for different situations.

5. Merging of both csv from steps 2 and 3 is detailed in data cleaning section