
# Get Pci Url Request

## Structure

`GetPciUrlRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The account holder code you provided when you created the account holder. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `returnUrl` | `?string` | Optional | The URL where the account holder will be redirected back to after they fill out the questionnaire, or if their session times out. Maximum length of 500 characters. | getReturnUrl(): ?string | setReturnUrl(?string returnUrl): void |

## Example

```php
use AdyenLib\Models\Builders\GetPciUrlRequestBuilder;

$getPciUrlRequest = GetPciUrlRequestBuilder::init(
    'accountHolderCode6'
)
    ->returnUrl('returnUrl8')
    ->build();
```

