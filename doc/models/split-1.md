
# Split 1

## Structure

`Split1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | `?string` | Optional | The unique identifier of the account to which the split amount is booked. Required if `type` is **MarketPlace** or **BalanceAccount**.<br><br>* [Classic Platforms integration](https://docs.adyen.com/classic-platforms): The [`accountCode`](https://docs.adyen.com/api-explorer/Account/latest/post/updateAccount#request-accountCode) of the account to which the split amount is booked.<br>* [Balance Platform](https://docs.adyen.com/adyen-for-platforms-model): The [`balanceAccountId`](https://docs.adyen.com/api-explorer/balanceplatform/latest/get/balanceAccounts/_id_#path-id) of the account to which the split amount is booked. | getAccount(): ?string | setAccount(?string account): void |
| `amount` | [`?SplitAmount`](../../doc/models/split-amount.md) | Optional | The amount of the split item.<br><br>* Required for all split types in the [Classic Platforms integration](https://docs.adyen.com/classic-platforms).<br>* Required if `type` is **BalanceAccount**, **Commission**, **Default**, or **VAT** in your [Balance Platform](https://docs.adyen.com/adyen-for-platforms-model) integration. | getAmount(): ?SplitAmount | setAmount(?SplitAmount amount): void |
| `description` | `?string` | Optional | Your description for the split item. | getDescription(): ?string | setDescription(?string description): void |
| `reference` | `?string` | Optional | Your unique reference for the part of the payment booked to the specified `account`.<br><br>This is required if `type` is **MarketPlace** ([Classic Platforms integration](https://docs.adyen.com/classic-platforms)) or **BalanceAccount** ([Balance Platform](https://docs.adyen.com/adyen-for-platforms-model)).<br><br>For the other types, we also recommend providing a **unique** reference so you can reconcile the split and the associated payment in the transaction overview and in the reports. | getReference(): ?string | setReference(?string reference): void |
| `type` | [`string(Type60Enum)`](../../doc/models/type-60-enum.md) | Required | The part of the payment you want to book to the specified `account`.<br><br>Possible values for the [Balance Platform](https://docs.adyen.com/adyen-for-platforms-model):<br><br>* **BalanceAccount**: books part of the payment (specified in `amount`) to the specified `account`.<br>* Transaction fees types that you can book to the specified `account`:<br>  * **AcquiringFees**: the aggregated amount of the interchange and scheme fees.<br>  * **PaymentFee**: the aggregated amount of all transaction fees.<br>  * **AdyenFees**: the aggregated amount of Adyen's commission and markup fees.<br>  * **AdyenCommission**: the transaction fees due to Adyen under [blended rates](https://www.adyen.com/knowledge-hub/interchange-fees-explained).<br>  * **AdyenMarkup**: the transaction fees due to Adyen under [Interchange ++ pricing](https://www.adyen.com/knowledge-hub/interchange-fees-explained).<br>  * **Interchange**: the fees paid to the issuer for each payment made with the card network.<br>  * **SchemeFee**: the fees paid to the card scheme for using their network.<br>* **Commission**: your platform's commission on the payment (specified in `amount`), booked to your liable balance account.<br>* **Remainder**: the amount left over after a currency conversion, booked to the specified `account`.<br>* **TopUp**: allows you and your users to top up balance accounts using direct debit, card payments, or other payment methods.<br>* **VAT**: the value-added tax charged on the payment, booked to your platforms liable balance account.<br>* **Commission**: your platform's commission (specified in `amount`) on the payment, booked to your liable balance account.<br>* **Default**: in very specific use cases, allows you to book the specified `amount` to the specified `account`. For more information, contact Adyen support.<br><br>Possible values for the [Classic Platforms integration](https://docs.adyen.com/classic-platforms): **Commission**, **Default**, **Marketplace**, **PaymentFee**, **VAT**. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\Split1Builder;
use AdyenLib\Models\Type60Enum;
use AdyenLib\Models\Builders\SplitAmountBuilder;

$split1 = Split1Builder::init(
    Type60Enum::PAYMENTFEE
)
    ->account('account4')
    ->amount(
        SplitAmountBuilder::init(
            110
        )
            ->currency('currency2')
            ->build()
    )
    ->description('description4')
    ->reference('reference0')
    ->build();
```

