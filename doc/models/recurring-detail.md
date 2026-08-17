
# Recurring Detail

## Structure

`RecurringDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be returned in a particular response.<br><br>The additionalData object consists of entries, each of which includes the key and value. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `alias` | `?string` | Optional | The alias of the credit card number.<br><br>Applies only to recurring contracts storing credit card details | getAlias(): ?string | setAlias(?string alias): void |
| `aliasType` | `?string` | Optional | The alias type of the credit card number.<br><br>Applies only to recurring contracts storing credit card details. | getAliasType(): ?string | setAliasType(?string aliasType): void |
| `bank` | [`?BankAccount`](../../doc/models/bank-account.md) | Optional | A container for bank account data. | getBank(): ?BankAccount | setBank(?BankAccount bank): void |
| `billingAddress` | [`?Address`](../../doc/models/address.md) | Optional | The billing address. | getBillingAddress(): ?Address | setBillingAddress(?Address billingAddress): void |
| `card` | [`?Card`](../../doc/models/card.md) | Optional | A container for card data. | getCard(): ?Card | setCard(?Card card): void |
| `contractTypes` | `?(string[])` | Optional | Types of recurring contracts. | getContractTypes(): ?array | setContractTypes(?array contractTypes): void |
| `creationDate` | `?DateTime` | Optional | The date when the recurring details were created. | getCreationDate(): ?\DateTime | setCreationDate(?\DateTime creationDate): void |
| `firstPspReference` | `?string` | Optional | The `pspReference` of the first recurring payment that created the recurring detail. | getFirstPspReference(): ?string | setFirstPspReference(?string firstPspReference): void |
| `name` | `?string` | Optional | An optional descriptive name for this recurring detail. | getName(): ?string | setName(?string name): void |
| `networkTxReference` | `?string` | Optional | Returned in the response if you are not tokenizing with Adyen and are using the Merchant-initiated transactions (MIT) framework from Mastercard or Visa.<br><br>This contains either the Mastercard Trace ID or the Visa Transaction ID. | getNetworkTxReference(): ?string | setNetworkTxReference(?string networkTxReference): void |
| `paymentMethodVariant` | `?string` | Optional | The  type or sub-brand of a payment method used, e.g. Visa Debit, Visa Corporate, etc. For more information, refer to [PaymentMethodVariant](https://docs.adyen.com/development-resources/paymentmethodvariant). | getPaymentMethodVariant(): ?string | setPaymentMethodVariant(?string paymentMethodVariant): void |
| `recurringDetailReference` | `string` | Required | The reference that uniquely identifies the recurring detail. | getRecurringDetailReference(): string | setRecurringDetailReference(string recurringDetailReference): void |
| `shopperName` | [`?Name`](../../doc/models/name.md) | Optional | The name of the shopper. | getShopperName(): ?Name | setShopperName(?Name shopperName): void |
| `socialSecurityNumber` | `?string` | Optional | A shopper's social security number (only in countries where it is legal to collect). | getSocialSecurityNumber(): ?string | setSocialSecurityNumber(?string socialSecurityNumber): void |
| `tokenDetails` | [`?TokenDetails`](../../doc/models/token-details.md) | Optional | - | getTokenDetails(): ?TokenDetails | setTokenDetails(?TokenDetails tokenDetails): void |
| `transactionLinkId` | `?string` | Optional | The unique identifier for the transaction link, used for Mastercard recurring transactions. | getTransactionLinkId(): ?string | setTransactionLinkId(?string transactionLinkId): void |
| `variant` | `string` | Required | The payment method, such as “mc", "visa", "ideal", "paypal". | getVariant(): string | setVariant(string variant): void |

## Example

```php
use AdyenLib\Models\Builders\RecurringDetailBuilder;
use AdyenLib\Models\Builders\BankAccountBuilder;
use AdyenLib\Models\Builders\AddressBuilder;

$recurringDetail = RecurringDetailBuilder::init(
    'recurringDetailReference4',
    'variant8'
)
    ->additionalData(
        [
            'key0' => 'additionalData4',
            'key1' => 'additionalData5'
        ]
    )
    ->alias('alias6')
    ->aliasType('aliasType4')
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
    ->build();
```

