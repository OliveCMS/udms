# UDMS - Universal Data Management System [![Build Status](https://travis-ci.org/OliveCMS/UDMS.svg?branch=master)](https://travis-ci.org/OliveCMS/UDMS)

UDMS is *Data Managements System* Hub for use database regardless of Data Management type.

## Installation

Install the latest version with

```
$ composer require olive-cms/udms
```

If you do not use Composer, you can download composered zip from [release Github page](https://github.com/OliveCMS/UDMS/releases/latest)

## Basic Usage

``` php
require_once 'vendor/autoload.php';
use Olive\UDMS\Core as udms;

// create a udms
$udms = new udms('/path/to/database/dir');

// set udms addon
$udms->setAddon('json');

// use it :)
$udms->school->student->find(
  [
    'id' => [
      '<' => 9300000,
      '>' => 9200000
    ],
    'lname' => [
      'match' => '(zade)+'
    ]
  ],
  // options
  [
    'relation' => false,
    'sort' => [
      'fname' => SORT_DESC
    ]
  ]
);
```

## Documentation

- [Usage Instructions](doc/01-usage.md)
- [Utility Classes](doc/02-utilities.md)
- [Addons Connect Instructions](doc/03-addons.md)

## Requirements

- udms 2.x works with PHP 5.5+.
- PDO mysql
- php mongodb module

## License

UDMS is licensed under the [MIT license](http://opensource.org/licenses/MIT).
