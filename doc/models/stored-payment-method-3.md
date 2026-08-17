
# Stored Payment Method 3

## Structure

`StoredPaymentMethod3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccountNumber` | `?string` | Optional | The bank account number (without separators). | getBankAccountNumber(): ?string | setBankAccountNumber(?string bankAccountNumber): void |
| `bankLocationId` | `?string` | Optional | The location id of the bank. The field value is `nil` in most cases. | getBankLocationId(): ?string | setBankLocationId(?string bankLocationId): void |
| `brand` | `?string` | Optional | The brand of the card. | getBrand(): ?string | setBrand(?string brand): void |
| `cashtag` | `?string` | Optional | The shopper’s Cash App Pay Cashtag. | getCashtag(): ?string | setCashtag(?string cashtag): void |
| `expiryMonth` | `?string` | Optional | The two-digit month when the card expires | getExpiryMonth(): ?string | setExpiryMonth(?string expiryMonth): void |
| `expiryYear` | `?string` | Optional | The last two digits of the year the card expires. For example, **22** for the year 2022. | getExpiryYear(): ?string | setExpiryYear(?string expiryYear): void |
| `externalToken` | `?string` | Optional | The token issued by an external tokenization service representing the shopper's payment method | getExternalToken(): ?string | setExternalToken(?string externalToken): void |
| `holderName` | `?string` | Optional | The name of the payment method holder. | getHolderName(): ?string | setHolderName(?string holderName): void |
| `iban` | `?string` | Optional | The IBAN of the bank account. | getIban(): ?string | setIban(?string iban): void |
| `id` | `?string` | Optional | A unique identifier of this stored payment method. | getId(): ?string | setId(?string id): void |
| `label` | `?string` | Optional | The shopper’s issuer account label | getLabel(): ?string | setLabel(?string label): void |
| `lastFour` | `?string` | Optional | The last four digits of the PAN. | getLastFour(): ?string | setLastFour(?string lastFour): void |
| `name` | `?string` | Optional | The display name of the stored payment method. | getName(): ?string | setName(?string name): void |
| `networkTxReference` | `?string` | Optional | Returned in the response if you are not tokenizing with Adyen and are using the Merchant-initiated transactions (MIT) framework from Mastercard or Visa.<br><br>This contains either the Mastercard Trace ID or the Visa Transaction ID. | getNetworkTxReference(): ?string | setNetworkTxReference(?string networkTxReference): void |
| `ownerName` | `?string` | Optional | The name of the bank account holder. | getOwnerName(): ?string | setOwnerName(?string ownerName): void |
| `shopperEmail` | `?string` | Optional | The shopper’s email address. | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `supportedRecurringProcessingModels` | `?(string[])` | Optional | The supported recurring processing models for this stored payment method. | getSupportedRecurringProcessingModels(): ?array | setSupportedRecurringProcessingModels(?array supportedRecurringProcessingModels): void |
| `supportedShopperInteractions` | `?(string[])` | Optional | The supported shopper interactions for this stored payment method. | getSupportedShopperInteractions(): ?array | setSupportedShopperInteractions(?array supportedShopperInteractions): void |
| `type` | `?string` | Optional | The type of payment method. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\StoredPaymentMethod3Builder;

$storedPaymentMethod3 = StoredPaymentMethod3Builder::init()
    ->bankAccountNumber('bankAccountNumber8')
    ->bankLocationId('bankLocationId2')
    ->brand('brand2')
    ->cashtag('cashtag6')
    ->expiryMonth('expiryMonth2')
    ->build();
```

