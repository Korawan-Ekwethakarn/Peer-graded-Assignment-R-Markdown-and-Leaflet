# Peer-graded-Assignment-R-Markdown-and-Leaflet
Create a web page using R Markdown that features a map created with Leaflet.  Host your webpage on either GitHub Pages, RPubs, or NeoCities.
library(leaflet)
new_icon <- awesomeIcons(
  icon = 'ios-close',
  iconColor = 'black',
  library = 'ion',
  markerColor = "red"
)

content <- paste(sep = "<br/>",
  "<b>ICICI BANK</b>",
  "Kunal Icon Rd",
  "Pune, 411027"
)

my_map <- leaflet() %>%
    addTiles() %>%
    addAwesomeMarkers(lat = 18.593470, lng = 73.795123,
        icon = new_icon,
        popup = "Good Coffee at the local CCD") %>%
    addPopups(lat = 18.593417, lng = 73.795595, content,
        options = popupOptions(closeButton = FALSE)
    )
my_map
