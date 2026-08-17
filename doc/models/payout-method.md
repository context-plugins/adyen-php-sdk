
# Payout Method

## Structure

`PayoutMethod`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The [`merchantAccount`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments__reqParam_merchantAccount) you used in the `/payments` request when you [saved the account holder's card details](https://docs.adyen.com/classic-platforms/payouts/manual-payout/payout-to-cards#check-and-store). | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `payoutMethodCode` | `?string` | Optional | Adyen-generated unique alphanumeric identifier (UUID) for the payout method, returned in the response when you create a payout method. Required when updating an existing payout method in an `/updateAccountHolder` request. | getPayoutMethodCode(): ?string | setPayoutMethodCode(?string payoutMethodCode): void |
| `payoutMethodReference` | `?string` | Optional | Your reference for the payout method. | getPayoutMethodReference(): ?string | setPayoutMethodReference(?string payoutMethodReference): void |
| `recurringDetailReference` | `string` | Required | The [`recurringDetailReference`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments__resParam_additionalData-ResponseAdditionalDataCommon-recurring-recurringDetailReference)  returned in the `/payments` response when you [saved the account holder's card details](https://docs.adyen.com/classic-platforms/payouts/manual-payout/payout-to-cards#check-and-store). | getRecurringDetailReference(): string | setRecurringDetailReference(string recurringDetailReference): void |
| `shopperReference` | `string` | Required | The [`shopperReference`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments__reqParam_shopperReference) you sent in the `/payments` request when you [saved the account holder's card details](https://docs.adyen.com/classic-platforms/payouts/manual-payout/payout-to-cards#check-and-store). | getShopperReference(): string | setShopperReference(string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutMethodBuilder;

$payoutMethod = PayoutMethodBuilder::init(
    'merchantAccount4',
    'recurringDetailReference2',
    'shopperReference0'
)
    ->payoutMethodCode('payoutMethodCode2')
    ->payoutMethodReference('payoutMethodReference2')
    ->build();
```

