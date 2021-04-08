# Laravel Eloquent Where Not

[![Latest Version on Packagist](https://img.shields.io/packagist/v/protonemedia/inertiajs-events-laravel-dusk.svg?style=flat-square)](https://packagist.org/packages/protonemedia/inertiajs-events-laravel-dusk)
![run-tests](https://github.com/protonemedia/inertiajs-events-laravel-dusk/workflows/run-tests/badge.svg)
[![Quality Score](https://img.shields.io/scrutinizer/g/protonemedia/inertiajs-events-laravel-dusk.svg?style=flat-square)](https://scrutinizer-ci.com/g/protonemedia/inertiajs-events-laravel-dusk)
[![Total Downloads](https://img.shields.io/packagist/dt/protonemedia/inertiajs-events-laravel-dusk.svg?style=flat-square)](https://packagist.org/packages/protonemedia/inertiajs-events-laravel-dusk)
[![Buy us a tree](https://img.shields.io/badge/Treeware-%F0%9F%8C%B3-lightgreen)](https://plant.treeware.earth/protonemedia/inertiajs-events-laravel-dusk)

### 📺 Want to see this package in action? Join the live stream on December 10 at 13:30 CET: [https://youtu.be/fAY75SLQj3w](https://youtu.be/fAY75SLQj3w)

## Requirements

* PHP 7.4+
* Laravel 8.0 and higher

## Support

We proudly support the community by developing Laravel packages and giving them away for free. Keeping track of issues and pull requests takes time, but we're happy to help! If this package saves you time or if you're relying on it professionally, please consider [supporting the maintenance and development](https://github.com/sponsors/pascalbaljet).

## Blogpost


## Installation

You can install the package via composer:

```bash
composer require protonemedia/inertiajs-events-laravel-dusk
```

Add to your main JavaScript file:

```js
window.inertiaEventsCount = {
    navigateCount: 0,
    successCount: 0,
    errorCount: 0,
}
```

Vue instance:

```vue
new Vue({
    mounted() {
        Inertia.on('navigate', (event) => {
            window.inertiaEventsCount.navigateCount++;
        })

        Inertia.on('success', (event) => {
            window.inertiaEventsCount.successCount++;
        })

        Inertia.on('error', (event) => {
            window.inertiaEventsCount.errorCount++;
        })
    }
})
```

## Usage

```php
$this->browse(function (Browser $browser) use ($user, $newApplicationName) {
    $browser->loginAs($user)
        ->visit(route('applications.create'))
        ->type('name', 'New Application')
        ->click('Submit')
        ->waitForInertiaNavigate()
        ->assertRouteIs('applications.index')
        ->assertSee('Application Created!');
});
```

### Testing

``` bash
composer test
```

### Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information about what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Other Laravel packages

* [`Laravel Analytics Event Tracking`](https://github.com/protonemedia/laravel-analytics-event-tracking): Laravel package to easily send events to Google Analytics.
* [`Laravel Blade On Demand`](https://github.com/protonemedia/laravel-blade-on-demand): Laravel package to compile Blade templates in memory.
* [`Laravel Cross Eloquent Search`](https://github.com/protonemedia/laravel-cross-eloquent-search): Laravel package to search through multiple Eloquent models.
* [`Laravel Eloquent Scope as Select`](https://github.com/protonemedia/laravel-eloquent-scope-as-select): Stop duplicating your Eloquent query scopes and constraints in PHP. This package lets you re-use your query scopes and constraints by adding them as a subquery.
* [`Laravel Eloquent Where Not`](https://github.com/protonemedia/laravel-eloquent-where-not): This Laravel package allows you to flip/invert an Eloquent scope, or really any query constraint.
* [`Laravel FFMpeg`](https://github.com/protonemedia/laravel-ffmpeg): This package provides an integration with FFmpeg for Laravel. The storage of the files is handled by Laravel's Filesystem.
* [`Laravel Form Components`](https://github.com/protonemedia/laravel-form-components): Blade components to rapidly build forms with Tailwind CSS Custom Forms and Bootstrap 4. Supports validation, model binding, default values, translations, includes default vendor styling and fully customizable!
* [`Laravel Paddle`](https://github.com/protonemedia/laravel-paddle): Paddle.com API integration for Laravel with support for webhooks/events.
* [`Laravel Verify New Email`](https://github.com/protonemedia/laravel-verify-new-email): This package adds support for verifying new email addresses: when a user updates its email address, it won't replace the old one until the new one is verified.
* [`Laravel WebDAV`](https://github.com/protonemedia/laravel-webdav): WebDAV driver for Laravel's Filesystem.

### Security

If you discover any security related issues, please email pascal@protone.media instead of using the issue tracker.

## Credits

- [Pascal Baljet](https://github.com/protonemedia)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

## Treeware

This package is [Treeware](https://treeware.earth). If you use it in production, then we ask that you [**buy the world a tree**](https://plant.treeware.earth/pascalbaljetmedia/inertiajs-events-laravel-dusk) to thank us for our work. By contributing to the Treeware forest you’ll be creating employment for local families and restoring wildlife habitats.
