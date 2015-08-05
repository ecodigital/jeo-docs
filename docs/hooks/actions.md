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

## Layers action hooks

### jeo_layer_save

## Markers action hooks

### jeo_markers_enqueue_scripts

### jeo_markers_before_print

### jeo_markers_after_print

### jeo_geocode_scripts

### jeo_geocode_box

### jeo_geocode_box_save
