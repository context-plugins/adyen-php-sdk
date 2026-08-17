
# Currency Conversion

Information related to a currency conversion.
A currency conversion occurred in the payment, and the merchant needs to know information related to this conversion (e.g. to print on the sale receipt).

## Structure

`CurrencyConversion`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerApprovedFlag` | `?bool` | Optional | Notify if the customer has approved something. Indicates if the customer has accepted a currency conversion.<br><br>**Default**: `true` | getCustomerApprovedFlag(): ?bool | setCustomerApprovedFlag(?bool customerApprovedFlag): void |
| `convertedAmount` | [`ConvertedAmount1`](../../doc/models/converted-amount-1.md) | Required | Amount after a currency conversion. | getConvertedAmount(): ConvertedAmount1 | setConvertedAmount(ConvertedAmount1 convertedAmount): void |
| `rate` | `?float` | Optional | Rate of currency conversion. | getRate(): ?float | setRate(?float rate): void |
| `markup` | `?float` | Optional | Markup of a currency conversion amount as a percentage. | getMarkup(): ?float | setMarkup(?float markup): void |
| `commission` | `?float` | Optional | Commission for a currency conversion.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getCommission(): ?float | setCommission(?float commission): void |
| `declaration` | `?string` | Optional | Declaration to present to the customer or the cashier for validation.<br>If a declaration has to be presented to the customer.<br><br>**Constraints**: *Pattern*: `^.+$` | getDeclaration(): ?string | setDeclaration(?string declaration): void |

## Example

```php
use AdyenLib\Models\Builders\CurrencyConversionBuilder;
use AdyenLib\Models\Builders\ConvertedAmount1Builder;

$currencyConversion = CurrencyConversionBuilder::init(
    ConvertedAmount1Builder::init(
        81.82,
        'Currency0'
    )->build()
)
    ->customerApprovedFlag(true)
    ->rate(37.94)
    ->markup(238.72)
    ->commission(59.92)
    ->declaration('Declaration0')
    ->build();
```

