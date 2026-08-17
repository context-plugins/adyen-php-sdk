
# Submit Request

## Structure

`SubmitRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be required for a particular request. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `amount` | [`Amount`](../../doc/models/amount.md) | Required | A container object for the payable amount information of the transaction. | getAmount(): Amount | setAmount(Amount amount): void |
| `dateOfBirth` | `?DateTime` | Optional | The date of birth.<br>Format: ISO-8601; example: YYYY-MM-DD<br><br>For Paysafecard it must be the same as used when registering the Paysafecard account.<br><br>> This field is mandatory for natural persons.<br>> This field is required to update the existing `dateOfBirth` that is associated with this recurring contract. | getDateOfBirth(): ?\DateTime | setDateOfBirth(?\DateTime dateOfBirth): void |
| `entityType` | [`?string(EntityType2Enum)`](../../doc/models/entity-type-2-enum.md) | Optional | The type of the entity the payout is processed for.<br><br>Allowed values:<br><br>* NaturalPerson<br>* Company<br><br>> This field is required to update the existing `entityType` that is associated with this recurring contract. | getEntityType(): ?string | setEntityType(?string entityType): void |
| `fraudOffset` | `?int` | Optional | An integer value that is added to the normal fraud score. The value can be either positive or negative. | getFraudOffset(): ?int | setFraudOffset(?int fraudOffset): void |
| `merchantAccount` | `string` | Required | The merchant account identifier you want to process the transaction request with. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `nationality` | `?string` | Optional | The shopper's nationality.<br><br>A valid value is an ISO 2-character country code (e.g. 'NL').<br><br>> This field is required to update the existing nationality that is associated with this recurring contract. | getNationality(): ?string | setNationality(?string nationality): void |
| `recurring` | [`Recurring`](../../doc/models/recurring.md) | Required | A container for the type of recurring contract to be retrieved.<br><br>The `recurring.contract` must be set to "PAYOUT". | getRecurring(): Recurring | setRecurring(Recurring recurring): void |
| `reference` | `string` | Required | The merchant reference for this payout. This reference will be used in all communication to the merchant about the status of the payout. Although it is a good idea to make sure it is unique, this is not a requirement. | getReference(): string | setReference(string reference): void |
| `selectedRecurringDetailReference` | `string` | Required | This is the `recurringDetailReference` you want to use for this payout.<br><br>You can use the value LATEST to select the most recently used recurring detail. | getSelectedRecurringDetailReference(): string | setSelectedRecurringDetailReference(string selectedRecurringDetailReference): void |
| `shopperEmail` | `string` | Required | The shopper's email address. | getShopperEmail(): string | setShopperEmail(string shopperEmail): void |
| `shopperName` | [`?Name`](../../doc/models/name.md) | Optional | The shopper's name.<br><br>In case the `entityType` is `Company`, the `shopperName.lastName` must contain the company name.<br><br>> This field is required to update the existing `shopperName` associated with a recurring contract. | getShopperName(): ?Name | setShopperName(?Name shopperName): void |
| `shopperReference` | `string` | Required | The shopper's reference for the payout transaction. | getShopperReference(): string | setShopperReference(string shopperReference): void |
| `shopperStatement` | `?string` | Optional | The description of this payout. This description is shown on the bank statement of the shopper (if this is supported by the chosen payment method). | getShopperStatement(): ?string | setShopperStatement(?string shopperStatement): void |
| `socialSecurityNumber` | `?string` | Optional | The shopper's social security number. | getSocialSecurityNumber(): ?string | setSocialSecurityNumber(?string socialSecurityNumber): void |

## Example

```php
use AdyenLib\Models\Builders\SubmitRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\RecurringBuilder;
use AdyenLib\Models\ContractEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\TokenServiceEnum;
use AdyenLib\Models\EntityType2Enum;

$submitRequest = SubmitRequestBuilder::init(
    AmountBuilder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount8',
    RecurringBuilder::init()
        ->contract(ContractEnum::ENUM_ONECLICKRECURRING)
        ->recurringDetailName('recurringDetailName2')
        ->recurringExpiry(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
        ->recurringFrequency('recurringFrequency0')
        ->tokenService(TokenServiceEnum::VISATOKENSERVICE)
        ->build(),
    'reference8',
    'selectedRecurringDetailReference4',
    'shopperEmail0',
    'shopperReference4'
)
    ->additionalData(
        [
            'key0' => 'additionalData6'
        ]
    )
    ->dateOfBirth(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->entityType(EntityType2Enum::NATURALPERSON)
    ->fraudOffset(166)
    ->nationality('nationality4')
    ->build();
```

