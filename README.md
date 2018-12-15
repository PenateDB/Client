# PHP Client for PenateDB

Simple client for working with PenadeDB using Guzzle

## Installation

```bash
$ composer require penate/client
```


## Usage

```php
use Penate\Client\PenateClient;

$penate = new PenateClient('http://localhost:8000');

// Write and read
$penate->setItem('code', 100); // 100
$penate->getItem('code');      // 100

// Operations
$penate->increment('code');    // 101
$penate->decrement('code');    // 100

//Mass call
$penate->setItem('val1', 10);
$penate->setItem('val2', 20);

$penate->getItem(['val1', 'val2']); // [10,20]
```

You can also set temporary values.

```php
$penate->setItem('temporaryValue', 'Hello', 1);

$client->getItem('temporaryValue'); // 100

sleep(120); // after 2 minutes

$client->getItem('temporaryValue'); // null
```
