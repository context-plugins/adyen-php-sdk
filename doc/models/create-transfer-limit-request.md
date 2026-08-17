
# Create Transfer Limit Request

## Structure

`CreateTransferLimitRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The amount for the transfer limit. This is the maximum amount allowed per transfer or per day based on the `scope` of the limit. | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `endsAt` | `?DateTime` | Optional | The date and time when the transfer limit becomes inactive. If you do not specify an end date, the limit stays active until you override it with a new limit.<br><br>Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): **YYYY-MM-DDThh:mm:ss.sssTZD** | getEndsAt(): ?\DateTime | setEndsAt(?\DateTime endsAt): void |
| `reference` | `?string` | Optional | Your reference for the transfer limit. | getReference(): ?string | setReference(?string reference): void |
| `scaInformation` | [`?CreateScaInformation1`](../../doc/models/create-sca-information-1.md) | Optional | Information for the Strong Customer Authentication (SCA) | getScaInformation(): ?CreateScaInformation1 | setScaInformation(?CreateScaInformation1 scaInformation): void |
| `scope` | [`string(ScopeEnum)`](../../doc/models/scope-enum.md) | Required | The scope to which the transfer limit applies. Possible values:<br><br>* **perTransaction**: you set a maximum amount for each transfer made from the balance account or balance platform.<br>* **perDay**: you set a maximum total amount for all transfers made from the balance account or balance platform in a day. | getScope(): string | setScope(string scope): void |
| `startsAt` | `?DateTime` | Optional | The date and time when the transfer limit becomes active. If you specify a date in the future, we will schedule a transfer limit.<br><br>Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): **YYYY-MM-DDThh:mm:ss.sssTZD** | getStartsAt(): ?\DateTime | setStartsAt(?\DateTime startsAt): void |
| `transferType` | [`string(TransferTypeEnum)`](../../doc/models/transfer-type-enum.md) | Required | The type of transfer to which the limit applies. Possible values:<br><br>* **instant**: the limit applies to transfers with an **instant** priority.<br>* **all**: the limit applies to all transfers, regardless of priority. | getTransferType(): string | setTransferType(string transferType): void |

## Example

```php
use AdyenLib\Models\Builders\CreateTransferLimitRequestBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\ScopeEnum;
use AdyenLib\Models\TransferTypeEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\CreateScaInformation1Builder;
use AdyenLib\Models\ScaExemptionEnum;

$createTransferLimitRequest = CreateTransferLimitRequestBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build(),
    ScopeEnum::PERDAY,
    TransferTypeEnum::INSTANT
)
    ->endsAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->reference('reference2')
    ->scaInformation(
        CreateScaInformation1Builder::init()
            ->exemption(ScaExemptionEnum::NOTREGULATED)
            ->scaOnApproval(false)
            ->build()
    )
    ->startsAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

