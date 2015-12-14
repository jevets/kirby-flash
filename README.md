# Kirby Flash

Allows you to "flash" data to the session, which will be available via the session on the next page load, after which the data is removed from the session.

This is very useful for:

- Saving submitted form data for form validation, specifically for the GET/POST/GET paradigm
- Displaying Success or Error messages after a page reload

## Installation

Install with composer:

```bash
// composer.json

{
    "require": {
        "jevets/kirby-flash": "dev-master"
    },
    "repositories": {
        {
            "type": "git",
            "url": "https://github.com/jevets/kirby-flash.git"
        }
    }
}
```

Then run `composer install` or `composer update`.

## Usage

```php
use Jevets\Kirby\Flash;

$flash = new Flash;

$flash->set($key, $value);
```

## Examples

```php
// Save a success message
$flash->set('messages.success', ['Thank you for the great feedback!']);
```
```phtml
// some template file or snippet
<?php if (count($flash->get('messages.success')) > 0): ?>
<div class="alert alert-success">
    <?php foreach ($flash->get('messages.success') as $message): ?>
        <div><?= html($message) ?></div>
    <?php endforeach ?>
</div>
<?php endif ?>
```