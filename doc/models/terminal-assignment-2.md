
# Terminal Assignment 2

Indicates the account level to which the terminal is assigned, the [assignment status](https://docs.adyen.com/point-of-sale/automating-terminal-management/assign-terminals-api), and where the terminals is in the process of being reassigned to.

## Structure

`TerminalAssignment2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `companyId` | `string` | Required | The unique identifier of the company account to which terminal is assigned. | getCompanyId(): string | setCompanyId(string companyId): void |
| `merchantId` | `?string` | Optional | The unique identifier of the merchant account to which terminal is assigned. | getMerchantId(): ?string | setMerchantId(?string merchantId): void |
| `reassignmentTarget` | [`?TerminalReassignmentTarget2`](../../doc/models/terminal-reassignment-target-2.md) | Optional | Indicates where the terminal is in the process of being reassigned to. | getReassignmentTarget(): ?TerminalReassignmentTarget2 | setReassignmentTarget(?TerminalReassignmentTarget2 reassignmentTarget): void |
| `status` | [`string(Status21Enum)`](../../doc/models/status-21-enum.md) | Required | The status of the reassignment. Possible values:<br><br>* `reassignmentInProgress`: the terminal was boarded and is now scheduled to remove the configuration. Wait for the terminal to synchronize with the Adyen platform.<br>* `deployed`: the terminal is deployed and reassigned.<br>* `inventory`: the terminal is in inventory and cannot process transactions.<br>* `boarded`: the terminal is boarded to a store, or a merchant account representing a store, and can process transactions. | getStatus(): string | setStatus(string status): void |
| `storeId` | `?string` | Optional | The unique identifier of the store to which terminal is assigned. | getStoreId(): ?string | setStoreId(?string storeId): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalAssignment2Builder;
use AdyenLib\Models\Status21Enum;
use AdyenLib\Models\Builders\TerminalReassignmentTarget2Builder;

$terminalAssignment2 = TerminalAssignment2Builder::init(
    'companyId0',
    Status21Enum::BOARDED
)
    ->merchantId('merchantId6')
    ->reassignmentTarget(
        TerminalReassignmentTarget2Builder::init(
            false
        )
            ->companyId('companyId4')
            ->merchantId('merchantId0')
            ->storeId('storeId8')
            ->build()
    )
    ->storeId('storeId4')
    ->build();
```

