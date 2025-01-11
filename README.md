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
    userId: 'user@example.com',
    description: 'A new user subscribed to the premium plan.',
    icon: '👍🏼',
    notify: true,
    tags: [
        'payment-method': 'card',
        'plan': 'monthly',
    ],
);
```

### Identify

```php

//
// Both the user id and the properties are required.
$userlog->identify(
    userId: 'user@example.com',
    properties: [
        'active': 'yes',
        'signed-in': 'no',
    ],
);
```
