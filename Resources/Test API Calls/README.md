# Hypotenuse Test Calls

Hypotenuse theory calls_by_coordinate_radius_4023_testing.ipynb – A test file with Yelp API to see if reduced graphical coordinates and shorter search radius would be better. If one thinks about the geographical coordinates spaced out every 5 miles, then the search radius selected was 2.5 miles and covering 78% of bay area while the search went on for the restaurants

Hypotenuse theory calls_by_coordinate_radius_5690_testing.ipynb – A test file with Yelp API to see if reduced graphical coordinates and a shorter search radius would be better. If one thinks about the geographical coordinates spaced out every 3 miles, then we want to grab all restaurants in the coordinate grid rectangular spacing with minimum restaurant duplicates returned, in order to reduce the number of API calls over 1K.

	Half way between 3 miles = 1.5
	1.5  = y
       Y^2 + Y^2 = r^2

Whereby, r will give the search radius of returning all restaurants in a geocoordinate block while minimizing duplicates.