# UserLog PHP SDK

## Installation

```sh
composer require userlog/php
```

## Usage

### Initialize Client

```php
use UserLog\UserLog\Client;

$userlog = new Client('7f568d73sdfgwSD44FG573432435175763sUUfs7b1dbf108e5', 'my-saas');
```

The project name will be auto-injected in all requests.

### Log

```php

//
// The channel and the event name are the only required parameters.
$userlog->log('subscriptions', 'User subscribed!');

//
// Other parameters can be added when needed.
$userlog->log(
    channel: 'subscriptions',
    event: 'User subscribed!',
    userId: '123-456',
    description: 'A new user subscribed to the **premium plan**.',
    icon: '👍🏼',
    notify: true,
    tags: [
        'payment-method': 'card',
        'plan': 'monthly',
    ],
    parser: 'markdown',
    timestamp: 1709842921,
);
```

### Identify

```php

//
// Both the user id and the properties are required.
$userlog->identify(
    userId: '123-456',
    properties: [
        'active': 'yes',
        'signed-in': 'no',
    ],
);
```

### Insight

```php

//
// The title and the value are the only required parameters.
$userlog->insight('Subscribed Users', 12);

//
// Other parameters can be added when needed.
$userlog->log(
    title: 'Status',
    value: 'watered',
    icon: '🪴',
);
```

### Insight Mutate

```php

//
// The title and at least one mutation is required.
$userlog->insight('Subscribed Users', inc: 3);

//
// Other parameters can be added when needed.
$userlog->log(
    title: 'Subscribed Users',
    inc: -2,
    icon: '👍🏼',
);
```
