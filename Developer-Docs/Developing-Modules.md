# Developing Modules

The example module used in this documentation can be found [on GitHub](https://github.com/anomalylabs/example-module).

## Module Structure
```bash
  ┌─ resources
  │  └─ lang
  │     └─ en
  │        ├─ addon.php
  │        └─ field.php
  │
  ├─ src
  │  ├─ Example
  │  │  └─ ExampleModel.php
  │  ├─ Http
  │  │  └─ Controller
  │  │     └─ ExampleController.php
  │  │
  │  ├─ Installer
  │  │  ├─ ExampleFieldInstaller.php
  │  │  └─ ExampleStreamInstaller.php
  │  │
  │  ├─ Ui
  │  │  ├─ Form
  │  │  │  └─ ExampleFormBuilder.php
  │  │  │
  │  │  └─ Table
  │  │     └─ ExampleTableBuilder.php
  │  │
  │  ├─ ExampleModule.php
  │  ├─ ExampleModuleInstaller.php
  │  └─ ExampleModuleServiceProvider.php
  │
  ├─ LICENSE.md
  ├─ README.md
  └─ composer.json
```

## Composer Package
[./composer.json](https://github.com/anomalylabs/example-module/blob/master/composer.json)

The `composer.json` file goes at the root of the module directory, and defines several fields which are used by the addons module:

| field | type | description |
|-------|-------------|
| [`name`](https://getcomposer.org/doc/04-schema.md#name) | `string` | This is the name of the package, and not the name of the module. It must follow the format of: `{vendor}/{slug}-{type}`. (ie, `anomaly/example-module`) |
| [`type`](https://getcomposer.org/doc/04-schema.md#type) | `string` | The type must be `streams-addon` |
| [`homepage`](https://getcomposer.org/doc/04-schema.md#homepage) | `string` | Used to provide a link to the website or documentation for your module. |
| [`authors`](https://getcomposer.org/doc/04-schema.md#authors) | `array` | A list of objects which define the author or authors of your module. |
| [`support`](https://getcomposer.org/doc/04-schema.md#support) | `object` | An object which provides a support email address, or a link to another form of support (ie: issue tracker, forum, wiki, irc, source) |
| [`autoload`](https://getcomposer.org/doc/04-schema.md#psr-4) | `object` | You must provide a PSR-4 autoload definition for your src directory. (ie, `"Anomaly\\ExampleModule\\": "src/"`)

You can also [define dependencies](https://getcomposer.org/doc/04-schema.md#package-links) specific to your module within the `composer.json` file. When you do, a `vendor` directory is created in the root of your module directory during installation. Each dependency will be autoloaded into its cooresponding namespace.

## Module Definition
[./src/ExampleModule.php](https://github.com/anomalylabs/example-module/blob/master/src/ExampleModule.php)

The module definition class extends `Anomaly\Streams\Platform\Addon\Module\Module`, and contains the information for creating admin navigation for your module. If your module requires no admin interface, this will just be an empty class file.

## Module Installer
[./src/ExampleModuleInstaller.php](https://github.com/anomalylabs/example-module/blob/master/src/ExampleModuleInstaller.php)

Your module's installer class contains a list of classes in `./src/Installer` to run, and which order to run them in. For modules requiring databse entries, these will likely include a [FieldInstaller](https://github.com/anomalylabs/example-module/blob/master/src/Installer/ExampleFieldInstaller.php) class, which will define the fields, and a [StreamInstaller](https://github.com/anomalylabs/example-module/blob/master/src/Installer/ExampleStreamInstaller.php) class, which will create the stream, and assign the fields to it.

## Service Provider
[./src/ExampleModuleServiceProvider.php](https://github.com/anomalylabs/example-module/blob/master/src/ExampleModuleServiceProvider.php)

All addons support an optional service provider, which is used to setup or bootstrap your module. For a module, this can be used to setup routes, etc. The service provider is a class in the `src` directory of your module, with `"ServiceProvider"` appended to the name of your module definition file. (ie, `ExampleModule.php` &#10137; `ExampleModuleServiceProvider.php`)