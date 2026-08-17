
# Ultimate Parent Company Business Details 2

Details about the ultimate parent company's business.

## Structure

`UltimateParentCompanyBusinessDetails2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `legalBusinessName` | `?string` | Optional | The legal name of the company. | getLegalBusinessName(): ?string | setLegalBusinessName(?string legalBusinessName): void |
| `registrationNumber` | `?string` | Optional | The registration number of the company. | getRegistrationNumber(): ?string | setRegistrationNumber(?string registrationNumber): void |
| `stockExchange` | `?string` | Optional | Market Identifier Code (MIC). | getStockExchange(): ?string | setStockExchange(?string stockExchange): void |
| `stockNumber` | `?string` | Optional | International Securities Identification Number (ISIN). | getStockNumber(): ?string | setStockNumber(?string stockNumber): void |
| `stockTicker` | `?string` | Optional | Stock Ticker symbol. | getStockTicker(): ?string | setStockTicker(?string stockTicker): void |

## Example

```php
use AdyenLib\Models\Builders\UltimateParentCompanyBusinessDetails2Builder;

$ultimateParentCompanyBusinessDetails2 = UltimateParentCompanyBusinessDetails2Builder::init()
    ->legalBusinessName('legalBusinessName0')
    ->registrationNumber('registrationNumber2')
    ->stockExchange('stockExchange6')
    ->stockNumber('stockNumber8')
    ->stockTicker('stockTicker8')
    ->build();
```

