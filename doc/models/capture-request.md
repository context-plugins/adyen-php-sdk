
# Capture Request

## Structure

`CaptureRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be required for a particular modification request.<br><br>The additionalData object consists of entries, each of which includes the key and value. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `merchantAccount` | `string` | Required | The merchant account that is used to process the payment. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `modificationAmount` | [`Amount`](../../doc/models/amount.md) | Required | The amount that needs to be captured. The `currency` must match the currency used in authorisation, the `value` must be smaller than or equal to the authorised amount. | getModificationAmount(): Amount | setModificationAmount(Amount modificationAmount): void |
| `mpiData` | [`?ThreeDSecureData`](../../doc/models/three-d-secure-data.md) | Optional | Authentication data produced by an MPI (Mastercard SecureCode, Visa Secure, or Cartes Bancaires). | getMpiData(): ?ThreeDSecureData | setMpiData(?ThreeDSecureData mpiData): void |
| `originalMerchantReference` | `?string` | Optional | The original merchant reference to cancel. | getOriginalMerchantReference(): ?string | setOriginalMerchantReference(?string originalMerchantReference): void |
| `originalReference` | `string` | Required | The original pspReference of the payment to modify.<br>This reference is returned in:<br><br>* authorisation response<br>* authorisation notification | getOriginalReference(): string | setOriginalReference(string originalReference): void |
| `platformChargebackLogic` | [`?PlatformChargebackLogic`](../../doc/models/platform-chargeback-logic.md) | Optional | Defines how to book chargebacks when using [Adyen for Platforms](https://docs.adyen.com/adyen-for-platforms-model). | getPlatformChargebackLogic(): ?PlatformChargebackLogic | setPlatformChargebackLogic(?PlatformChargebackLogic platformChargebackLogic): void |
| `reference` | `?string` | Optional | Your reference for the payment modification. This reference is visible in Customer Area and in reports.<br>Maximum length: 80 characters. | getReference(): ?string | setReference(?string reference): void |
| `splits` | [`?(Split[])`](../../doc/models/split.md) | Optional | An array of objects specifying how the amount should be split between accounts when using Adyen for Platforms. For more information, see how to split payments for [platforms](https://docs.adyen.com/platforms/automatic-split-configuration/). | getSplits(): ?array | setSplits(?array splits): void |
| `tenderReference` | `?string` | Optional | The transaction reference provided by the PED. For point-of-sale integrations only. | getTenderReference(): ?string | setTenderReference(?string tenderReference): void |
| `uniqueTerminalId` | `?string` | Optional | Unique terminal ID for the PED that originally processed the request. For point-of-sale integrations only. | getUniqueTerminalId(): ?string | setUniqueTerminalId(?string uniqueTerminalId): void |

## Example

```php
use AdyenLib\Models\Builders\CaptureRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\ThreeDSecureDataBuilder;
use AdyenLib\Models\AuthenticationResponseEnum;
use AdyenLib\Models\ChallengeCancelEnum;
use AdyenLib\Models\DirectoryResponseEnum;
use AdyenLib\Models\Builders\PlatformChargebackLogicBuilder;
use AdyenLib\Models\BehaviorEnum;

$captureRequest = CaptureRequestBuilder::init(
    'merchantAccount0',
    AmountBuilder::init(
        'currency6',
        92
    )->build(),
    'originalReference8'
)
    ->additionalData(
        [
            'key0' => 'additionalData8',
            'key1' => 'additionalData9',
            'key2' => 'additionalData0'
        ]
    )
    ->mpiData(
        ThreeDSecureDataBuilder::init()
            ->authenticationResponse(AuthenticationResponseEnum::U)
            ->cavv('cavv0')
            ->cavvAlgorithm('cavvAlgorithm0')
            ->challengeCancel(ChallengeCancelEnum::ENUM_07)
            ->directoryResponse(DirectoryResponseEnum::U)
            ->build()
    )
    ->originalMerchantReference('originalMerchantReference2')
    ->platformChargebackLogic(
        PlatformChargebackLogicBuilder::init()
            ->behavior(BehaviorEnum::DEDUCTFROMONEBALANCEACCOUNT)
            ->costAllocationAccount('costAllocationAccount8')
            ->targetAccount('targetAccount6')
            ->build()
    )
    ->reference('reference6')
    ->build();
```

