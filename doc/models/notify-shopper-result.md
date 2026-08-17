
# Notify Shopper Result

## Structure

`NotifyShopperResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `displayedReference` | `?string` | Optional | Reference of Pre-debit notification that is displayed to the shopper | getDisplayedReference(): ?string | setDisplayedReference(?string displayedReference): void |
| `message` | `?string` | Optional | A simple description of the `resultCode`. | getMessage(): ?string | setMessage(?string message): void |
| `pspReference` | `?string` | Optional | The unique reference that is associated with the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `reference` | `?string` | Optional | Reference of Pre-debit notification sent in my the merchant | getReference(): ?string | setReference(?string reference): void |
| `resultCode` | `?string` | Optional | The code indicating the status of notification. | getResultCode(): ?string | setResultCode(?string resultCode): void |
| `shopperNotificationReference` | `?string` | Optional | The unique reference for the request sent downstream. | getShopperNotificationReference(): ?string | setShopperNotificationReference(?string shopperNotificationReference): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the recurringDetailReference returned in the response when token was created | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |

## Example

```php
use AdyenLib\Models\Builders\NotifyShopperResultBuilder;

$notifyShopperResult = NotifyShopperResultBuilder::init()
    ->displayedReference('displayedReference8')
    ->message('message0')
    ->pspReference('pspReference2')
    ->reference('reference6')
    ->resultCode('resultCode4')
    ->build();
```

