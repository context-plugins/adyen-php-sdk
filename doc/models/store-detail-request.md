
# Store Detail Request

## Structure

`StoreDetailRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be required for a particular request. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `bank` | [`?BankAccount`](../../doc/models/bank-account.md) | Optional | A container for bank account data.<br><br>> This field is mandatory if `card` is not provided. | getBank(): ?BankAccount | setBank(?BankAccount bank): void |
| `billingAddress` | [`?Address`](../../doc/models/address.md) | Optional | The billing address.<br><br>> The `billingAddress` object is required for cross-border payouts to and from Canada. Include all of the fields within this object. | getBillingAddress(): ?Address | setBillingAddress(?Address billingAddress): void |
| `card` | [`?Card`](../../doc/models/card.md) | Optional | A container for card data.<br><br>> This field is mandatory if `bank` is not provided. | getCard(): ?Card | setCard(?Card card): void |
| `dateOfBirth` | `DateTime` | Required | The date of birth.<br>Format: [ISO-8601](https://www.w3.org/TR/NOTE-datetime); example: YYYY-MM-DD<br>For Paysafecard it must be the same as used when registering the Paysafecard account.<br><br>> This field is mandatory for natural persons. | getDateOfBirth(): \DateTime | setDateOfBirth(\DateTime dateOfBirth): void |
| `entityType` | [`string(EntityType1Enum)`](../../doc/models/entity-type-1-enum.md) | Required | The type of the entity the payout is processed for. | getEntityType(): string | setEntityType(string entityType): void |
| `fraudOffset` | `?int` | Optional | An integer value that is added to the normal fraud score. The value can be either positive or negative. | getFraudOffset(): ?int | setFraudOffset(?int fraudOffset): void |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `nationality` | `string` | Required | The shopper's nationality.<br><br>A valid value is an ISO 2-character country code (e.g. 'NL').<br><br>**Constraints**: *Maximum Length*: `2` | getNationality(): string | setNationality(string nationality): void |
| `recurring` | [`Recurring`](../../doc/models/recurring.md) | Required | A container for the type of recurring contract to be retrieved.<br><br>The recurring.contract must be set to `PAYOUT` | getRecurring(): Recurring | setRecurring(Recurring recurring): void |
| `selectedBrand` | `?string` | Optional | The name of the brand to make a payout to.<br><br>For Paysafecard it must be set to `paysafecard`. | getSelectedBrand(): ?string | setSelectedBrand(?string selectedBrand): void |
| `shopperEmail` | `string` | Required | The shopper's email address. | getShopperEmail(): string | setShopperEmail(string shopperEmail): void |
| `shopperName` | [`?Name`](../../doc/models/name.md) | Optional | The shopper's name.<br><br>When the `entityType` is `Company`, the `shopperName.lastName` must contain the company name. | getShopperName(): ?Name | setShopperName(?Name shopperName): void |
| `shopperReference` | `string` | Required | The shopper's reference for the payment transaction. | getShopperReference(): string | setShopperReference(string shopperReference): void |
| `socialSecurityNumber` | `?string` | Optional | The shopper's social security number. | getSocialSecurityNumber(): ?string | setSocialSecurityNumber(?string socialSecurityNumber): void |
| `telephoneNumber` | `?string` | Optional | The shopper's phone number. | getTelephoneNumber(): ?string | setTelephoneNumber(?string telephoneNumber): void |

## Example

```php
use AdyenLib\Models\Builders\StoreDetailRequestBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\EntityType1Enum;
use AdyenLib\Models\Builders\RecurringBuilder;
use AdyenLib\Models\ContractEnum;
use AdyenLib\Models\TokenServiceEnum;
use AdyenLib\Models\Builders\BankAccountBuilder;
use AdyenLib\Models\Builders\AddressBuilder;
use AdyenLib\Models\Builders\CardBuilder;

$storeDetailRequest = StoreDetailRequestBuilder::init(
    DateTimeHelper::fromSimpleDateRequired('2016-03-13'),
    EntityType1Enum::NATURALPERSON,
    'merchantAccount2',
    'nationality8',
    RecurringBuilder::init()
        ->contract(ContractEnum::ENUM_ONECLICKRECURRING)
        ->recurringDetailName('recurringDetailName2')
        ->recurringExpiry(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
        ->recurringFrequency('recurringFrequency0')
        ->tokenService(TokenServiceEnum::VISATOKENSERVICE)
        ->build(),
    'shopperEmail4',
    'shopperReference8'
)
    ->additionalData(
        [
            'key0' => 'additionalData0'
        ]
    )
    ->bank(
        BankAccountBuilder::init()
            ->bankAccountNumber('bankAccountNumber8')
            ->bankCity('bankCity0')
            ->bankLocationId('bankLocationId2')
            ->bankName('bankName4')
            ->bic('bic0')
            ->build()
    )
    ->billingAddress(
        AddressBuilder::init(
            'city8',
            'country6',
            'houseNumberOrName0',
            'postalCode6',
            'street2'
        )
            ->stateOrProvince('stateOrProvince0')
            ->build()
    )
    ->card(
        CardBuilder::init()
            ->cvc('cvc0')
            ->expiryMonth('expiryMonth0')
            ->expiryYear('expiryYear0')
            ->holderName('holderName2')
            ->issueNumber('issueNumber8')
            ->build()
    )
    ->fraudOffset(28)
    ->build();
```

