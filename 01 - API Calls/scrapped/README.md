# SCRAPPED API Calls


Evolution of the Yelp API call used for this project divided into 4 stages. Titles listed below explain the approach taken in each of the stages. Encountered issues are listed in bullets.


### SETUP / API CALL EVOLUTION


1 - API CALLS BY CITY
* Many queries over results limit: significant missing data
* Inaccurate results due to internal algorithm: need results restricted to query location
* Extracts only first category: need full array (this issue is not solved until working code)
POSSIBLE SOLUTION: Run calls again but with ratings sort to get additional results, concatenate both datasets

2 - API CALLS BY CITY WITH RATINGS SORT
* Same issues as stage 1
* Still unsure how much of the data is actually missing
POSSIBLE SOLUTION: Abandon search by cities entirely and look for more precise parameters

3 - API CALLS BY ZIP CODE
* Same issues as stage 1 & 2 despite the larger query set
* Internal algorithm does not restrict results when using city or zip parameters
POSSIBLE SOLUTION: Research geocoordinate and radius parameters

4 - API CALLS BY GEOCOORDINATES
 
First run of calls used set in grid_coordinates.csv, intervals of 5 mi. The search radius of 5 mi
was hardcoded into calls_by_coord.ipynb
* Dataset more complete but also many duplicate results due to overlapping searches. Could cause problems with maxing out daily call limit of 5k if coordinate set is large enough
* Still many coordinates over limit
POSSIBLE SOLUTION: Run calls again but with ratings sort to get additional results, concatenate both datasets

Second run of calls used same set of 5 mi interval coordinates and 5 mi search radius but ran calls_by_coord_ratings.ipynb to sort by ratings
* Still unsure how much of data is actually missing
POSSIBLE SOLUTION: Try a tighter set of coordinates and determine search radius based on hypotenuse theory to reduce duplicates

Third run of calls used set in grid_coordinates2.csv, intervals of 3 mi. The search radius was hardcoded to 2.12 mi to satisfy hypotenuse theory. Code used in first geocoordinates run, calls_by_coord.ipynb, was adjusted to its current state.
* 2 coordinates over limit
POSSIBLE SOLUTION: Very minimal missing data, but for completeness run both queries again with ratings sort and concat to results here

Fourth run of calls hardcodes the over-limit coordinates in run 3 into calls_for_2_coords_rating.ipynb and returns results in order of top-rated. The same 2.12 radius is used

* Full dataset of restaurants attained but each stage up to this point has issue of missing category information. This is due to bug in code starting in stage 1 and subsequently inherited. The working API call corrects this issue while following logic of runs 3 & 4 in stage 4.