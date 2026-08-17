
# Create Session Request

## Structure

`CreateSessionRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The unique identifier of your merchant account. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `setupToken` | `string` | Required | The setup token provided by the POS Mobile SDK.<br><br>- When using the Android POS Mobile SDK, obtain the token through the `AuthenticationService.authenticate(setupToken)` callback of `AuthenticationService`.<br>- When using the iOS POS Mobile SDK, obtain the token through the `PaymentServiceDelegate.register(with:)` callback of `PaymentServiceDelegate`.<br><br>**Constraints**: *Maximum Length*: `50000` | getSetupToken(): string | setSetupToken(string setupToken): void |
| `store` | `?string` | Optional | The unique identifier of the store that you want to process transactions for. | getStore(): ?string | setStore(?string store): void |

## Example

```php
use AdyenLib\Models\Builders\CreateSessionRequestBuilder;

$createSessionRequest = CreateSessionRequestBuilder::init(
    'merchantAccount6',
    'setupToken0'
)
    ->store('store4')
    ->build();
```

