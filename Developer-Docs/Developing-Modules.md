# Developing Modules

## Module Structure
```bash
  ┌─ resources
  │  ├─ lang
  │  │  └─ en
  │  │     └─ addon.yml
  │  │
  │  └─ views
  │     ├─ admin
  │     │  └─ # HTML views for admin pages
  │     │
  │     └─ public
  │        └─ # HTML views for fron-end/user-facing views
  │
  ├─ src
  │  ├─ Installer
  │  │  ├─ TodoFieldInstaller.php
  │  │  └─ TodoStreamInstaller.php
  │  │
  │  ├─ TodoModule.php
  │  └─ TodoModuleInstaller.php
  │
  ├─ vendor
  │  └─ # Auto-generated for composer dependencies
  │
  └─ composer.json
```

### Using Composer in Modules
The `composer.json` file at the root of the module directory is not required, but
you can use it to include dependencies specific to your module. A `vendor` directory is created in the root of your module directory upon installation. Each dependency will be autoloaded into its cooresponding namespace.

## Module Definition
The module definition class is really the only *required* file for a module. It extends `Anomaly\Streams\Platform\Addon\Module\Module`, and contains the information for creating admin navigation for your module. If your module requires no admin interface, this will just be an empty class file.

```php
<?php namespace Anomaly\Streams\Addon\Module\Todo;

use Anomaly\Streams\Platform\Addon\Module\Module;

class TodoModule extends Module
{
    /*
     * A translatable string representing
     * the primary admin nav group for this module,
     * or Null for no group.
     */
    protected $nav = 'nav.system';

    /*
     * The secondary navigation, specific to this module 
     */
    protected $sections = [
        'todo' => [
            'url'     => 'admin/todo',
            'buttons' => [
                'create' => []
            ]
        ]
    ];

    /*
     * The dropdown under the module heading
     * Typically for less-used actions, like settings
     */
    protected $menu = [
        'settings' => [
            'title' => trans('module.todo::addon.settings'),
            'path'  => 'admin/todo/settings'
        ]
    ];
}
```

## Module Installation
Your module's installer class contains a list of classes in `./src/Installer` to run, and which order to run them in.

```php
<?php namespace Anomaly\Streams\Addon\Module\Todo;

use Anomaly\Streams\Addon\Module\ModuleInstaller;

class TodoModuleInstaller extends ModuleInstaller
{
    protected $installers = [
        'TodoFieldInstaller',
        'TodoStreamInstaller'
    ];
}
```

### Installing Streams
For modules requiring databse entries, there are two installer classes for you to extend: `FieldInstaller` and `StreamInstaller`. FieldInstaller will define the fields, and StreamInstaller will create the stream, and assign the fields to it.

#### Defining Fields
```php
<?php namespace Anomaly\Streams\Addon\Module\Todo\Installer;

use Anomaly\Streams\Platform\Field\FieldInstaller;

class TodoFieldInstaller extends FieldInstaller
{
    /*
     * A list of fields to create.
     *
     * The array keys will become the field slugs,
     * and the values are the configuration
     * for the field type.
     *
     * See the documentation for each field type
     * too see what options are available.
     */
    protected $fields = [
        'title' => [
            'type' => 'text'
        ],
        'description' => [
            'type' => 'textarea'
        ],
        'due_date' => [
            'type' => 'datetime'
        ]
    ];
}
```
#### Defining Streams
```php
<?php namespace Anomaly\Streams\Addon\Module\Todo\Installer;

use Anomaly\Streams\Platform\Stream\StreamInstaller;

class TodoStreamInstaller extends StreamInstaller
{
    /*
     * The configuration for your stream
     */
    protected $stream = [
        'is_hidden' => true
    ];

    /*
     * An array of fields to assign to this stream,
     * with stream-specific configuration.
     */
    protected $assignments = [
        'title' => ['is_required' => true],
        'description' => [],
        'due_date'
    ];
}
```

