
# Transfer View

## Structure

`TransferView`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `categoryData` | [BankCategoryData](../../doc/models/bank-category-data.md)\|[InternalCategoryData](../../doc/models/internal-category-data.md)\|[IssuedCard](../../doc/models/issued-card.md)\|[PlatformPayment](../../doc/models/platform-payment.md)\|null | Optional | This is a container for one-of cases. | getCategoryData(): | setCategoryData( categoryData): void |
| `id` | `?string` | Optional | The ID of the resource. | getId(): ?string | setId(?string id): void |
| `reference` | `string` | Required | The [`reference`](https://docs.adyen.com/api-explorer/#/transfers/latest/post/transfers__reqParam_reference) from the `/transfers` request. If you haven't provided any, Adyen generates a unique reference. | getReference(): string | setReference(string reference): void |

## Example

```php
use AdyenLib\Models\Builders\TransferViewBuilder;
use AdyenLib\Models\Builders\BankCategoryDataBuilder;
use AdyenLib\Models\Priority1Enum;
use AdyenLib\Models\Type310Enum;

$transferView = TransferViewBuilder::init(
    'reference2'
)
    ->categoryData(
        BankCategoryDataBuilder::init()
            ->priority(Priority1Enum::INSTANT)
            ->type(Type310Enum::BANK)
            ->build()
    )
    ->id('id6')
    ->build();
```

