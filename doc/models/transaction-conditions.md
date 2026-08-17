
# Transaction Conditions

Conditions on which the transaction must be processed.

## Structure

`TransactionConditions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowedPaymentBrand` | `?(string[])` | Optional | Payment brands accepted for this transaction.<br>Card payment brands allowed by the Sale System for the payment transaction.<br>Restrict brand if data sent.<br><br>**Constraints**: *Pattern*: `^.+$` | getAllowedPaymentBrand(): ?array | setAllowedPaymentBrand(?array allowedPaymentBrand): void |
| `acquirerID` | `?(int[])` | Optional | Identification of the Acquirer.<br>Restrict to these Acquirer if present. | getAcquirerID(): ?array | setAcquirerID(?array acquirerID): void |
| `debitPreferredFlag` | `?bool` | Optional | The preferred type of payment is a debit transaction rather than a credit transaction. | getDebitPreferredFlag(): ?bool | setDebitPreferredFlag(?bool debitPreferredFlag): void |
| `allowedLoyaltyBrand` | `?(string[])` | Optional | Loyalty brands or programs allowed by the Sale System for the loyalty transaction.<br>Restrict brand if data sent.<br><br>**Constraints**: *Pattern*: `^.+$` | getAllowedLoyaltyBrand(): ?array | setAllowedLoyaltyBrand(?array allowedLoyaltyBrand): void |
| `loyaltyHandling` | [`?string(LoyaltyHandling1Enum)`](../../doc/models/loyalty-handling-1-enum.md) | Optional | Type of Loyalty processing requested by the Sale System.<br>Possible values:<br><br>* **Allowed**<br>* **Forbidden**<br>* **Processed**<br>* **Proposed**<br>* **Required** | getLoyaltyHandling(): ?string | setLoyaltyHandling(?string loyaltyHandling): void |
| `customerLanguage` | `?string` | Optional | The language used on the terminal screen or in text printed by the terminal.<br>Typical use case is setting the language on unattended terminals. Format: two-character [ISO 639:2023](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes) format.<br><br>**Constraints**: *Pattern*: `^[a-z]{2,2}$` | getCustomerLanguage(): ?string | setCustomerLanguage(?string customerLanguage): void |
| `forceOnlineFlag` | `?bool` | Optional | Indicates if the Cashier requires POI forces online access to the Acquirer.<br>Go online if data sent.<br><br>**Default**: `false` | getForceOnlineFlag(): ?bool | setForceOnlineFlag(?bool forceOnlineFlag): void |
| `forceEntryMode` | [`?(string(ForceEntryModeEnum)[])`](../../doc/models/force-entry-mode-enum.md) | Optional | Payment instrument entry mode requested by the Sale System.<br>Restrict entry mode if sent.<br>Possible values:<br><br>* **CheckReader**<br>* **Contactless**<br>* **File**<br>* **ICC**<br>* **Keyed**<br>* **MagStripe**<br>* **Manual**<br>* **RFID**<br>* **Scanned**<br>* **SynchronousICC**<br>* **Tapped** | getForceEntryMode(): ?array | setForceEntryMode(?array forceEntryMode): void |
| `merchantCategoryCode` | `?string` | Optional | The code which identifies the category of the transaction (MCC).<br>The payment implies a specific MCC.<br><br>**Constraints**: *Pattern*: `^.{3,4}$` | getMerchantCategoryCode(): ?string | setMerchantCategoryCode(?string merchantCategoryCode): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionConditionsBuilder;
use AdyenLib\Models\LoyaltyHandling1Enum;

$transactionConditions = TransactionConditionsBuilder::init()
    ->allowedPaymentBrand(
        [
            'AllowedPaymentBrand4'
        ]
    )
    ->acquirerID(
        [
            34
        ]
    )
    ->debitPreferredFlag(false)
    ->allowedLoyaltyBrand(
        [
            'AllowedLoyaltyBrand2',
            'AllowedLoyaltyBrand3',
            'AllowedLoyaltyBrand4'
        ]
    )
    ->loyaltyHandling(LoyaltyHandling1Enum::REQUIRED)
    ->forceOnlineFlag(false)
    ->build();
```

