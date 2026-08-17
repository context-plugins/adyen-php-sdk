
# Issued Card

## Structure

`IssuedCard`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorisationType` | `?string` | Optional | The authorisation type. For example, **defaultAuthorisation**, **preAuthorisation**, **finalAuthorisation** | getAuthorisationType(): ?string | setAuthorisationType(?string authorisationType): void |
| `panEntryMode` | [`?string(PanEntryModeEnum)`](../../doc/models/pan-entry-mode-enum.md) | Optional | Indicates the method used for entering the PAN to initiate a transaction.<br><br>Possible values: **manual**, **chip**, **magstripe**, **contactless**, **cof**, **ecommerce**, **token**. | getPanEntryMode(): ?string | setPanEntryMode(?string panEntryMode): void |
| `processingType` | [`?string(ProcessingType1Enum)`](../../doc/models/processing-type-1-enum.md) | Optional | Contains information about how the payment was processed.<br><br>Possible values: **atmWithdraw**, **balanceInquiry**, **ecommerce**, **moto**, **pos**, **purchaseWithCashback**, **recurring**, **token**. | getProcessingType(): ?string | setProcessingType(?string processingType): void |
| `relayedAuthorisationData` | [`?RelayedAuthorisationData2`](../../doc/models/relayed-authorisation-data-2.md) | Optional | If you are using relayed authorisation, this object contains information from the relayed authorisation response from your server. | getRelayedAuthorisationData(): ?RelayedAuthorisationData2 | setRelayedAuthorisationData(?RelayedAuthorisationData2 relayedAuthorisationData): void |
| `schemeTraceId` | `?string` | Optional | The identifier of the original payment. This ID is provided by the scheme and can be alphanumeric or numeric, depending on the scheme. The `schemeTraceID` should refer to an original `schemeUniqueTransactionID` provided in an earlier payment (not necessarily processed by Adyen). A `schemeTraceId` is typically available for authorization adjustments or recurring payments. | getSchemeTraceId(): ?string | setSchemeTraceId(?string schemeTraceId): void |
| `schemeUniqueTransactionId` | `?string` | Optional | The unique identifier created by the scheme. This ID can be alphanumeric or numeric depending on the scheme. | getSchemeUniqueTransactionId(): ?string | setSchemeUniqueTransactionId(?string schemeUniqueTransactionId): void |
| `threeDSecure` | [`?ThreeDSecure2`](../../doc/models/three-d-secure-2.md) | Optional | The data of the result from the 3DS authentication. | getThreeDSecure(): ?ThreeDSecure2 | setThreeDSecure(?ThreeDSecure2 threeDSecure): void |
| `type` | [`?string(Type511Enum)`](../../doc/models/type-511-enum.md) | Optional | **issuedCard**<br><br>**Default**: `Type511Enum::ISSUEDCARD` | getType(): ?string | setType(?string type): void |
| `validationFacts` | [`?(TransferNotificationValidationFact[])`](../../doc/models/transfer-notification-validation-fact.md) | Optional | The evaluation of the validation facts. See [validation checks](https://docs.adyen.com/issuing/validation-checks) for more information. | getValidationFacts(): ?array | setValidationFacts(?array validationFacts): void |

## Example

```php
use AdyenLib\Models\Builders\IssuedCardBuilder;
use AdyenLib\Models\PanEntryModeEnum;
use AdyenLib\Models\ProcessingType1Enum;
use AdyenLib\Models\Builders\RelayedAuthorisationData2Builder;
use AdyenLib\Models\Type511Enum;

$issuedCard = IssuedCardBuilder::init()
    ->authorisationType('authorisationType6')
    ->panEntryMode(PanEntryModeEnum::MANUAL)
    ->processingType(ProcessingType1Enum::ECOMMERCE)
    ->relayedAuthorisationData(
        RelayedAuthorisationData2Builder::init()
            ->metadata(
                [
                    'key0' => 'metadata9',
                    'key1' => 'metadata8'
                ]
            )
            ->reference('reference8')
            ->build()
    )
    ->schemeTraceId('schemeTraceId6')
    ->type(Type511Enum::ISSUEDCARD)
    ->build();
```

