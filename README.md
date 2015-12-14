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
// Set data
flash('messages.success', ['Thanks for your feedback!']);
flash('messages.errors', ['Email is a required field']);
flash('username', 'jimihendrix');

// Get data
$success_messages = flash('messages.success');
$username = flash('username');
```

## Examples

```php
flash('messages.errors', ['Email is required.']);
flash('messages.errors', ['Password is required.']);

// or just
flash('messages.errors', [
    'Email is required',
    'Password is required',
]);
```

```php
<?php if (count(flash('messages.errors')) > 0): ?>
<div class="alert alert-error">
    <?php foreach (flash('messages.errors') as $message): ?>
        <div><?= html($message) ?></div>
    <?php endforeach ?>
</div>
<?php endif ?>
```