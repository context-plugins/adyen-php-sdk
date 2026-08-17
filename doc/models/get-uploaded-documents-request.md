
# Get Uploaded Documents Request

## Structure

`GetUploadedDocumentsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the Account Holder for which to retrieve the documents. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `bankAccountUUID` | `?string` | Optional | The code of the Bank Account for which to retrieve the documents. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `shareholderCode` | `?string` | Optional | The code of the Shareholder for which to retrieve the documents. | getShareholderCode(): ?string | setShareholderCode(?string shareholderCode): void |

## Example

```php
use AdyenLib\Models\Builders\GetUploadedDocumentsRequestBuilder;

$getUploadedDocumentsRequest = GetUploadedDocumentsRequestBuilder::init(
    'accountHolderCode0'
)
    ->bankAccountUUID('bankAccountUUID0')
    ->shareholderCode('shareholderCode2')
    ->build();
```

