
# Not Delivered Info

## Structure

`NotDeliveredInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `agreedDeliveryLocation` | `?string` | Optional | The delivery location specified by the cardholder. Required if **deliveredToWrongLocation** is **true**.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `500` | getAgreedDeliveryLocation(): ?string | setAgreedDeliveryLocation(?string agreedDeliveryLocation): void |
| `dateOfCancellation` | `?DateTime` | Optional | The date the undelivered goods or services were cancelled in YYYY-MM-DD format. | getDateOfCancellation(): ?\DateTime | setDateOfCancellation(?\DateTime dateOfCancellation): void |
| `deliveredToWrongLocation` | `?bool` | Optional | Indicates goods were delivered to the wrong location.<br><br>Possible values: **true**, **false**. | getDeliveredToWrongLocation(): ?bool | setDeliveredToWrongLocation(?bool deliveredToWrongLocation): void |
| `descriptionOfIssue` | `string` | Required | Your description of the issue for raising a dispute of `type` **notDelivered**.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `2500` | getDescriptionOfIssue(): string | setDescriptionOfIssue(string descriptionOfIssue): void |
| `didCardholderReturn` | `?bool` | Optional | Indicates if the cardholder returned the goods to the merchant. Required if **isDeliveryLate** is **true**.<br><br>Possible values: **true**, **false**. | getDidCardholderReturn(): ?bool | setDidCardholderReturn(?bool didCardholderReturn): void |
| `isDeliveryLate` | `?bool` | Optional | Indicates if the goods or services were delivered late. Required if **whatWasNotDelivered** is **goods**.<br><br>Possible values: **true**, **false**. | getIsDeliveryLate(): ?bool | setIsDeliveryLate(?bool isDeliveryLate): void |
| `isMerchantBankrupt` | `?bool` | Optional | Indicates if the transaction was processed by a bankrupt merchant.<br><br>Possible values: **true**, **false**. | getIsMerchantBankrupt(): ?bool | setIsMerchantBankrupt(?bool isMerchantBankrupt): void |
| `isNonFiatOrNft` | `?bool` | Optional | Indicates if the transaction is non-fiat or non-fungible token (NFT) related.<br><br>Possible values: **true**, **false**. | getIsNonFiatOrNft(): ?bool | setIsNonFiatOrNft(?bool isNonFiatOrNft): void |
| `lastExpectedDate` | `DateTime` | Required | The date the undelivered goods or services were expected to be delivered in YYYY-MM-DD format. | getLastExpectedDate(): \DateTime | setLastExpectedDate(\DateTime lastExpectedDate): void |
| `whatWasNotDelivered` | [`string(ProductType21Enum)`](../../doc/models/product-type-21-enum.md) | Required | The type of product that you expected to receive.<br><br>Possible values: **goods**, **services**. | getWhatWasNotDelivered(): string | setWhatWasNotDelivered(string whatWasNotDelivered): void |
| `whoCancelled` | [`?string(CancellingEntity1Enum)`](../../doc/models/cancelling-entity-1-enum.md) | Optional | The party that initiated the cancellation of the transaction.<br><br>Possible values: **merchant**, **cardholder**. | getWhoCancelled(): ?string | setWhoCancelled(?string whoCancelled): void |

## Example

```php
use AdyenLib\Models\Builders\NotDeliveredInfoBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\ProductType21Enum;

$notDeliveredInfo = NotDeliveredInfoBuilder::init(
    'descriptionOfIssue6',
    DateTimeHelper::fromSimpleDateRequired('2016-03-13'),
    ProductType21Enum::GOODS
)
    ->agreedDeliveryLocation('agreedDeliveryLocation4')
    ->dateOfCancellation(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->deliveredToWrongLocation(false)
    ->didCardholderReturn(false)
    ->isDeliveryLate(false)
    ->build();
```

