# Developing Data Products Assignment 1
# Peer-graded Assignment: R Markdown and Leaflet
# Interactive Map Assignment: Developing Data Products
# Create a web page using R Markdown that features a map created with Leaflet.
# Host your webpage on either GitHub Pages, RPubs, or NeoCities.
# Your webpage must contain the date that you created the document, and it must contain a map created with Leaflet. We would love to see you show off your creativity!ity!
library(leaflet)
library(shiny)
my_map <- leaflet() %>% addTiles() 
my_map <- my_map %>% addMarkers(lng=103.7758052, lat=1.3283259, popup="My School")
my_map
