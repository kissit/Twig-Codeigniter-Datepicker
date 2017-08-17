## Twig-Codeigniter-Datepicker

A simple filter for Twig/Codeigniter to format and ensure a date field used for a datepicker has a sane default.  Primarily designed for use with 
default date columns of '0000-00-00'.  This is currently a very, VERY basic filter.

### Requirements
This filter is built on and requires usage of the Twig-Codeigniter library: https://github.com/bmatschullat/Twig-Codeigniter

It may be possible to use with other libraries as well with slight modifications.

### Installation
* Copy Datepicker.php into your CI project where your Twig extensions are, probably: application/third_party/Twig/extensions

* Add the following to the __construct() method in application/libraries/Twig_library.php
```
require_once (string)APPPATH . 'third_party/Twig/extensions/Datepicker.php';
```
* Add the following to the ci_function_init() method in application/libraries/Twig_library.php
```
$this->_twig_env->addExtension(new Twig_Extensions_Extension_Datepicker());
```

### Usage
In your template, use the filter as follows:

* Example 1, use the default format of "Y-m-d".  If you are filtering on a valid date it will be returned as is, otherwise the current date will be returned.
```
{{ '0000-00-00' | datepicker() }}
```

* Example 2, default to the first day of current month "Y-m-01".  If you are filtering on a valid date it will be returned as is, otherwise the current month, day 01 will be returned.
```
{{ '0000-00-00' | datepicker('Y-m-01') }}
```
