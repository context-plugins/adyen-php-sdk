
# Authentication Session Response

## Structure

`AuthenticationSessionResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The unique identifier of the session. | getId(): ?string | setId(?string id): void |
| `token` | `?string` | Optional | The session token created. | getToken(): ?string | setToken(?string token): void |

## Example

```php
use AdyenLib\Models\Builders\AuthenticationSessionResponseBuilder;

$authenticationSessionResponse = AuthenticationSessionResponseBuilder::init()
    ->id('id6')
    ->token('token0')
    ->build();
```

