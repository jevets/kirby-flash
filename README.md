# kirby-flash

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