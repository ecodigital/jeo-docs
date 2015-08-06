## Core action hooks

### jeo_init

#### Description

This action is called after JEO has loaded. Useful for plugging new features for JEO.

#### Usage

```php
<?php
function my_jeo_plugin_init() {
  // Do something here
}
add_action('jeo_init', 'my_jeo_plugin_init');
?>
```

---

### jeo_enqueue_scripts

#### Description

This action is called after JEO core scripts has been loaded.

#### Usage

```php
<?php
function my_jeo_scripts() {
  wp_enqueue_script('jeo-dependent-script', get_stylesheet_directory_uri() . '/js/script.js');
}
add_action('jeo_enqueue_scripts', 'my_jeo_scripts');
?>
```

---

### jeo_map_setup_options

#### Description

This action is called inside the map settings metabox. You can create extra fields for your map by hooking into this action.

#### Usage

This action receives 1 parameter:

 - `$map_data`: The map data of the map being edited

```php
<?php
function my_new_setting($map_data) {
  ?>
  <p>
    <label for="my_new_field">My field</label>
    <input id="my_new_field" type="text" name="map_data[my_new_field]" value="<?php echo $map_data['my_new_field']; ?>" />
  </p>
  <?php
}
add_action('jeo_map_setup_options', 'my_new_setting');
?>
```

---

### jeo_pre_get_map

#### Description

This action is called inside the map query. Useful to modify the map query.

#### Usage

This action receives 1 parameter:

 - `$query`: the map query

```php
<?php
function my_pre_get_map($query) {
  if($_GET['my_input']) {
    // Modifying query here
  }
}
add_action('jeo_pre_get_map', 'my_pre_get_map');
?>
```

---

## Layers action hooks

### jeo_layer_save

#### Description

This action is called after a layer is saved.

#### Usage

Same concept of WordPress' [`save_post`](https://codex.wordpress.org/Plugin_API/Action_Reference/save_post) action hook.

This action receives 1 parameter:

 - `$post_id`: The layer post id

```php
<?php

function my_layer_save($post_id) {
  // Modify layer
}
add_action('jeo_layer_save', 'my_layer_save');

?>
```

---


## Markers action hooks

### jeo_markers_enqueue_scripts

#### Description

This action is called after the markers scripts has been loaded.

#### Usage

```php
<?php
function my_jeo_markers_scripts() {
  wp_enqueue_script('jeo-markers-dependent-script', get_stylesheet_directory_uri() . '/js/markers-script.js');
}
add_action('jeo_markers_enqueue_scripts', 'my_jeo_markers_scripts');
?>
```

---

### jeo_markers_before_print

#### Description

This action is called before the markers GeoJSON is printed on the page.

#### Usage

You can use it to modify the headers.

```php
<?php
function my_markers_before_print() {
  if(isset($_GET['download'])) {
    header('Content-Disposition: attachment;');
  }
}
add_action('jeo_markers_before_print', 'my_markers_before_print');
?>
```

---

### jeo_markers_after_print

#### Description

This action is called after the markers GeoJSON is printed on the page.

#### Usage

```php
<?php
function my_markers_after_print() {
  // Do something here
}
add_action('jeo_markers_after_print', 'my_markers_after_print');
?>
```

---

## Post geocoder action hooks

### jeo_geocode_scripts

#### Description

This action is called after the post geocoder scripts has been loaded.

#### Usage

```php
<?php
function my_geocode_scripts() {
    wp_enqueue_script('geocode-dependent-script', get_stylesheet_directory_uri() . '/js/geocode-script.js');
}
add_action('jeo_geocode_scripts', 'my_geocode_scripts');
?>
```

---

### jeo_geocode_box

#### Description

This action is called inside the post geocoder metabox, after the main form fields.

#### Usage

This action receives 1 parameter:

 - `$post`: the post object being edited

```php
<?php
function my_geocode_box_fields($post) {
  $field = get_post_meta($post->ID, 'my_new_field', true);
  ?>
  <p>
    <label for="my_new_field">My field</label>
    <input id="my_new_field" type="text" name="my_new_field" value="<?php echo $field; ?>" />
  </p>
  <?php
}
add_action('jeo_geocode_box', 'my_geocode_box_fields');
?>
```

---

### jeo_geocode_box_save

#### Description

This action is called after the post geocode data is saved.

#### Usage

This action receives 1 parameter:

 - `$post_id`: the ID of saved post

```php
<?php
function my_geocode_save($post_id) {
  if(isset($_REQUEST['my_new_field'])) {
    update_post_meta($post->ID, 'my_new_field', $_REQUEST['my_new_field']);
  }
}
add_action('jeo_geocode_box_save', 'my_geocode_save');
?>
```

---

## Embed action hooks

### jeo_before_embed

#### Description

This action is called before the embed template is displayed.

#### Usage

```php
<?php
function my_before_embed_content() {
  ?>
  <p>Some content here</p>
  <?php
}
add_action('jeo_before_embed', 'my_before_embed_content');
?>
```

---

### jeo_after_embed

#### Description

This action is called after the embed template is displayed.

#### Usage

```php
<?php
function my_after_embed_content() {
  ?>
  <p>Some content here</p>
  <?php
}
add_action('jeo_after_embed', 'my_before_embed_content');
?>
```

---
