# Developing Modules

## Module Structure

```
  ┌─ resources
  │  ├─ lang
  │  │  └─ en
  │  │     └─ ...
  │  │
  │  └─ views
  │     ├─ admin
  │     │  └─ ...
  │     │
  │     └─ public
  │        └─ ...
  │
  ├─ src
  │  ├─ Installer
  │  │  ├─ TodoFieldInstaller.php
  │  │  └─ TodoStreamInstaller.php
  │  │
  │  ├─ TodoModule.php
  │  └─ TodoModuleInstaller.php
  │
  └─ composer.json
```

## `Module` Class
```php
<?php namespace Anomaly\Streams\Addon\Module\Todo;

use Anomaly\Streams\Platform\Addon\Module\Module;

class TodoModule extends Module
{
    protected $nav = 'nav.system';

    protected $sections = [
        'todo' => [
            'url'     => 'admin/todo',
            'buttons' => [
                'create' => []
            ]
        ]
    ];

    protected $menu = [
        'settings' => [
            'title' => 'Settings',
            'path'  => 'admin/todo/settings'
        ]
    ];
}
```

## `ModuleInstaller` Class
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

## `FieldInstaller` Class
```php
<?php namespace Anomaly\Streams\Addon\Module\Todo\Installer;

use Anomaly\Streams\Platform\Field\FieldInstaller;

class TodoFieldInstaller extends FieldInstaller
{
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


## `StreamInstaller` Class
```php
<?php namespace Anomaly\Streams\Addon\Module\Todo\Installer;

use Anomaly\Streams\Platform\Stream\StreamInstaller;

class TodoStreamInstaller extends StreamInstaller
{
    protected $stream = [
        'is_hidden' => true
    ];

    protected $assignments = [
        'title' => ['is_required' => true],
        'description' => [],
        'due_date'
    ];
}
```

