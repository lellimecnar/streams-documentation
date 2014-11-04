# Helper Tag

## Methods

### `count`<br/><sub>`{{ helper.count array_or_countable mode }}`</sub>
Count all elements in an array, or something in an object.


See PHP Manual: [count()](http://php.net/manual/en/function.count.php)

### `empty`<br/><sub>`{{ helper.empty var }}`</sub>
Determine whether a variable is empty.

See PHP Manual: [count()](http://php.net/manual/en/function.count.php)

### `explode`<br/><sub>`{{ helper.explode delimiter string limit }}`</sub>
Split a string by string.

See PHP Manual: [explode()](http://php.net/manual/en/function.explode.php)

### `html_entity_decode`<br/><sub>`{{ helper.html_entity_decode string }}`</sub>
Convert all HTML entities to their applicable characters.

See PHP Manual: [html-entity-decode()](http://php.net/manual/en/function.html_entity_decode.php)

### `htmlentities`<br/><sub>`{{ helper.htmlentities string }}`</sub>
Convert all applicable characters to HTML entities.

See PHP Manual: [htmlentities()](http://php.net/manual/en/function.htmlentities.php)

### `htmlspecialchars`<br/><sub>`{{ helper.htmlspecialchars string }}`</sub>
Convert special characters to HTML entities.

See PHP Manual: [htmlspecialchars()](http://php.net/manual/en/function.htmlspecialchars.php)

### `htmlspecialchars_decode`<br/><sub>`{{ helper.htmlspecialchars_decode string }}`</sub>
Convert special HTML entities back to characters.

See PHP Manual: [htmlspecialchars_decode()](http://php.net/manual/en/function.htmlspecialchars-decode.php)

### `implode`<br/><sub>`{{ helper.implode glue pieces }}`</sub>
Join array elements with a string.

See PHP Manual: [implode()](http://php.net/manual/en/function.implode.php)

### `is_array`<br/><sub>`{{ helper.is_array var }}`</sub>
Finds whether a variable is an array.

See PHP Manual: [is_array()](http://php.net/manual/en/function.is-array.php)

### `is_int`<br/><sub>`{{ helper.is_int var }}`</sub>
Finds whether the type of the given variable is integer.

See PHP Manual: [is_int()](http://php.net/manual/en/function.is-int.php)

### `is_integer`<br/><sub>`{{ helper.is_integer var }}`</sub>
Alias of [is_int()](http://php.net/manual/en/function.is-int.php)

See PHP Manual: [is_integer()](http://php.net/manual/en/function.is-integer.php)

### `is_string`<br/><sub>`{{ helper.is_string var }}`</sub>
Find whether the type of a variable is string.

See PHP Manual: [is_string()](http://php.net/manual/en/function.is-string.php)

### `ltrim`<br/><sub>`{{ helper.ltrim string character }}`</sub>
Strip whitespace (or other characters) from the beginning of a string.

See PHP Manual: [ltrim()](http://php.net/manual/en/function.ltrim.php)

### `md5`<br/><sub>`{{ helper.md5 string }}`</sub>
Calculate the md5 hash of a string.

See PHP Manual: [md5()](http://php.net/manual/en/function.md5.php)

### `memory_get_usage`<br/><sub>`{{ helper.memory_get_usage }}`</sub>
Returns the amount of memory allocated to PHP.

See PHP Manual: [memory_get_usage()](http://php.net/manual/en/function.memory-get-usage.php)

### `nl2br`<br/><sub>`{{ helper.nl2br string }}`</sub>
Inserts HTML line breaks before all newlines in a string.

See PHP Manual: [nl2br()](http://php.net/manual/en/function.nl2br.php)

### `preg_match`<br/><sub>`{{ helper.preg_match pattern subject }}`</sub>
Perform a regular expression match.

See PHP Manual: [preg_match()](http://php.net/manual/en/function.preg-match.php)

### `preg_replace`<br/><sub>`{{ helper.preg_replace pattern replacement subject }}`</sub>
Perform a regular expression search and replace.

See PHP Manual: [preg_replace()](http://php.net/manual/en/function.preg-replace.php)

### `rtrim`<br/><sub>`{{ helper.rtrim string character }}`</sub>
Strip whitespace (or other characters) from the end of a string.

See PHP Manual: [rtrim()](http://php.net/manual/en/function.rtrim.php)

### `sprintf`<br/><sub>`{{ helper.sprintf format args... }}`</sub>
Return a formatted string.

See PHP Manual: [sprintf()](http://php.net/manual/en/function.sprintf.php)

### `str_replace`<br/><sub>`{{ helper.str_replace search replace subject }}`</sub>
Replace all occurrences of the search string with the replacement string.

See PHP Manual: [str_replace()](http://php.net/manual/en/function.str-replace.php)

### `str_word_count`<br/><sub>`{{ helper.str_word_count string }}`</sub>
Return information about words used in a string.

See PHP Manual: [str_word_count()](http://php.net/manual/en/function.str-word-count.php)

### `strip_tags`<br/><sub>`{{ helper.strip_tags string allowable tags }}`</sub>
Strip HTML and PHP tags from a string.

See PHP Manual: [strip_tags()](http://php.net/manual/en/function.strip-tags.php)

### `strpos`<br/><sub>`{{ helper.strpos haystack needle offset }}`</sub>
Find the position of the first occurrence of a substring in a string.

See PHP Manual: [strpos()](http://php.net/manual/en/function.strpos.php)

### `strtolower`<br/><sub>`{{ helper.strtolower string }}`</sub>
Make a string lowercase.

See PHP Manual: [strtolower()](http://php.net/manual/en/function.strtolower.php)

### `strtoupper`<br/><sub>`{{ helper.strtoupper string }}`</sub>
Make a string uppercase.

See PHP Manual: [strtoupper()](http://php.net/manual/en/function.strtoupper.php)

### `substr`<br/><sub>`{{ helper.substr string start length }}`</sub>
Return part of a string.

See PHP Manual: [substr()](http://php.net/manual/en/function.substr.php)

### `trim`<br/><sub>`{{ helper.trim string character }}`</sub>
Strip whitespace (or other characters) from the beginning and end of a string.

See PHP Manual: [trim()](http://php.net/manual/en/function.trim.php)

### `ucfirst`<br/><sub>`{{ helper.ucfirst string }}`</sub>


See PHP Manual: [ucfirst()](http://php.net/manual/en/function.ucfirst.php)
Make a string's first character uppercase.
### `ucwords`<br/><sub>`{{ helper.ucwords string }}`</sub>
Uppercase the first character of each word in a string.

See PHP Manual: [ucwords()](http://php.net/manual/en/function.ucwords.php)

## Usage

**Example:**
```html

```

**Result:**
```html

```