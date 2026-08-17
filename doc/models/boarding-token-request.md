
# Boarding Token Request

## Structure

`BoardingTokenRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `boardingRequestToken` | `string` | Required | The boardingToken request token. | getBoardingRequestToken(): string | setBoardingRequestToken(string boardingRequestToken): void |

## Example

```php
use AdyenLib\Models\Builders\BoardingTokenRequestBuilder;

$boardingTokenRequest = BoardingTokenRequestBuilder::init(
    'boardingRequestToken4'
)->build();
```

