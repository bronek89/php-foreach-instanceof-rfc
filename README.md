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

```php
foreach ($collection as $key => ClassName $val) {
}
```

```php
foreach ($collection as int $key => ClassName $val) {
}
```

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
