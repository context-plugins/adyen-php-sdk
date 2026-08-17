
# Third Party Token Redundancy Info 1

Configuration for creating redundant payment tokens with third-party token vaults using the Adyen Forward API. This feature requires Forward API webhook integration and pre-configured templates in your Adyen account. Contact your Adyen account manager for setup and availability.

## Structure

`ThirdPartyTokenRedundancyInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `requestParameters` | `?array<string,string>` | Optional | Request-specific parameter values to populate the template placeholders. Each key must match a placeholder defined in the template referenced by `requestTemplateCode`. | getRequestParameters(): ?array | setRequestParameters(?array requestParameters): void |
| `requestTemplateCode` | `string` | Required | Identifier for the third-party token request template configured in your Adyen account. This template defines the structure and endpoint for token requests. | getRequestTemplateCode(): string | setRequestTemplateCode(string requestTemplateCode): void |

## Example

```php
use AdyenLib\Models\Builders\ThirdPartyTokenRedundancyInfo1Builder;

$thirdPartyTokenRedundancyInfo1 = ThirdPartyTokenRedundancyInfo1Builder::init(
    'requestTemplateCode8'
)
    ->requestParameters(
        [
            'key0' => 'requestParameters7'
        ]
    )
    ->build();
```

