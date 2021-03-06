Laravel 5 Installation
============

Step 1
------
To Install Laravel-Piwik using Composer, the Default method for Laravel, add ``RobBrazier\Piwik`` to ``composer.json``::

	{
		"require": {
			"RobBrazier/Piwik": "~2.1"
		}
	}

Step 2
------
Then, add ``'RobBrazier\Piwik\PiwikServiceProvider'`` and ``'Piwik' => 'RobBrazier\Piwik\Facades\Piwik'`` to ``app/config/app.php``::

	'providers' = array(
		...
		'RobBrazier\Piwik\PiwikServiceProvider',
		...
	);

	[...]

	'aliases' = array(
		...
		'Piwik' => 'RobBrazier\Piwik\Facades\Piwik',
		...
	);

Step 3
------
Next, move the config out of the package, so that it doesn't get overwritten on each update::

	php artisan vendor:publish --provider="RobBrazier\Piwik\PiwikServiceProvider" --tag="config"

Step 4
------
Update your packages by running ``composer update``

Step 5
------
Finally, go to ``config/piwik.php`` and add your config settings such as server, username, password, apikey etc.
