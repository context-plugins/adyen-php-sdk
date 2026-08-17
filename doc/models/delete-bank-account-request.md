
# Delete Bank Account Request

## Structure

`DeleteBankAccountRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the Account Holder from which to delete the Bank Account(s). | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `bankAccountUUIDs` | `string[]` | Required | The code(s) of the Bank Accounts to be deleted. | getBankAccountUUIDs(): array | setBankAccountUUIDs(array bankAccountUUIDs): void |

## Example

```php
use AdyenLib\Models\Builders\DeleteBankAccountRequestBuilder;

$deleteBankAccountRequest = DeleteBankAccountRequestBuilder::init(
    'accountHolderCode2',
    [
        'bankAccountUUIDs1',
        'bankAccountUUIDs2'
    ]
)->build();
```

