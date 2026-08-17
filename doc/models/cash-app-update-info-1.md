
# Cash App Update Info 1

Details to provide if `type` is **cashapp**.

## Structure

`CashAppUpdateInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logoUrl` | `?string` | Optional | The URL of the logo image shown in Cash App checkout next to payments. | getLogoUrl(): ?string | setLogoUrl(?string logoUrl): void |
| `merchantName` | `?string` | Optional | The merchant display name shown in Cash App checkout. | getMerchantName(): ?string | setMerchantName(?string merchantName): void |

## Example

```php
use AdyenLib\Models\Builders\CashAppUpdateInfo1Builder;

$cashAppUpdateInfo1 = CashAppUpdateInfo1Builder::init()
    ->logoUrl('logoUrl6')
    ->merchantName('merchantName6')
    ->build();
```

