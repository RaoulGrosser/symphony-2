# Symfony PSR-2 CodeSniffer ruleset 

Provide Symfony PSR CodeSniffer ruleset

* PSR-1 & PSR-2
* Symfony standard
* Symfony naming conventions

Strongly inspired by [OpenSky Symfony2 coding standard](https://github.com/opensky/Symfony2-coding-standard) (forked InterfaceSuffixSniff).
Yet, this ruleset rely on CodeSniffer PSR-1 & 2 sniffs and add Symfony standard & naming conventions. It's also allow chained calls (fluent interface).

## Installation

1. Install phpcs:

        pear install PHP_CodeSniffer

2. Find your PEAR directory:

        pear config-show | grep php_dir

3. Copy, symlink or check out this repo to a folder called Symfony inside the
   phpcs `Standards` directory:

        cd /path/to/pear/PHP/CodeSniffer/Standards
        git clone git://github.com/ludofleury/symfony-coding-standard.git Symfony

4. Set Symfony ruleset as your default coding standard:

        phpcs --config-set default_standard Symfony

5. Profit

        phpcs path/to/my/file.php


## Pragmatic & opinionated Customisations

### Allows fluent-interface chained calls syntax

```php
<?php

    $this
        ->getFoo()
            ->getBar()
            ->getBar()
    ; // This is allowed

    $this->getFoo()  ; // This is a violation

?>
```

## Known limitations

* "Exception" naming convention isn't enforced (Symfony require Exception suffix)
* PHPDoc blocks for all classes, methods, and functions isn't enforced at the moment

## Contributing

If you do contribute code to these sniffs, please make sure it conforms to the PEAR coding standard and that the unit tests still pass.

To check the coding standard, run from the Symfony-coding-standard source root:

        phpcs --ignore=Tests --standard=PEAR . -n

The unit-tests are run from within the PHP_CodeSniffer directory

* get the [CodeSniffer repository](https://github.com/squizlabs/PHP_CodeSniffer)
* symlink, copy or clone this repository at CodeSniffer/Standard/Symfony
* from the CodeSniffer repository root run `phpunit --filter Symfony_ tests/AllTests.php`

## Credit

[OpenSky](https://github.com/opensky) for the [Symfony2 coding standard](https://github.com/opensky/Symfony2-coding-standard)

