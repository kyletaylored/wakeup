# Wake Up!

This is simple script that can be used to wake up a site environment by pinging the public URL before running any other Quicksilver scripts.

### Installation

This project is designed to be included from a site's `composer.json` file, and placed in its appropriate installation directory by [Composer Installers](https://github.com/composer/installers).

In order for this to work, you should have the following in your composer.json file:

```json
{
  "require": {
    "composer/installers": "^1"
  },
  "extra": {
    "installer-paths": {
      "web/private/scripts/quicksilver": ["type:quicksilver-script"]
    }
  }
}
```

The project can be included by using the command:

`composer require pantheon-quicksilver/wakeup`

### Example `pantheon.yml`

```yaml
api_version: 1

workflows:
  sync_code:
    after:
      - type: webphp
        description: Wakeup!
        script: private/scripts/quicksilver/pantheon-quicksilver/wakeup.php
```
