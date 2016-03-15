# php-foreach-instanceof-rfc

Given collection:

```php
$collection = [
  new \stdClass(),
  new ClassName(),
  new class extends ClassName() {},
  10,
  '10',
  'string value',
];
```

## Class or interface name filter

```php
foreach ($collection as ClassName $val) {
}
```

is equivalent of:

```php
foreach ($collection as $val) {
  if ($val instanceof ClassName) {
  }
}
```

## Scalar type filter

```php
foreach ($collection as int $val) {
}
```

is equivalent of:

```php
foreach ($collection as $val) {
  if (is_int($val)) {
  }
}
```

or

```php
foreach ($collection as $val) {
  $val = (int)$val;
}
```

## Key type filter

```php
foreach ($collection as int $key => $val) {
}
```

```php
foreach ($collection as int $key => ClassName $val) {
}
```

## Support for union types

```php
foreach ($collection as ClassName|int $val) {
}
```

## With unpacking

```php
foreach ($collection as array list($a, $v)) {
}
```

```php
foreach ($collection as $key => void) {
}
```

```php
foreach ($collection as int $key => void) {
}
```
