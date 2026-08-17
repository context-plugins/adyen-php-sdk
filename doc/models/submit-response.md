
# Submit Response

## Structure

`SubmitResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be returned in a particular response. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `pspReference` | `string` | Required | A new reference to uniquely identify this request. | getPspReference(): string | setPspReference(string pspReference): void |
| `refusalReason` | `?string` | Optional | In case of refusal, an informational message for the reason. | getRefusalReason(): ?string | setRefusalReason(?string refusalReason): void |
| `resultCode` | `string` | Required | The response:<br><br>* In case of success, it is `payout-submit-received`.<br>* In case of an error, an informational message is returned. | getResultCode(): string | setResultCode(string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\SubmitResponseBuilder;

$submitResponse = SubmitResponseBuilder::init(
    'pspReference2',
    'resultCode8'
)
    ->additionalData(
        [
            'key0' => 'additionalData4',
            'key1' => 'additionalData3',
            'key2' => 'additionalData2'
        ]
    )
    ->refusalReason('refusalReason4')
    ->build();
```

