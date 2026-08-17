
# Delegated Authentication Data 1

Contains information required to register the SCA device.

## Structure

`DelegatedAuthenticationData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sdkOutput` | `string` | Required | A base64-encoded block with the data required to register the SCA device. You obtain this information by using our authentication SDK.<br><br>**Constraints**: *Maximum Length*: `20000` | getSdkOutput(): string | setSdkOutput(string sdkOutput): void |

## Example

```php
use AdyenLib\Models\Builders\DelegatedAuthenticationData1Builder;

$delegatedAuthenticationData1 = DelegatedAuthenticationData1Builder::init(
    'sdkOutput2'
)->build();
```

