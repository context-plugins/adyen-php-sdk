
# Localized Information 2

Localized information about the store.

## Structure

`LocalizedInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `localShopperStatement` | [`LocalShopperStatement[]`](../../doc/models/local-shopper-statement.md) | Required | An array of local shopper statements. Card schemes use this in the bank statement.<br><br>For Japan local shopper statements in both ja-Hani and ja-Kana are required. | getLocalShopperStatement(): array | setLocalShopperStatement(array localShopperStatement): void |

## Example

```php
use AdyenLib\Models\Builders\LocalizedInformation2Builder;
use AdyenLib\Models\Builders\LocalShopperStatementBuilder;

$localizedInformation2 = LocalizedInformation2Builder::init(
    [
        LocalShopperStatementBuilder::init(
            'script4',
            'value6'
        )->build()
    ]
)->build();
```

