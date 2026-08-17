
# Source of Funds 1

## Structure

`SourceOfFunds1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adyenProcessedFunds` | `bool` | Required | Indicates whether the funds are coming from transactions processed by Adyen. If **false**, the `type` is required. | getAdyenProcessedFunds(): bool | setAdyenProcessedFunds(bool adyenProcessedFunds): void |
| `amount` | [`?PatchableAmountDTO`](../../doc/models/patchable-amount-dto.md) | Optional | Required if `type` is **business**, **assetSale**, **gamblingWinnings** or **inheritance**.<br><br>For `type` **business**, provide the annual turn over of the business. For `type` **assetSale**, **gamblingWinnings** or **inheritance**, provide the amount of the funds. | getAmount(): ?PatchableAmountDTO | setAmount(?PatchableAmountDTO amount): void |
| `assetMonthsHeld` | `?int` | Optional | The number of months that the asset has been in possession of the user.<br><br>For example, if the source of funds is of type **cryptocurrencyIncome** then `assetMonthsHeld` is the number of months the user has owned the cryptocurrency. | getAssetMonthsHeld(): ?int | setAssetMonthsHeld(?int assetMonthsHeld): void |
| `cryptocurrencyExchange` | `?string` | Optional | Required if `type` is **cryptocurrencyIncome**. The cryptocurrency exchange where the funds were acquired. | getCryptocurrencyExchange(): ?string | setCryptocurrencyExchange(?string cryptocurrencyExchange): void |
| `dateOfFundsReceived` | `?DateTime` | Optional | Required if `type` is **donations** or **inheritance**. The date the funds were received, in YYYY-MM-DD format. | getDateOfFundsReceived(): ?\DateTime | setDateOfFundsReceived(?\DateTime dateOfFundsReceived): void |
| `dateOfSourceEvent` | `?DateTime` | Optional | Required if `type` is **assetSale** or **gamblingWinnings**. The date the funds were received, in YYYY-MM-DD format.<br><br>For example, if the source of funds is of type **assetSale**, the dateOfSourceEvent is the date of the sale. If the source of funds is of type **gamblingWinnings**, the dateOfSourceEvent is the date of winnings. | getDateOfSourceEvent(): ?\DateTime | setDateOfSourceEvent(?\DateTime dateOfSourceEvent): void |
| `description` | `?string` | Optional | Required if `type` is **business** or **assetSale**. A description for the source of funds.<br><br>For example, for `type` **business**, provide a description of where the business transactions come from, such as payments through bank transfer. For `type` **assetSale**, provide a description of the asset. For example, the address of a residential property if it is a property sale. | getDescription(): ?string | setDescription(?string description): void |
| `financiers` | [`?(Financier[])`](../../doc/models/financier.md) | Optional | Required if `type` is **thirdPartyFunding**. Information about the financiers. | getFinanciers(): ?array | setFinanciers(?array financiers): void |
| `originatorLegalEntityId` | `?string` | Optional | Required if `type` is **donations** or **inheritance**. The legal entity ID representing the originator of the source of funds.<br><br>For example, if the source of funds is **inheritance**, then `originatorOfFundsReference` should be the legal entity reference of the benefactor. | getOriginatorLegalEntityId(): ?string | setOriginatorLegalEntityId(?string originatorLegalEntityId): void |
| `purpose` | `?string` | Optional | Required if `type` is **donations**. The reason for receiving the funds. | getPurpose(): ?string | setPurpose(?string purpose): void |
| `relationship` | `?string` | Optional | Required if `type` is **donations** or **inheritance**. The relationship of the originator of the funds to the recipient. | getRelationship(): ?string | setRelationship(?string relationship): void |
| `type` | [`?string(Type74Enum)`](../../doc/models/type-74-enum.md) | Optional | The type of the source of funds.<br><br>Possible values:<br><br>* **business**<br>* **employment**<br>* **donations**<br>* **inheritance**<br>* **financialAid**<br>* **rentalIncome**<br>* **dividendIncome**<br>* **royaltyIncome**<br>* **thirdPartyFunding**<br>* **pensionIncome**<br>* **insuranceSettlement**<br>* **cryptocurrencyIncome**<br>* **assetSale**<br>* **loans**<br>* **gamblingWinnings** | getType(): ?string | setType(?string type): void |
| `website` | `?string` | Optional | Required if `type` is **gamblingWinnings**. The location of the gambling site for the winnings.<br><br>For example, if the source of funds is online gambling, provide the website of the gambling company. | getWebsite(): ?string | setWebsite(?string website): void |

## Example

```php
use AdyenLib\Models\Builders\SourceOfFunds1Builder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;
use AdyenLib\Utils\DateTimeHelper;

$sourceOfFunds1 = SourceOfFunds1Builder::init(
    false
)
    ->amount(
        PatchableAmountDTOBuilder::init()
            ->currency('currency2')
            ->value(110)
            ->build()
    )
    ->assetMonthsHeld(60)
    ->cryptocurrencyExchange('cryptocurrencyExchange4')
    ->dateOfFundsReceived(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->dateOfSourceEvent(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->build();
```

