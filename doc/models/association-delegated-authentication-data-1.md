
# Association Delegated Authentication Data 1

Contains authentication information required to associate the resource with the SCA device.

## Structure

`AssociationDelegatedAuthenticationData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sdkOutput` | `string` | Required | A base64-encoded block with the data required to authenticate the request. You obtain this information by using our authentication SDK.<br><br>**Constraints**: *Maximum Length*: `20000` | getSdkOutput(): string | setSdkOutput(string sdkOutput): void |

## Example

```php
use AdyenLib\Models\Builders\AssociationDelegatedAuthenticationData1Builder;

$associationDelegatedAuthenticationData1 = AssociationDelegatedAuthenticationData1Builder::init(
    'sdkOutput8'
)->build();
```

