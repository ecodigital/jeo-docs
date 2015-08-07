## Core filter hooks

### jeo_directory

#### Description

Modify JEO core directory. Default is `get_template_directory() . '/inc'`.

#### Usage

```php
<?php
function my_jeo_dir($dir) {
  return get_stylesheet_directory() . '/jeo';
}
add_filter('jeo_directory', 'my_jeo_dir');
?>
```

---

### jeo_directory_uri

#### Description

Modify JEO core directory URI. Default is `get_template_directory_uri() . '/inc'`.

#### Usage

```php
<?php
function my_jeo_dir_uri($dir_uri) {
  return get_stylesheet_directory_uri() . '/jeo';
}
add_filter('jeo_directory_uri', 'my_jeo_dir_uri');
?>
```

---

### jeo_mapped_post_types

#### Description

Modify array of post types with mapping features. That includes the geocode box and use the post type inside the map posts query.

Default is all public post types, excluding pages.

You can also edit the mapped post types on the dashboard.

#### Usage

```php
<?php
function my_mapped_post_types($post_types) {
  return array('school', 'library');
}
add_filter('jeo_mapped_post_types', 'my_mapped_post_types');
?>
```

---

### jeo_use_map_query

#### Description

Rather the map related posts query should be used or not. Default is true.

You can also edit this on the dashboard.

#### Usage

```php
<?php
add_filter('jeo_use_map_query', '__return_false');
?>
```

---

### jeo_use_hash

#### Description

Modify the use of the map location hash. Default is true.

You can also edit this on the dashboard.

#### Usage

```php
<?php
add_filter('jeo_use_map_query', '__return_false');
?>
```

---

### jeo_mapbox_access_token

#### Description

Modify the MapBox library access token.

You can also edit this on the dashboard.

#### Usage

```php
<?php
function my_mapbox_token() {
  return 'pk.eyJ1IjoiaW5mb2FtYXpvbmlhIiwiYSI6InItajRmMGsifQ.JnRnLDiUXSEpgn7bPDzp7g';
}
add_filter('jeo_mapbox_access_token', 'my_mapbox_token');
?>
```

---

### jeo_posts_clauses_join

#### Description

Modify the map post query **join** clause.

#### Usage

This filter receives 3 parameters:

 - `$join`
 - `$clauses`: all the clauses
 - `$query`: the original query

```php
<?php
function my_jeo_posts_join($join, $clauses, $query) {
  // Modify $join here
  return $join;
}
add_filter('jeo_posts_clauses_join', 'my_jeo_posts_join', 10, 3);
?>
```

---

### jeo_posts_clauses_where

#### Description

Modify the map post query **where** clause.

#### Usage

This filter receives 3 parameters:

 - `$where`
 - `$clauses`: all the clauses
 - `$query`: the original query

```php
<?php
function my_jeo_posts_where($where, $clauses, $query) {
  // Modify $where here
  return $where;
}
add_filter('jeo_posts_clauses_where', 'my_jeo_posts_where', 10, 3);
?>
```

---

### jeo_posts_clauses_groupby

#### Description

Modify the map post query **groupby** clause.

#### Usage

This filter receives 3 parameters:

 - `$groupby`
 - `$clauses`: all the clauses
 - `$query`: the original query

```php
<?php
function my_jeo_posts_clauses($groupby, $clauses, $query) {
  // Modify $groupby here
  return $groupby;
}
add_filter('jeo_posts_clauses_groupby', 'my_jeo_posts_groupby', 10, 3);
?>
```

---

### jeo_map_conf

#### Description

Modify the array with the configuration of the map to be displayed.

#### Usage

This filter receives 2 parameters:

 - `$conf`: the configuration array
 - `$post`: the map post object

```php
<?php
function my_map_conf($conf, $post) {
  $conf['disableHash'] = true;
  return $conf;
}
add_filter('jeo_map_conf', 'my_map_conf', 10, 2);
?>
```

---

### jeo_mapgroup_conf

#### Description

Modify the array with the configuration of the mapgroup to be displayed.

#### Usage

This filter receives 2 parameters:

 - `$conf`: the configuration array
 - `$post`: the mapgroup post object

```php
<?php
function my_mapgroup_conf($conf, $post) {
  $conf['disableHash'] = true;
  return $conf;
}
add_filter('jeo_mapgroup_conf', 'my_mapgroup_conf', 10, 2);
?>
```

---

### jeo_map_data

#### Description

Modify the array with the map data to de displayed, including layers and legends.

#### Usage

This filter receives 2 parameters:

 - `$data`: the map data
 - `$post`: the map post

```php
<?php
function my_map_data($data, $post) {
  // Modify map data here
  return $data;
}
add_filter('jeo_map_data', 'my_map_data', 10, 2);
?>
```

---

### jeo_mapgroup_data

#### Description

Modify the array with the mapgroup data to de displayed.

#### Usage

This filter receives 2 parameters:

 - `$data`: the mapgroup data
 - `$post`: the mapgroup post

```php
<?php
function my_mapgroup_data($data, $post) {
  // Modify map data here
  return $data;
}
add_filter('jeo_mapgroup_data', 'my_mapgroup_data', 10, 2);
?>
```

---

## Markers filter hooks

### jeo_enable_clustering

#### Description

Modify the use of marker clustering. Default is false.

You can also edit this on the dashboard.

#### Usage

```php
<?php
add_filter('jeo_enable_clustering', '__return_true');
?>
```

---

### jeo_markers_enable_transient

#### Description

Use [transient API](https://codex.wordpress.org/Transients_API) to cache marker data. Default is true.

#### Usage

```php
<?php
add_filter('jeo_markers_enable_transient', '__return_false');
?>
```

---

### jeo_markers_enable_browser_caching

#### Description

Use browser cache on GeoJSON response. Default is true.

#### Usage

```php
<?php
add_filter('jeo_markers_enable_browser_caching', '__return_false');
?>
```

---

### jeo_geocode_type

#### Description

Rather to use `default` (address search) or `latlng` (direct coordinates) for post geocoding. Default is `default`.

You can also edit this on the dashboard.

#### Usage

```php
<?php
function my_geocode_type() {
  return 'latlng';
}
add_filter('jeo_geocode_type', 'my_geocode_type');
?>
```

---

### jeo_geocode_service

#### Description

Rather to use `osm` (OpenStreetMap Nominatim) or `gmaps` (Google Maps) geocode service. Default is `osm`.

You can also edit this on the dashboard.

*Note: `gmaps` requires API Key*

#### Usage

```php
<?php
function my_geocode_service() {
  return 'gmaps';
}
add_filter('jeo_geocode_service', 'my_geocode_service');
?>
```

---

### jeo_gmaps_api_key

#### Description

Modify the Google Maps api key, used for Google Maps geocode service.

You can also edit this on the dashboard.

#### Usage

```php
<?php
function my_gmaps_api_key() {
  return 'apikeyhere';
}
add_filter('jeo_gmaps_api_key', 'my_gmaps_api_key');
?>
```

---

### jeo_use_marker_extent

#### Description

Modify the use of the marker extent to center the map. Default is `false` for the front page and single map/mapgroup pages and `true` for other cases.

#### Usage

```php
<?php
function my_marker_extent() {
  // Never use marker extent
  return false;
}
add_filter('jeo_use_marker_extent', 'my_marker_extent');
?>
```

---

### jeo_marker_extent_default_zoom

#### Description

Set a default zoom for map centering on marker extent. Default is `false`.

#### Usage

```php
<?php
function my_marker_extent_default_zoom() {
  return 12;
}
add_filter('jeo_marker_extent_default_zoom', 'my_marker_extent_default_zoom');
?>
```

---

### jeo_markerclusterer_options

#### Description

Modify [Leaflet.markerclusterer](https://github.com/Leaflet/Leaflet.markercluster) options.

#### Usage

```php
<?php
function my_markerclusterer_options() {
  return array(
   'spiderfyOnMaxZoom' => false
  );
}
add_filter('jeo_markerclusterer_options', 'my_markerclusterer_options');
?>
```

---

### jeo_marker_base_query

#### Description

Modify the base query object for the map markers. This query object will still pass through JEO default settings to display markers.

The default query is the global `$wp_query`.

#### Usage

This filter receives 1 parameter:

 - `$query`: the marker base query object

```php
<?php
function my_marker_base_query($query) {
  if(is_home() || is_front_page()) {
    return new WP_Query();
  }
  return $query;
}
add_filter('jeo_marker_base_query', 'my_marker_base_query');
?>
```

---

### jeo_marker_query

#### Description

Modify the final query object for the map markers. After it passes through JEO default settings for marker queries.

#### Usage

This filter receives 1 parameter:

 -  `$query`: the marker query object

```php
<?php
function my_marker_query($query) {
  // Modify query here
  return $query;
}
add_filter('jeo_marker_query', 'my_marker_query');
?>
```

---

### jeo_markers_cache_key

#### Description

Modify the marker query cache key value for the transient api. Useful if you need more values to differentiate queries with hidden extra parameters.

#### Usage

This filter receives 2 parameters:

 - `$cache_key`: the cache key
 - `$query`: array with query parameters

```php
<?php
function my_markers_cache_key($cache_key, $query) {
  // Modify cache key here
  return $cache_key
}
add_filter('jeo_markers_cache_key', 'my_markers_cache_key', 10, 2);
?>
```

---

### jeo_markers_data

#### Description

Modify the markers' GeoJSON as an associative array.

#### Usage

This filter receives 2 parameters:

 - `$data`: the geojson array
 - `$markers_query`: the markers query object

```php
<?php
function my_markers_data($data, $markers_query) {
  // Modify geojson here
  return $data;
}
add_filter('jeo_markers_data', 'my_markers_data', 10, 2);
?>
```

---

### jeo_geojson_content_type

#### Description

Modify the `Content-Type` header for the GeoJSON response. Default is `application/json`.

#### Usage

```php
<?php
function my_geojson_content_type() {
  return 'application/vnd.geo+json';
}
add_filter('jeo_geojson_content_type', 'my_geojson_content_type');
?>
```

---

### jeo_markers_geojson

#### Description

Modify the already JSON encoded GeoJSON output.

#### Usage

```php
<?php
function my_markers_geojson($geojson) {
  // Modify GeoJSON here
  return $geojson;
}
add_filter('jeo_markers_geojson', 'my_markers_geojson');
?>
```

---

### jeo_markers_limit

#### Description

Modify the limit of markers to be displayed on the map. Default is `200`.

#### Usage

```php
<?php
function my_markers_limit() {
  // Unlimited markers
  return -1;
}
add_filter('jeo_markers_limit', 'my_markers_limit');
?>
```

---

### jeo_marker_bubble

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_marker_icon

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_marker_class

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_marker_data

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_marker_geometry

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_marker_coordinates

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_markers_geojson_key

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_markers_geojson_keys

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

## Marker icons filter hooks

### jeo_marker_taxonomies

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

## Featured posts filter hooks

### jeo_featured_post_types

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

## Range slider feature filter hooks

### jeo_range_slider_options

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_range_slider_filter_property

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

## "Share a map" feature filter hooks

### jeo_disable_share_map_menu

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_share_url

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

## Embed filter hooks

### jeo_embed_url

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_map_embed_conf

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_map_embed_geojson_conf

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

## Admin page filter hooks

### jeo_settings_tabs

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---

### jeo_settings_form_sections

#### Description

#### Usage

```php
<?php
function my_() {

}
add_filter('jeo_', 'my_');
?>
```

---
