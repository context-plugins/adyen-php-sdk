
# Details Request Authentication Data 1

Data for 3DS authentication.

## Structure

`DetailsRequestAuthenticationData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authenticationOnly` | `?bool` | Optional | Required to trigger the [authentication-only flow](https://docs.adyen.com/online-payments/3d-secure/authentication-only/). If set to **true**, you will only perform the 3D Secure 2 authentication, and will not proceed to the payment authorization.Default: **false**.<br><br>**Default**: `false` | getAuthenticationOnly(): ?bool | setAuthenticationOnly(?bool authenticationOnly): void |

## Example

```php
use AdyenLib\Models\Builders\DetailsRequestAuthenticationData1Builder;

$detailsRequestAuthenticationData1 = DetailsRequestAuthenticationData1Builder::init()
    ->authenticationOnly(false)
    ->build();
```

