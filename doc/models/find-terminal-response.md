
# Find Terminal Response

## Structure

`FindTerminalResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `companyAccount` | `string` | Required | The company account that the terminal is associated with. If this is the only account level shown in the response, the terminal is assigned to the inventory of the company account. | getCompanyAccount(): string | setCompanyAccount(string companyAccount): void |
| `merchantAccount` | `?string` | Optional | The merchant account that the terminal is associated with. If the response doesn't contain a `store` the terminal is assigned to this merchant account. | getMerchantAccount(): ?string | setMerchantAccount(?string merchantAccount): void |
| `merchantInventory` | `?bool` | Optional | Boolean that indicates if the terminal is assigned to the merchant inventory. This is returned when the terminal is assigned to a merchant account.<br><br>- If **true**, this indicates that the terminal is in the merchant inventory. This also means that the terminal cannot be boarded.<br><br>- If **false**, this indicates that the terminal is assigned to the merchant account as an in-store terminal. This means that the terminal is ready to be boarded, or is already boarded. | getMerchantInventory(): ?bool | setMerchantInventory(?bool merchantInventory): void |
| `store` | `?string` | Optional | The store code of the store that the terminal is assigned to. | getStore(): ?string | setStore(?string store): void |
| `terminal` | `string` | Required | The unique terminal ID. | getTerminal(): string | setTerminal(string terminal): void |

## Example

```php
use AdyenLib\Models\Builders\FindTerminalResponseBuilder;

$findTerminalResponse = FindTerminalResponseBuilder::init(
    'companyAccount6',
    'terminal0'
)
    ->merchantAccount('merchantAccount6')
    ->merchantInventory(false)
    ->store('store8')
    ->build();
```

