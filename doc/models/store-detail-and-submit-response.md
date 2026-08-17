
# Store Detail and Submit Response

## Structure

`StoreDetailAndSubmitResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be returned in a particular response. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `pspReference` | `string` | Required | A new reference to uniquely identify this request. | getPspReference(): string | setPspReference(string pspReference): void |
| `refusalReason` | `?string` | Optional | In case of refusal, an informational message for the reason. | getRefusalReason(): ?string | setRefusalReason(?string refusalReason): void |
| `resultCode` | `string` | Required | The response:<br><br>* In case of success is payout-submit-received.<br>* In case of an error, an informational message is returned. | getResultCode(): string | setResultCode(string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\StoreDetailAndSubmitResponseBuilder;

$storeDetailAndSubmitResponse = StoreDetailAndSubmitResponseBuilder::init(
    'pspReference0',
    'resultCode6'
)
    ->additionalData(
        [
            'key0' => 'additionalData2',
            'key1' => 'additionalData1',
            'key2' => 'additionalData0'
        ]
    )
    ->refusalReason('refusalReason2')
    ->build();
```

