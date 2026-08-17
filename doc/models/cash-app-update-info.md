
# Cash App Update Info

## Structure

`CashAppUpdateInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logoUrl` | `?string` | Optional | The URL of the logo image shown in Cash App checkout next to payments. | getLogoUrl(): ?string | setLogoUrl(?string logoUrl): void |
| `merchantName` | `?string` | Optional | The merchant display name shown in Cash App checkout. | getMerchantName(): ?string | setMerchantName(?string merchantName): void |

## Example

```php
use AdyenLib\Models\Builders\CashAppUpdateInfoBuilder;

$cashAppUpdateInfo = CashAppUpdateInfoBuilder::init()
    ->logoUrl('logoUrl4')
    ->merchantName('merchantName4')
    ->build();
```

