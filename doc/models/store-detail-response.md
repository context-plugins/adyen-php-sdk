
# Store Detail Response

## Structure

`StoreDetailResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be returned in a particular response. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `pspReference` | `string` | Required | A new reference to uniquely identify this request. | getPspReference(): string | setPspReference(string pspReference): void |
| `recurringDetailReference` | `string` | Required | The token which you can use later on for submitting the payout. | getRecurringDetailReference(): string | setRecurringDetailReference(string recurringDetailReference): void |
| `resultCode` | `string` | Required | The result code of the transaction. `Success` indicates that the details were stored successfully. | getResultCode(): string | setResultCode(string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\StoreDetailResponseBuilder;

$storeDetailResponse = StoreDetailResponseBuilder::init(
    'pspReference8',
    'recurringDetailReference0',
    'resultCode4'
)
    ->additionalData(
        [
            'key0' => 'additionalData0',
            'key1' => 'additionalData1'
        ]
    )
    ->build();
```

