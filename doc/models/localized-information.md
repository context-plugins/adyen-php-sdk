
# Localized Information

## Structure

`LocalizedInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `localShopperStatement` | [`LocalShopperStatement[]`](../../doc/models/local-shopper-statement.md) | Required | An array of local shopper statements. Card schemes use this in the bank statement.<br><br>For Japan local shopper statements in both ja-Hani and ja-Kana are required. | getLocalShopperStatement(): array | setLocalShopperStatement(array localShopperStatement): void |

## Example

```php
use AdyenLib\Models\Builders\LocalizedInformationBuilder;
use AdyenLib\Models\Builders\LocalShopperStatementBuilder;

$localizedInformation = LocalizedInformationBuilder::init(
    [
        LocalShopperStatementBuilder::init(
            'script4',
            'value6'
        )->build()
    ]
)->build();
```

