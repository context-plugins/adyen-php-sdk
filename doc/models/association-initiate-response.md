
# Association Initiate Response

## Structure

`AssociationInitiateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sdkInput` | `?string` | Optional | A string that you must pass to the authentication SDK to continue with the association process.<br><br>**Constraints**: *Maximum Length*: `20000` | getSdkInput(): ?string | setSdkInput(?string sdkInput): void |

## Example

```php
use AdyenLib\Models\Builders\AssociationInitiateResponseBuilder;

$associationInitiateResponse = AssociationInitiateResponseBuilder::init()
    ->sdkInput('sdkInput0')
    ->build();
```

