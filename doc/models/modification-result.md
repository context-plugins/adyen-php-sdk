
# Modification Result

## Structure

`ModificationResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be returned in a particular modification response. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `pspReference` | `string` | Required | Adyen's 16-character string reference associated with the transaction/request. This value is globally unique; quote it when communicating with us about this request. | getPspReference(): string | setPspReference(string pspReference): void |
| `response` | [`string(ResponseEnum)`](../../doc/models/response-enum.md) | Required | Indicates if the modification request has been received for processing. | getResponse(): string | setResponse(string response): void |

## Example

```php
use AdyenLib\Models\Builders\ModificationResultBuilder;
use AdyenLib\Models\ResponseEnum;

$modificationResult = ModificationResultBuilder::init(
    'pspReference4',
    ResponseEnum::ENUM_CANCELRECEIVED
)
    ->additionalData(
        [
            'key0' => 'additionalData2',
            'key1' => 'additionalData3'
        ]
    )
    ->build();
```

