# Developing Extensions
Sometimes, you need to provide special functionality to a smaller subset of users. Rather than cluttering your addon with each of these special use cases, you can place that extra functionality into an installable extension which your addon can use to alter its functionality.

Here's an example: suppose you have a "Store" module which provides simple catalog management, and the checkout process. This is the most basic use case–every store will need some sort of product catalog, and a way for customers to buy products. Some stores might need more advanced functionality, though. Perhaps they want to sell downloadable goods, or give out coupon codes, or promotions. These extra use cases are excellent candidates for extensions.

## Writing an Extendable Module
Opening up your module to extensions is simple: `app('streams.extensions')` will return a `Collection` of all enabled extensions:

```php
	$myExtensions = app('streams.extensions')->search('module.my_module::my_module_extension');

	foreach ($myExtensions as $myExtension) {
		$myModuleData = $myExtension->myExtensionMethod();
	}
```

The example above can be used in your module to populate `$myModuleData` using special logic from your extension. This could be used to pull data from a third party API instead of a local database.

Extensions are just classes, so you can implement whatever special-case functionality you need from within your extension.