# Battle of the Neighborhoods Week 1 Final Project

## Introduction/Business Problem

  E-sports (competition using video games) has become more popular than ever. Video game bars
  can be a great place for people who are interested in competing professionally or casually to congregate and socialize.
  They are also a great place to host organized competitions.
  
  In this project, we will help an investor decide the best location within the city of Toronto to open a video game bar. 
## Data

We will be using three sources of Data in this project

- Canada Postal Codes Wikipedia Page
  By using the postal code location data from this page, we will scrape Boroughs and Neighborhood names in Toronto.
  https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M
  
- Cognitive Class Geospatial_data csv
  This data will be used to get latitude/longitude of each neighborhood based on their postal code. We will combine them with the wikipedia data and transform to a Pandas Dataframe.
  https://cocl.us/Geospatial_data
  
 - Foursquare API 
   We will use Foursquare to get top common venues in each neighborhood using the location data we retrieved in the above data set.
  
   
   
 Once we have retrieved all our data and put into a Pandas Dataframe, we will use KMeans clustering to cluster the neighborhoods and present the data on a folium map. We will asl use Foursquare API to analyze top neighborhood venues and any other venues that may relate 
to video games and choose to look at the neighborhoods closest to those findings.

## Methodology 
  First we retrieve the Toronto data from the Wikipedia page provided above to create our data frame. This data gives us postal codes, boroughs,and neighborhood names within the city. We then combine the neighborhoods and boroughs with similar postal codes to clean our data frame.
  
  In order to use the Foursquare API we also need the latitudes and longitudes of each neighborhood. We retrieve this data with the Cognitive Class Geospatial_data data listed above and add to our data frame. 
  
  Next we create our credentials for the Foursquare API and use the explore feature to view venues within a 500 mile radius. We use the 'Venue Category' with the venues latitude and longitude to find the different types of venues in each neighborhood. I then counted how many venues were in each neighborhood. 
  
  Since we are looking to open a bar centered around video games and Foursquare does not have a category type of "Game Bar", I checked to see if there were any "Gaming Cafes" within the city and found 2 venues with this category type. They are both located within the same neighborhood of Chinatown,Grange Park,Kensnington Market
  
  I then searched for venue category "Bars" for each neighborhood. 21 neighborhoods were found to have "Bar" in their venue category. I also searched for other venue categories containing "Bar" as a string in order to find other types of bars within our data. 
  
  Venue Category
Hookah Bar             1

Sake Bar               1

Hotel Bar              3

Gay Bar                5

Salon / Barbershop     5

Juice Bar              8

Sports Bar             8

Wine Bar               9

Cocktail Bar          14

Beer Bar              17

Bar                   42

Majority of Bars in Toronto have a 'Venue Category' of Bar -47,Beer Bar-17,and Cocktail Bar - 14


I then used KMeans to get the mean frequency and cluster my data with the top 10 venues per neighborhood. I chose this method so I can choose the cluster out of 6 that has the most bars listed as a top 10 most common venue.

I used a folium map to display the clusters to help me find the top 3 best neighborhoods to recommend opening a video game bar.

  My intention is to find the neighborhoods in which there is a popularity of bars and is also in close proximity to the gaming cafes as with that data being our only evidence of venues being centered around "Gaming" 
  
## Results
##### Cluster 0 
- This cluster only had one neighborhood of Roselawn so there is not enough variety to go off of to find the best location.

##### Cluster 1 
- This cluster had the most neighborhoods and with large variety. It also had 15 neighborhoods with bars listed as the top 10 most common venues.

##### Cluster 2 
- This cluster returned 10 neighborhoods with Park and Diner listed in the the top common venues and no bars
since this cluster is large I will list the neighborhoods with the neighborhood name and Bar venue place.

Northwood Park, York University - Bar is 4th most common venue

Studio District - 7th most common venue

Berczy Park - Cocktail Bar is 2nd most common venue, and Beer Bar is 5th most common

Adelaide,King,Richmond - 8th most common venue

Harbord,University of Toronto - 5th most common

Chinatown,Grange Park,Kensington Market - 3rd most common venue, Cocktail Bar 10th most common venue

Stn A PO Boxes 25 The Esplanade - Cocktail Bar 4th most common venue, Beer Bar 6th

Dovercourt Village, Dufferin - 9th most common venue

Little Portugal, Trinity - 1st most common venue

Brockton, Exhibition Place,Parkdale Village - 9th most common venue

Del Ray,Keelesdale,Mount Dennis,Silverthorn - 1st most common venue

High Park,The Junction South - 1st most common venue

Parkdale,Roncesvalles - 4th most common venue

Runnymede,Swansea - 10th most common venue

Northwest - 3rd most common venue


##### Cluster 3 
- This cluster only returned 1 neighborhood. While it did have Bar listed as the top most common venue, it is the furthest away from the neighborhood with "Gaming Cafe"

##### Cluster 4 
- This cluster only lists 5 neighborhoods mostly with parks and Donut Shops 

##### Cluster 5 
-This cluster only lists one neighborhood with Motel as the top venue and no bars. 

## Discussion



