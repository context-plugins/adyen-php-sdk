
# Association Delegated Authentication Data

## Structure

`AssociationDelegatedAuthenticationData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sdkOutput` | `string` | Required | A base64-encoded block with the data required to authenticate the request. You obtain this information by using our authentication SDK.<br><br>**Constraints**: *Maximum Length*: `20000` | getSdkOutput(): string | setSdkOutput(string sdkOutput): void |

## Example

```php
use AdyenLib\Models\Builders\AssociationDelegatedAuthenticationDataBuilder;

$associationDelegatedAuthenticationData = AssociationDelegatedAuthenticationDataBuilder::init(
    'sdkOutput0'
)->build();
```

