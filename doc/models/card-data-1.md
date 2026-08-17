
# Card Data 1

Information related to the payment card used for the transaction.
If PaymentInstrumentType is Card.

## Structure

`CardData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentBrand` | `?string` | Optional | Type of payment card.<br>If card PAN is readable.<br>Indicates the card used to pay in the PaymentResponse. Sent in the CardAcquisitionResponse, to leave the Cashier to choose between several applications in a smartcard, or several brand in a co-branded card. In this case, the CardAcquisitionRequest.ForceCustomerSelectionFlag must contain the value False. Brands are part of the POI and Sale Systems configurations.<br><br>**Constraints**: *Pattern*: `^.+$` | getPaymentBrand(): ?string | setPaymentBrand(?string paymentBrand): void |
| `maskedPan` | `?string` | Optional | Masked Primary Account Number<br>Part of the PAN is replaced by a string of * characters, to identify a customer account or relationship. Presence of this data element, which replace the PAN when SensitiveCardData is protected and replaced by ProtectedCardData. Alternatively the MaskedPAN can be used as a token to identify a customer.<br><br>**Constraints**: *Pattern*: `^.+$` | getMaskedPan(): ?string | setMaskedPan(?string maskedPan): void |
| `paymentAccountRef` | `?string` | Optional | Reference of the PAN, which identifies the PAN or the card uniquely, named also PAR (Payment Account Reference). This reference may be defined by the card issuer or by a token service provider under the control of the card issuer, and cannot be used for a payment transaction.<br><br>**Constraints**: *Pattern*: `^.+$` | getPaymentAccountRef(): ?string | setPaymentAccountRef(?string paymentAccountRef): void |
| `entryMode` | [`?(string(EntryModeEnum)[])`](../../doc/models/entry-mode-enum.md) | Optional | Entry mode of the payment instrument information. In the Payment, Loyalty or StoredValue Request messages, it informs the POI System the entry mode of the payment instrument information when read by the Sale Terminal. In the Payment, Loyalty or StoredValue Response messages, it informs the Sale System the entry mode of the payment instrument.<br>Possible values:<br><br>* **Contactless**<br>* **File**<br>* **ICC**<br>* **Keyed**<br>* **MagStripe**<br>* **Manual**<br>* **Mobile**<br>* **RFID**<br>* **Scanned**<br>* **SynchronousICC**<br>* **Tapped** | getEntryMode(): ?array | setEntryMode(?array entryMode): void |
| `cardCountryCode` | `?int` | Optional | Country Code attached to the card (3 numerics).<br>If available in the card.<br><br>**Constraints**: `>= 3`, `<= 3` | getCardCountryCode(): ?int | setCardCountryCode(?int cardCountryCode): void |
| `protectedCardData` | `?string` | Optional | Sensitive information related to the payment card, protected by CMS.<br>SensitiveCardData protected by CMS EnvelopedData. | getProtectedCardData(): ?string | setProtectedCardData(?string protectedCardData): void |
| `sensitiveCardData` | [`?SensitiveCardData1`](../../doc/models/sensitive-card-data-1.md) | Optional | Sensitive information related to the payment card, entered or read by the Sale System.<br>If structure non empty and unprotected. | getSensitiveCardData(): ?SensitiveCardData1 | setSensitiveCardData(?SensitiveCardData1 sensitiveCardData): void |
| `paymentToken` | [`?PaymentToken1`](../../doc/models/payment-token-1.md) | Optional | Surrogate of the PAN (Primary Account Number) of the payment card to identify the payment mean of the customer. It allows, for a merchant, to identify the customer.<br>Restriction of product payable by a card. | getPaymentToken(): ?PaymentToken1 | setPaymentToken(?PaymentToken1 paymentToken): void |

## Example

```php
use AdyenLib\Models\Builders\CardData1Builder;
use AdyenLib\Models\EntryModeEnum;

$cardData1 = CardData1Builder::init()
    ->paymentBrand('PaymentBrand6')
    ->maskedPan('MaskedPan4')
    ->paymentAccountRef('PaymentAccountRef4')
    ->entryMode(
        [
            EntryModeEnum::SYNCHRONOUSICC
        ]
    )
    ->cardCountryCode(3)
    ->build();
```

