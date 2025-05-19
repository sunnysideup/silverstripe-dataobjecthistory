# Silverstripe dataobjecthistory

Adds a history tab to dataobjects

## Installation

Composer is the recommended way of installing Silverstripe modules.

```sh
composer require gorriecoe/silverstripe-dataobjecthistory
```

## Requirements

- silverstripe/framework ^5.0
- symbiote/silverstripe-gridfieldextensions ^4.0

## Author

- [Gorrie Coe](https://github.com/gorriecoe)

## Maintainers

- [Quinn Interactive](https://github.com/Quinn-Interactive)

## Example

```php
<?php

use SilverStripe\Versioned\Versioned;
use gorriecoe\DataObjectHistory\Extension\DataObjectHistory;

class MyObject extends DataObject
{
    private static $extensions = [
        Versioned::class . '.versioned',
        DataObjectHistory::class
    ];

    public function getCMSFields()
    {
        $fields = FieldList::create();
        ...
        $this->extend('updateCMSFields', $fields); // Required
        return $fields;
    }
}
```

## Version history

- 3.0.0
    - This release is by Quinn Interactive
    - Now follows PSR4
    - Namespaces have changed from lowercase plural to uppercase singular.
      This is a breaking change, so we have incremented to version 3.
        - `gorriecoe\DataObjectHistory\extensions` → `gorriecoe\DataObjectHistory\Extension`
        - `gorriecoe\DataObjectHistory\forms` → `gorriecoe\DataObjectHistory\Form`
