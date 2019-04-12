Atom
====
PHP unique ID generator, based on the Twitter `snowflake` algorithm

### APIs:
```php
/*
 * Get the next unique ID
 */
string atom_next_id(int $type_id)

/*
 * Change unique ID to array includes: timestamp, server id and type id
 */
array atom_explain(string $id)
```

### example:
```php
<?php
$id = atom_next_id(1);
echo $id;

$info = atom_explain($id);
echo date('Y-m-d H:i:s', $info['timestamp']), PHP_EOL;
echo $info['server_id'], PHP_EOL;
echo $info['type_id'], PHP_EOL;
?>
```

### install:
```
$  cd ./atom
$  phpize
$  ./configure
$  make
$  sudo make install
```

### php.ini configure entries:
```
[atom]
atom.server_id = integer
atom.twepoch = uint64
```
