
# Card Bin

## Structure

`CardBin`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bin` | `?string` | Optional | The first 6 digit of the card number. Enable this field via merchant account settings. | getBin(): ?string | setBin(?string bin): void |
| `commercial` | `?bool` | Optional | If true, it indicates a commercial card. Enable this field via merchant account settings. | getCommercial(): ?bool | setCommercial(?bool commercial): void |
| `fundingSource` | `?string` | Optional | The card funding source. Valid values are:<br><br>* CHARGE<br>* CREDIT<br>* DEBIT<br>* DEFERRED_DEBIT<br>* PREPAID<br>* PREPAID_RELOADABLE<br>* PREPAID_NONRELOADABLE<br><br>> Enable this field via merchant account settings. | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `fundsAvailability` | `?string` | Optional | Indicates availability of funds.<br><br>Visa:<br><br>* "I" (fast funds are supported)<br>* "N" (otherwise)<br><br>Mastercard:<br><br>* "I" (product type is Prepaid or Debit, or issuing country is in CEE/HGEM list)<br>* "N" (otherwise)<br><br>> Returned when you verify a card BIN or estimate costs, and only if `payoutEligible` is different from "N" or "U". | getFundsAvailability(): ?string | setFundsAvailability(?string fundsAvailability): void |
| `issuerBin` | `?string` | Optional | The first 8 digit of the card number. Enable this field via merchant account settings. | getIssuerBin(): ?string | setIssuerBin(?string issuerBin): void |
| `issuingBank` | `?string` | Optional | The issuing bank of the card. | getIssuingBank(): ?string | setIssuingBank(?string issuingBank): void |
| `issuingCountry` | `?string` | Optional | The country where the card was issued from. | getIssuingCountry(): ?string | setIssuingCountry(?string issuingCountry): void |
| `issuingCurrency` | `?string` | Optional | The currency of the card. | getIssuingCurrency(): ?string | setIssuingCurrency(?string issuingCurrency): void |
| `paymentMethod` | `?string` | Optional | The payment method associated with the card (e.g. visa, mc, or amex). | getPaymentMethod(): ?string | setPaymentMethod(?string paymentMethod): void |
| `payoutEligible` | `?string` | Optional | Indicates whether a payout is eligible or not for this card.<br><br>Visa:<br><br>* "Y"<br>* "N"<br><br>Mastercard:<br><br>* "Y" (domestic and cross-border)<br>* "D" (only domestic)<br>* "N" (no MoneySend)<br>* "U" (unknown)<br><br>> Returned when you verify a card BIN or estimate costs, and only if `payoutEligible` is different from "N" or "U". | getPayoutEligible(): ?string | setPayoutEligible(?string payoutEligible): void |
| `summary` | `?string` | Optional | The last four digits of the card number. | getSummary(): ?string | setSummary(?string summary): void |

## Example

```php
use AdyenLib\Models\Builders\CardBinBuilder;

$cardBin = CardBinBuilder::init()
    ->bin('bin6')
    ->commercial(false)
    ->fundingSource('fundingSource0')
    ->fundsAvailability('fundsAvailability0')
    ->issuerBin('issuerBin8')
    ->build();
```

