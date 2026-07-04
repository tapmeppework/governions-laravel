# README

## Preamble
The tapmeppe extension for the governance⚙️ tools based on Laravel.

## Installation
1. The package must be added to the extensions list in the main *composer.json* file:
	```jsonc
		// ...
		"require": {
			// ...
			"tapmeppe/governance": "@dev"
		}
	```
2. *If necessary* the repositories must be extended:
	```jsonc
		// ...
		"repositories": [
			// ...
			{
				"type": "path",
				"url": "extensions/governance"
			}
		]
	```
	This step can be skipped if the repositories already contains the following wild cards URL: `"url": "packages/*/*",`
3. After saving the composer.json file, run `composer update tapmeppe/governance` for:
	 - the package to be registered,
	 - the namespace to be indexed (implicit execution of the command `composer dump-autoload`), and 
	 - the changes to take effect.
4. *Optional* Optimise the application: `php artisan optimize:clear` -or- `php artisan optimize`
5. To make sure everything works, run the command `php artisan list`. The 'tapmeppe-' commands should be listed.
6. Next run the following command to publish the custom CSS and JS scripts:
   `php artisan vendor:publish --provider="tapmeppe\composer\helpers\Views" --tag=public --force`.
	 This command must be run every time the CSS and JS scripts are updated.
7. To make sure API routes are registered, run the following command: `php artisan route:list --path=governance`.
	 If the routes are not available, clear the cache with the following command `php artisan route:clear`.

