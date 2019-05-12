# Battle of the Neighborhoods Week 1 Final Project

## Introduction/Business Problem

  E-sports (competition using video games) has become more popular than ever. Video game bars (or cafes) 
  can be a great place for people whom are interested in competing professionally or casually to congregate and socialize.
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
   Then we will narrow down our Data to one Borough.
   
   
 Once we have retrieved all our data and put into a Pandas Dataframe, we will use KMeans clustering to cluster the neighborhoods and present the data on a folium map.
