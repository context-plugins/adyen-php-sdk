
# Boarding Token Response

## Structure

`BoardingTokenResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `boardingToken` | `string` | Required | The boarding token that allows the Payments App to board. | getBoardingToken(): string | setBoardingToken(string boardingToken): void |
| `installationId` | `string` | Required | The unique identifier of the Payments App instance. | getInstallationId(): string | setInstallationId(string installationId): void |

## Example

```php
use AdyenLib\Models\Builders\BoardingTokenResponseBuilder;

$boardingTokenResponse = BoardingTokenResponseBuilder::init(
    'boardingToken4',
    'installationId2'
)->build();
```

