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

### jeo_map_legend

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

## Markers filter hooks

### jeo_enable_clustering

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

### jeo_markers_enable_transient

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

### jeo_markers_enable_browser_caching

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

### jeo_geocode_type

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

### jeo_geocode_service

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

### jeo_gmaps_api_key

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

### jeo_use_marker_extent

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

### jeo_marker_extent_default_zoom

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

### jeo_markerclusterer_options

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

### jeo_marker_base_query

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

### jeo_marker_query

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

### jeo_markers_cache_key

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

### jeo_markers_data

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

### jeo_geojson_content_type

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

### jeo_markers_geojson

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

### jeo_markers_limit

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
