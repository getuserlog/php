# UserLog PHP SDK

## Installation

```sh
composer require userlog/php
```

## Usage

### Initialize Client

```php
use UserLog\PHP\Client;

$userlog = new Client('<API_KEY>', '<PROJECT_NAME>');
```

The project name will be auto-injected in all requests.

### Log

```php

// The channel name, event name and user_id are the only required parameters.
$userlog->log('subscriptions', 'User subscribed!', 'user@example.com');

// Other parameters can be added when needed.
$userlog->log(
    channel: 'subscriptions',
    event: 'User subscribed!',
    user_id: 'user@example.com',
    description: 'A new user subscribed to the premium plan.',
    icon: '👍🏼',
    notify: true,
    tags: [
        'payment-method' => 'card',
        'plan' => 'monthly',
    ],
);
```

### Identify

```php

// Both the user id and the properties are required.
$userlog->identify(
    userId: 'user@example.com',
    properties: [
        'active' => 'yes',
        'signed-in' => 'no',
    ],
);
```
