
# Stock Data 2

Information about the organization's publicly traded stock. Provide this object only if `type` is **listedPublicCompany**.

## Structure

`StockData2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `marketIdentifier` | `?string` | Optional | The four-digit [Market Identifier Code](https://en.wikipedia.org/wiki/Market_Identifier_Code) of the stock market where the organization's stocks are traded. | getMarketIdentifier(): ?string | setMarketIdentifier(?string marketIdentifier): void |
| `stockNumber` | `?string` | Optional | The 12-digit International Securities Identification Number (ISIN) of the company, without dashes (-). | getStockNumber(): ?string | setStockNumber(?string stockNumber): void |
| `tickerSymbol` | `?string` | Optional | The stock ticker symbol. | getTickerSymbol(): ?string | setTickerSymbol(?string tickerSymbol): void |

## Example

```php
use AdyenLib\Models\Builders\StockData2Builder;

$stockData2 = StockData2Builder::init()
    ->marketIdentifier('marketIdentifier4')
    ->stockNumber('stockNumber0')
    ->tickerSymbol('tickerSymbol0')
    ->build();
```

