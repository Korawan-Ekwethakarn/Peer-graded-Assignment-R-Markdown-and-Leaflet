# Developing Data Products Assignment 1
# Peer-graded Assignment: R Markdown and Leaflet
# Interactive Map Assignment: Developing Data Products
# Create a web page using R Markdown that features a map created with Leaflet.
# Host your webpage on either GitHub Pages, RPubs, or NeoCities.
# Your webpage must contain the date that you created the document, and it must contain a map created with Leaflet. We would love to see you show off your creativity!ity!
install.packages("leaflet")
library(leaflet)
m <- leaflet()
m <- addTiles(m)
m <- addMarkers(m, lng=174.768, lat=-36.852, popup="The birthplace of R")
m 
