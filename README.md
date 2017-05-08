# Oracle DB driver for Laravel 4|5 via OCI8

## Laravel-p-OCI8

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Software License][ico-license]](LICENSE.md)
[![Total Downloads][ico-downloads]][link-downloads]

Laravel-OCI8 is an Oracle Database Driver package for [Laravel](http://laravel.com/). Laravel-OCI8 is an extension of [Illuminate/Database](https://github.com/illuminate/database) that uses [OCI8](http://php.net/oci8) extension to communicate with Oracle. Thanks to @taylorotwell.
## Documentations

## Quick Installation [Laravel 5.4]
```
$ composer require vincent/laravel-oci8:"5.4.*"
```

## Quick Installation [Laravel 5.3]
```
$ composer require vincent/laravel-oci8:"5.3.*"
```

## Quick Installation [Laravel 5.2]
```
$ composer require vincent/laravel-oci8:"5.2.*"
```

## Quick Installation [Laravel 5.1]
```
$ composer require vincent/laravel-oci8:"5.1.*"
```

## Service Provider
Once Composer has installed or updated your packages you need to register Laravel-OCI8. Open up `config/app.php` and find the providers key and add:
```php
Vincent\Oci8\Oci8ServiceProvider::class,
```
> Important: Since v4.0, the package will now use `Vincent\Oci8` (capital Y) namespace from `Vincent\Oci8` to follow the name standard for vendor name.

## Configuration (OPTIONAL)
Finally you can optionally publish a configuration file by running the following Artisan command.
If config file is not publish, the package will automatically use what is declared on your `.env` file database configuartion.

```
$ php artisan vendor:publish --tag=oracle
```

This will copy the configuration file to `config/oracle.php`.

> Note: For [Laravel Lumen configuration](http://lumen.laravel.com/docs/configuration#configuration-files), make sure you have a `config/database.php` file on your project and append the configuration below:

```php
'oracle' => [
    'driver'        => 'oracle',
    'tns'           => env('DB_TNS', ''),
    'host'          => env('DB_HOST', ''),
    'port'          => env('DB_PORT', '1521'),
    'database'      => env('DB_DATABASE', ''),
    'username'      => env('DB_USERNAME', ''),
    'password'      => env('DB_PASSWORD', ''),
    'charset'       => env('DB_CHARSET', 'AL32UTF8'),
    'prefix'        => env('DB_PREFIX', ''),
    'prefix_schema' => env('DB_SCHEMA_PREFIX', ''),
],
```

And run your laravel installation...

## [Laravel 5.2++] Oracle User Provider
When using oracle, we may encounter a problem on authentication because oracle queries are case sensitive by default. 
By using this oracle user provider, we will now be able to avoid user issues when logging in and doing a forgot password failure because of case sensitive search.

To use, just update `auth.php` config and set the driver to `oracle`
```php
'providers' => [
	'users' => [
		'driver' => 'oracle',
		'model' => App\User::class,
	],
]
```

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.


[ico-version]: https://img.shields.io/packagist/v/vincentshiqi/laravel-p-oci8.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-travis]: https://img.shields.io/travis/vincentshiqi/laravel-p-oci8/master.svg?style=flat-square
[ico-scrutinizer]: https://img.shields.io/scrutinizer/coverage/g/vincentshiqi/laravel-p-oci8.svg?style=flat-square
[ico-code-quality]: https://img.shields.io/scrutinizer/g/vincentshiqi/laravel-p-oci8.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/vincentshiqi/laravel-p-oci8.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/vincentshiqi/laravel-p-oci8
[link-downloads]: https://packagist.org/packages/vincentshiqi/laravel-p-oci8
[link-author]: https://github.com/vincentshiqi
