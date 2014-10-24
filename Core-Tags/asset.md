# Asset Tag

The `{{ asset }}` tag uses [Assetic](https://github.com/kriswallsmith/assetic) for managing, organizing, combining, and processing JavaScript and CSS assets to be included in the UI.


## Filters
Filters provide a way to manipulate assets. Multiple filters can be applied by passing a pipe (`|`) seperated array into the `filters` argument.

### Available Filters

name | description
-|-
`coffee` | Compiles CoffeeScript into JS
`embed` | Generates a `<style>` tag for embedding CSS
`less` | Compiles LESS into CSS
`min` | Minifies CSS or JS, based on the `group`
`scss` | Compiles SCSS into CSS


## Type Hinting

....

## Methods

### `add`<br/><sub>`{{ asset.add group asset filters }}`</sub>
....

### `path`<br/><sub>`{{ asset.path group filters }}`</sub>
....

### `paths`<br/><sub>`{{ asset.paths group filters }}`</sub>
....

### `url`<br/><sub>`{{ asset.url group filters }}`</sub>
....

### `script`<br/><sub>`{{ asset.script group filters }}`</sub>
....

### `style`<br/><sub>`{{ asset.style group filters }}`</sub>
....

### `styles`<br/><sub>`{{ asset.styles group filters }}`</sub>
....

### `scripts`<br/><sub>`{{ asset.scripts group filters }}`</sub>
....


## Usage

```
{{ asset.add group="script.js" asset="theme::js/*" }}
```