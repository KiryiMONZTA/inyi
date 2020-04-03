# Kiryi's INYI
A simple INI file reader.

## Installation
```bash
composer require kiryi/inyi
```

## Usage
```php
$inyi = new \Kiryi\Inyi\Reader($filepath);
$value = $inyi->get($key);
```

## Method Definition
```php
__construct(string $filepath)
```
### Parameters
**filepath**  
The filepath to your INI file. It is relative to your project's root directory.

```php
get(string $key)
```
### Parameters
**key**  
The key to read the value from the INI file. Key levels are seperated by double colons.

### Return Values
Returns the value corresponding to the key. Since it is possible to define strings as well as arrays in an INI file, the return type can be either.

## Example
*configuration/config.ini*
```ini
[database]
user = kiryi
password = qwe123
```
*src/ConfigController.php*
```php
$inyi = new \Kiryi\Inyi\Reader('configuration/config.ini');
$value = $inyi->get('database::user');
```
*returns*
```
kiryi
```
