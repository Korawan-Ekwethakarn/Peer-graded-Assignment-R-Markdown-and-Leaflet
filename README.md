# Developing Data Products Assignment 1
# Peer-graded Assignment: R Markdown and Leaflet
# Interactive Map Assignment: Developing Data Products
# Create a web page using R Markdown that features a map created with Leaflet.
# Host your webpage on either GitHub Pages, RPubs, or NeoCities.
# Your webpage must contain the date that you created the document, and it must contain a map created with Leaflet. We would love to see you show off your creativity!ity!
# Installation
install.packages("leaflet")
library(leaflet)
# My First Map
# Getting started with leaflet is easy. The leaflet() function creates a map widget that you can store in a variable so that you canmodify the map later on. You can add features to the map using the pipe operator (%>%) just like in dplyr. The addTiles()function adds mapping data from Open Street Map.
my_map <- leaflet() %>%
addTiles()
my_map
# Adding Markers
# You can add markers to your map one at a time using theaddMarkers() function by specifying the longitude and latitude.(Here’s a tip if you tend to mix them up.) You can specify popup text for when you click on the marker with the popup argument.
library(leaflet)
my_map <- my_map %>%
addMarkers(lat=39.2980803, lng=-76.5898801,
popup="Korawan's Office")
my_map
# Adding Many Markers
# Adding one marker at a time is often not practical if you want todisplay many markers. If you have a data frame with columns latand lng you can pipe that data frame into leaflet() to add all the points at once.
set.seed(2016-04-25)
df <- data.frame(lat = runif(20, min = 39.2, max = 39.3),
lng = runif(20, min = -76.6, max = -76.5))
df %>%
leaflet() %>%
addTiles() %>%
addMarkers()
# Making Custom Markers
# The blue markers that leaflet comes packaged with may not be enough depending on what you’re mapping. Thankfully you can make your own markers from .png files.
# Adding Multiple Popups
# When adding multiple markers to a map, you may want to add popups for each marker. You can specify a string of plain text foreach popup, or you can provide HTML which will be rendered inside of each popup
# Mapping Clusters
# Sometimes you might have so many points on a map that it doesn’tmake sense to plot every marker. In these situations leaflet allows you to plot clusters of markers using addMarkers(clusterOptions = markerClusterOptions()). When you zoom in to each cluster, the clusters will separate until you can see the individual markers.
# Examples
df <- data.frame(lat = runif(500, min = 39.25, max = 39.35),
lng = runif(500, min = -76.65, max = -76.55))
df %>%
leaflet() %>%
addTiles() %>%
addMarkers(clusterOptions = markerClusterOptions())
# Mapping Circle Markers
# Instead of adding markers or clusters you can easily add circle markers using addCircleMarkers().
# Examples
df <- data.frame(lat = runif(20, min = 39.25, max = 39.35),
lng = runif(20, min = -76.65, max = -76.55))
df %>%
leaflet() %>%
addTiles() %>%
addCircleMarkers()
# Drawing Circles
# You can draw arbitrary shapes on the maps you create, including circles and squares. The code below draws a map where the circle on each city is proportional to the population of that city.
# Drawing Rectangles
# You can add rectangles on leaflet maps as well:
# Examples
leaflet() %>%
addTiles() %>%
addRectangles(lat1 = 37.3858, lng1 = -122.0595,
lat2 = 37.3890, lng2 = -122.0625)
Adding Legends
# Adding a legend can be useful if you have markers on your map with
# different colors
Conclusion
For more details about the leaflet package for R visit
http://rstudio.github.io/leaflet/.
# I have problems about Shiney Application I try to download R 3.0.3 and many versions but very disappointed that no have this application that's why I have to submit code.
