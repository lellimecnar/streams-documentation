# Asset Tag

The `{{ asset }}` tag uses [Assetic](https://github.com/kriswallsmith/assetic) for managing, organizing, combining, and processing JavaScript and CSS assets to be included in the UI.


## Filters
Filters provide a way to manipulate assets. Multiple filters can be applied by passing a pipe (`|`) seperated array into the `filters` argument.

The asset tag will automatically try to determine what filters to apply, based on the asset extension. An asset with the file name of `script.coffee` will automaticaly have the `coffee` filter applied, because it has the standard CoffeeScript extension. If you choose to use a non-standard extension, you will need to apply the filter yourself.

### Available Filters

name     | extension  | description
---------|------------|------------
`coffee` | `*.coffee` | Compiles CoffeeScript into JS
`embed`  |            | Base64 encodes all image urls in the `group`
`less`   | `*.less`   | Compiles LESS into CSS
`min`    |            | Minifies CSS or JS, based on the `group`
`scss`   | `*.scss`   | Compiles SCSS into CSS


## Methods

### `add`<br/><sub>`{{ asset.add group asset filters }}`</sub>

Adds an asset to the specified group. Any filters specified will apply only to this asset, and not to the group as a whole.

### `path`<br/><sub>`{{ asset.path group filters }}`</sub>

Returns the relative path of the processed output file from the specified group.

### `paths`<br/><sub>`{{ asset.paths group filters }}`</sub>

Returns an array of paths for each of the assets, with filters applied, in the specified group.

### `url`<br/><sub>`{{ asset.url group filters }}`</sub>

Displays the absolute URL of the file returned by `path`.

### `script`<br/><sub>`{{ asset.script group filters }}`</sub>

Displays a single `<script>` tag, with the `src` being the URL returned from `url`.

### `scripts`<br/><sub>`{{ asset.scripts group filters }}`</sub>

Displays a `<script>` tag for each of the URLs from `paths`.

### `link`<br/><sub>`{{ asset.link group filters }}`</sub>

Displays a single `<link>` tag, with the `src` being the URL of the compiled CSS for the group.

### `links`<br/><sub>`{{ asset.links group filters }}`</sub>

Displays a `<link>` tag for each of the URLs from `paths`.


## Usage
The following example will add all JavaScript and CoffeScript files into the `scripts.js` group, compile the CoffeScript into JavaScript, combine all of the resulting code into one file, and insert the `<script>` tag for `scripts.js`.

**Example:**
```html
<!-- Add raw JavaScript libraries -->
{{ asset.add group="scripts.js" asset="theme::js/libs/*.js" }}

<!-- Add the CoffeScript files -->
{{ asset.add group="scripts.js" asset="theme::js/src/*.coffee" }}

<!-- Output the combined and minified JS file -->
{{ asset.script group="scripts.js" filter="min" }}
```

**Result:**
```html
<script type="text/javascript" src="scripts.js"></script>
```

Stylesheets work pretty much the same way:

**Example:**
```html
<!-- Add the LESS files -->
{{ asset.add group="styles.css" asset="theme::less/*.less" }}

<!-- And mix in some SCSS files too -->
{{ asset.add group="styles.css" asset="theme::less/*.scss" }}

<!-- Output the combined and minified CSS file -->
{{ asset.link group="styles.css" filter="min" }}
```

**Result:**
```html
<link rel="stylesheet" type="text/css" href="styles.css" />
```