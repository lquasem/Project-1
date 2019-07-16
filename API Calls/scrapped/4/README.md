WORKBOOKS

* calls_by_coord.ipynb - Makes Yelp API calls by coordinate

* calls_by_coord_ratings.ipynb - Same as coord_calls.ipynb but sorts queries by rating when making calls

* calls_for_2_coords_rating.ipynb - Makes additional queries on 2 coordinates, with ratings sort adjustment to extract Yelp's top 1k results. Provides extra assurance that top restaurants in those busy areas are represented in final dataset.

* plot_coords.ipynb - Creates scatter plot using lat/lng and total restaurants at each coordinate pair


RESOURCES

* Images - directory to store images from plot_coords.ipynb

* grid_coordinates.csv - list of coordinates for a grid covering Bay Area with 5 mi intervals

* grid_coordinates2.csv - similar to above but with 3 mi intervals

* grid_coordinates.csv - list of coordinates for a grid covering Bay Area with 5 mi intervals

* grid_coordinates2.csv - similar to above but with 3 mi intervals

* restaurant_data_coords.csv - output data of query results from calls_by_coord.ipynb using grid_coordinates.csv & 5 mi search radius
* restaurant_data_coords_ratings.csv - similar to above but with additional ratings sort

* restaurant_data_coords2.csv - output data of query results from calls_by_coord.ipynb using grid_coordinates2.csv & 2.12 mi search radius
* restaurant_data_coords_ratings2.csv - similar to above but with additional ratings sort

* total_count_coords.csv - output data from calls_by_coord.ipynb to check if any queries are over limit, which indicates missing data

* total_count_coords2.csv - similar to above but results for 3 mi intervals and 2.12 radius

* total_count_coords_ratings.csv - output data from calls_by_coord_ratings.ipynb to check if any queries are over limit, which indicates missing data
