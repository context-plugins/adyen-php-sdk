
# Delegated Authentication Data

## Structure

`DelegatedAuthenticationData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sdkOutput` | `string` | Required | A base64-encoded block with the data required to register the SCA device. You obtain this information by using our authentication SDK.<br><br>**Constraints**: *Maximum Length*: `20000` | getSdkOutput(): string | setSdkOutput(string sdkOutput): void |

## Example

```php
use AdyenLib\Models\Builders\DelegatedAuthenticationDataBuilder;

$delegatedAuthenticationData = DelegatedAuthenticationDataBuilder::init(
    'sdkOutput2'
)->build();
```

