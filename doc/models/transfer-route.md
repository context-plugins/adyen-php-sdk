
# Transfer Route

## Structure

`TransferRoute`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `category` | [`?string(Category2Enum)`](../../doc/models/category-2-enum.md) | Optional | The type of transfer.<br><br>Possible values:<br><br>- **bank**: Transfer to a [transfer instrument](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/transferInstruments__resParam_id) or a bank account. | getCategory(): ?string | setCategory(?string category): void |
| `country` | `?string` | Optional | The two-character ISO-3166-1 alpha-2 country code of the counterparty. For example, **US** or **NL**. | getCountry(): ?string | setCountry(?string country): void |
| `currency` | `?string` | Optional | The three-character ISO currency code of transfer. For example, **USD** or **EUR**. | getCurrency(): ?string | setCurrency(?string currency): void |
| `priority` | [`?string(Priority2Enum)`](../../doc/models/priority-2-enum.md) | Optional | The priority for the bank transfer. This sets the speed at which the transfer is sent and the fees that you have to pay. Possible values:<br><br>* **regular**: For normal, low-value transactions.<br><br>* **fast**: A faster way to transfer funds, but the fees are higher. Recommended for high-priority, low-value transactions.<br><br>* **wire**: The fastest way to transfer funds, but this has the highest fees. Recommended for high-priority, high-value transactions.<br><br>* **instant**: For instant funds transfers within the United States and in [SEPA locations](https://www.ecb.europa.eu/paym/integration/retail/sepa/html/index.en.html).<br><br>* **crossBorder**: For high-value transfers to a recipient in a different country.<br><br>* **internal**: For transfers to an Adyen-issued business bank account (by bank account number/IBAN). | getPriority(): ?string | setPriority(?string priority): void |
| `requirements` | array<[AdditionalBankIdentificationRequirement](../../doc/models/additional-bank-identification-requirement.md)\|[AddressRequirement](../../doc/models/address-requirement.md)\|[AmountMinMaxRequirement](../../doc/models/amount-min-max-requirement.md)\|[AmountNonZeroDecimalsRequirement](../../doc/models/amount-non-zero-decimals-requirement.md)\|[BankAccountIdentificationTypeRequirement](../../doc/models/bank-account-identification-type-requirement.md)\|[IbanAccountIdentification](../../doc/models/iban-account-identification.md)Requirement\|[PaymentInstrumentRequirement](../../doc/models/payment-instrument-requirement.md)\|USInstantPayout[AddressRequirement](../../doc/models/address-requirement.md)\|USInternationalAch[AddressRequirement](../../doc/models/address-requirement.md)\|[USInternationalAchPriorityRequirement](../../doc/models/us-international-ach-priority-requirement.md)>\|null | Optional | This is Array of a container for one-of cases. | getRequirements(): ?array | setRequirements(?array requirements): void |

## Example

```php
use AdyenLib\Models\Builders\TransferRouteBuilder;
use AdyenLib\Models\Category2Enum;
use AdyenLib\Models\Priority2Enum;
use AdyenLib\Models\Builders\AdditionalBankIdentificationRequirementBuilder;
use AdyenLib\Models\AdditionalBankIdentificationTypeEnum;

$transferRoute = TransferRouteBuilder::init()
    ->category(Category2Enum::GRANTS)
    ->country('country4')
    ->currency('currency0')
    ->priority(Priority2Enum::INSTANT)
    ->requirements(
        [
            AdditionalBankIdentificationRequirementBuilder::init()
                ->additionalBankIdentificationType(AdditionalBankIdentificationTypeEnum::GBSORTCODE)
                ->description('description8')
                ->build()
        ]
    )
    ->build();
```

