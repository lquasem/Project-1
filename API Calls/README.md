# Foodie's Paradise

Using Yelp Fusion API to determine which city in the Bay Area is best suited for a foodie to live or vist.


### SETUP

RESOURCES
* cities.csv - list of cities to compare
* grid_coordinates.csv - list of coordinates for a grid based on cities.csv
* restaurant_data.csv - output data of query results from city_calls.ipynb
* restaurant_data_rating.csv - output data of query results from city_calls_rating.ipynb
* General - directory for storing assignment directions and misc items

JUPYTER WORKBOOKS
* calls_by_city.ipynb - Makes Yelp API calls by city
* calls_by_city_ratings.ipynb - Same as city_calls.ipynb but sorts queries by rating when making calls
* coordinates_grid.ipynb - Outputs list of coordinates to make a grid using cities.csv as input
* calls_by_coord.ipynb - Makes Yelp API calls by coordinate
* calls_by_coord_ratings.ipynb - Same as coord_calls.ipynb but sorts queries by rating when making calls
* calls_by_zip.ipynb - Makes Yelp API calls by zip code, only returns first 50 results for each zip code
* plot_coord.ipynb - Creates scatter plot using lat/lng and total restaurants at each coordinate pair


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