
# Modify Request

## Structure

`ModifyRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be required for a particular payout request. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `originalReference` | `string` | Required | The PSP reference received in the `/submitThirdParty` response. | getOriginalReference(): string | setOriginalReference(string originalReference): void |

## Example

```php
use AdyenLib\Models\Builders\ModifyRequestBuilder;

$modifyRequest = ModifyRequestBuilder::init(
    'merchantAccount0',
    'originalReference8'
)
    ->additionalData(
        [
            'key0' => 'additionalData8'
        ]
    )
    ->build();
```

