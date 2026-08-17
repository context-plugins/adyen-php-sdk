
# Donation Request

## Structure

`DonationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `donationAccount` | `string` | Required | The Adyen account name of the charity. | getDonationAccount(): string | setDonationAccount(string donationAccount): void |
| `merchantAccount` | `string` | Required | The merchant account that is used to process the payment. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `modificationAmount` | [`Amount`](../../doc/models/amount.md) | Required | The amount to be donated.The `currency` must match the currency used in authorisation, the `value` must be smaller than or equal to the authorised amount. | getModificationAmount(): Amount | setModificationAmount(Amount modificationAmount): void |
| `originalReference` | `?string` | Optional | The original pspReference of the payment to modify.<br>This reference is returned in:<br><br>* authorisation response<br>* authorisation notification | getOriginalReference(): ?string | setOriginalReference(?string originalReference): void |
| `platformChargebackLogic` | [`?PlatformChargebackLogic`](../../doc/models/platform-chargeback-logic.md) | Optional | Defines how to book chargebacks when using [Adyen for Platforms](https://docs.adyen.com/adyen-for-platforms-model). | getPlatformChargebackLogic(): ?PlatformChargebackLogic | setPlatformChargebackLogic(?PlatformChargebackLogic platformChargebackLogic): void |
| `reference` | `?string` | Optional | Your reference for the payment modification. This reference is visible in Customer Area and in reports.<br>Maximum length: 80 characters. | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\DonationRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\PlatformChargebackLogicBuilder;
use AdyenLib\Models\BehaviorEnum;

$donationRequest = DonationRequestBuilder::init(
    'donationAccount8',
    'merchantAccount6',
    AmountBuilder::init(
        'currency6',
        92
    )->build()
)
    ->originalReference('originalReference2')
    ->platformChargebackLogic(
        PlatformChargebackLogicBuilder::init()
            ->behavior(BehaviorEnum::DEDUCTFROMONEBALANCEACCOUNT)
            ->costAllocationAccount('costAllocationAccount8')
            ->targetAccount('targetAccount6')
            ->build()
    )
    ->reference('reference0')
    ->build();
```

