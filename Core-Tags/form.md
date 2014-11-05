# Form Tag

## Methods

### `open`<br/><sub>`{{ form.open ... }}`</sub>
Opens up a new `<form>` tag with the given attributes.

### `close`<br/><sub>`{{ form.close }}`</sub>
Closes the current `<form>`.

### `token`<br/><sub>`{{ form.token }}`</sub>
Generates a hidden field with the current CSRF token.

### `label`<br/><sub>`{{ form.label name value ... }}`</sub>
Creates an HTML `<label>` element with the given attributes.

### `input`<br/><sub>`{{ form.input type name value ... }}`</sub>
Creates an HTML `<input />` element with the given attributes.

### `text`<br/><sub>`{{ form.text name value ... }}`</sub>
Creates an HTML `<input type="text" />` element with the given attributes.

### `password`<br/><sub>`{{ form.password name ... }}`</sub>
Creates an HTML `<input type="password" />` element with the given attributes.

### `email`<br/><sub>`{{ form.email name value ... }}`</sub>
Creates an HTML `<input type="email" />` element with the given attributes.

### `url`<br/><sub>`{{ form.url name ... }}`</sub>

### `file`<br/><sub>`{{ form.file name ... }}`</sub>

### `textarea`<br/><sub>`{{ form.textarea name value ... }}`</sub>

### `select`<br/><sub>`{{ form.select name list selected ... }}`</sub>

### `range`<br/><sub>`{{ form.range name begin end selected ... }}`</sub>

### `year`<br/><sub>`{{ form.year name begin end selected ... }}`</sub>

### `month`<br/><sub>`{{ form.month name selected format ... }}`</sub>

### `checkbox`<br/><sub>`{{ form.checkbox name value checked ... }}`</sub>

### `radio`<br/><sub>`{{ form.radio name value checked ... }}`</sub>

### `reset`<br/><sub>`{{ form.reset value ... }}`</sub>

### `image`<br/><sub>`{{ form.image url name ... }}`</sub>

### `submit`<br/><sub>`{{ form.submit value ... }}`</sub>

### `button`<br/><sub>`{{ form.button value ... }}`</sub>

## Usage

**Example:**
```html

```

**Result:**
```html

```