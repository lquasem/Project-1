# Yelp Fusion API Calls for Bay Area Restaurants

This is the final version of code to extract full dataset (within scope of project) of Bay Area restaurants from Yelp API. Failed attempts are outlined in sub-directory labeled 'scrapped'. These  preceding trials are divided in stages and described in more detail in sub-directory. Otherwise, for more information on final stable code, continue below:


### SETUP


JUPYTER WORKBOOKS

* coordinates_grid.ipynb - Creates GPS coordinates grid covering the Bay Area and stores in grid_coordinates2.csv

* calls_by_coord_ver2.ipynb - Makes API calls using coordinates in grid_coordinates2.csv and stores results in restaurant_data_coords3.csv. Analysis into results show 2 coordinates with > 1k results, warranting further queries on the pair to ensure valid results were not missed (see below).

* calls_for_2_coords_rating_ver2.ipynb - Makes additional queries on the 2 coordinates identified above with a sort-by-rating and stores results in restaurant_data_coords_ratings3.csv. Ensures the top-1k restaurants in those 2 coordinates are represented in final dataset.


RESOURCES

* grid_coordinates2.csv - Coordinates for a grid covering Bay Area with 3 mi intervals
* restaurant_data_coords3.csv - Raw dataset from Yelp API that contains all restaurants in Bay Area, except limited results from 2 coordinates.
* restaurant_data_coords_ratings3.csv - Raw dataset of the top-1k restaurants for each of the 2 coordinates with limited results in restaurants_data_coords3.csv

### METHODOLOGY

For each city listed in cities.csv, return all restaurants found via yelp api and
extract data regarding:

- name
- address & zip
- coordinates
- rating
- review count
- price level
- category
- yelp id


From above data, also determine the following for each city:

- total count of restaurants
- distribution of categories (eg. 10% Pizza, 20% Sushi, etc.)
- ratio of price level options (ie. total count of pricier levels divided by count of lower levels)
- total count of restaurants above a given rating
- concentration of restaurants (ie. total count divided by sq. mi of city)