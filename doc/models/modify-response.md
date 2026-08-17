
# Modify Response

## Structure

`ModifyResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be returned in a particular response. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `pspReference` | `string` | Required | Adyen's 16-character string reference associated with the transaction. This value is globally unique; quote it when communicating with us about this response. | getPspReference(): string | setPspReference(string pspReference): void |
| `response` | `string` | Required | The response:<br><br>* In case of success, it is either `payout-confirm-received` or `payout-decline-received`.<br>* In case of an error, an informational message is returned. | getResponse(): string | setResponse(string response): void |

## Example

```php
use AdyenLib\Models\Builders\ModifyResponseBuilder;

$modifyResponse = ModifyResponseBuilder::init(
    'pspReference6',
    'response4'
)
    ->additionalData(
        [
            'key0' => 'additionalData4',
            'key1' => 'additionalData5',
            'key2' => 'additionalData6'
        ]
    )
    ->build();
```

