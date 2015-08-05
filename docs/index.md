# JEO WordPress Theme

A WordPress parent theme for interactive maps and journalism

---

JEO WordPress Theme acts as a geojournalism platform which allows news organizations, bloggers and NGOs to publish news stories as layers of information on digital maps. With JEO, creating the interaction between data layers and contextual information is much more intuitive and interactive. The theme is ready for multilingual content and facilitates the publishing tasks.

You can post geotagged stories and create richly designed pages for each one of the featured stories. At same time, by simply imputing the ids of layers hosted on MapBox, you can manage sophisticated maps without loosing perfomance, add legends directly with HTML and set the map paramethers. All direct at the WordPress dashboard.

JEO wants to help journalists and NGOs to improve storytelling with maps. Creating a child theme with all its functionality is easy since it contains all the necessary hooks to customize layouts and data visualization.

---

## Features

 - Leaflet map library
 - Custom tile layers
 - [MapBox](http://mapbox.com/) maps
 - [CartoDB](http://cartodb.com/) maps
 - Layer filtering options, allowing you to mix tile layer, MapBox and CartoDB.
 - Geocoding WordPress posts using OpenStreetMaps or Google Maps supporting custom post types.
 - Google Street View support for Google Maps geocoding.
 - Customizable marker icons that can be associated to categories, custom taxonomies or posts directly.
 - Map markers query integrated to posts query.
 - GeoJSON API (any content /?geojson gives the geojson output). E.g.: yourwebsite.com/category/one/?geojson
 - Support [qTranslate](https://wordpress.org/plugins/qtranslate/) multilanguage plugin

---

## User tutorials

 - [Creating a map](Creating-a-map)
 - [Managing map groups](Managing-map-groups)

---

## Developer documentation

### Tutorials

 - [Starting a child theme](Starting-a-child-theme)

### [Template Tags](Template-Tags)
 - [General settings](Template-Tags#general-settings)
 - [Map](Template-Tags#map)

### [Action hooks](Action-hooks)
 - [Core](Action-hooks#core-action-hooks)
 - [Layers](Action-hooks#layers-action-hooks)
 - [Markers](Action-hooks#markers-action-hooks)
 - [Embed](Action-hooks#embed-action-hooks)

### [Filter hooks](Filter-hooks)
 - [Core](Filter-hooks#core-filter-hooks)
 - [Markers](Filter-hooks#markers-filter-hooks)
 - [Featured posts](Filter-hooks#featured-posts-filter-hooks)
 - [Marker icons](Filter-hooks#marker-icons-filter-hooks)
 - ["Share a map" feature](Filter-hooks#share-a-map-feature-filter-hooks)
 - [Embed](Filter-hooks#embed-filter-hooks)
 - [Range slider feature](Filter-hooks#range-slider-feature-filter-hooks)
 - [Admin page](Filter-hooks#admin-page-filter-hooks)

### [JavaScript Events](JavaScript-Events)
 - [Map](JavaScript-Events#map-events)
 - [Marker](JavaScript-Events#marker-events)
 - [Range slider feature](JavaScript-Events#range-slider-feature-events)
