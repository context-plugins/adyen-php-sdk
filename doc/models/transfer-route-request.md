
# Transfer Route Request

## Structure

`TransferRouteRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccountId` | `?string` | Optional | The unique identifier of the source [balance account](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/post/balanceAccounts__resParam_id).<br>Required if `counterparty` is **transferInstrumentId**. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `balancePlatform` | `string` | Required | The unique identifier assigned to the balance platform associated with the account holder. | getBalancePlatform(): string | setBalancePlatform(string balancePlatform): void |
| `category` | `string` | Required, Constant | The type of transfer. Possible values:<br><br>- **bank**: Transfer to a [transfer instrument](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/transferInstruments__resParam_id) or a bank account.<br><br>**Value**: `'bank'` | getCategory(): string | setCategory(string category): void |
| `counterparty` | [`?Counterparty1`](../../doc/models/counterparty-1.md) | Optional | The recipient of the funds transfer. A bank account or a transfer instrument. | getCounterparty(): ?Counterparty1 | setCounterparty(?Counterparty1 counterparty): void |
| `country` | `?string` | Optional | The two-character ISO-3166-1 alpha-2 country code of the counterparty. For example, **US** or **NL**.<br><br>> Either `counterparty` or `country` field must be provided in a transfer route request. | getCountry(): ?string | setCountry(?string country): void |
| `currency` | `string` | Required | The three-character ISO currency code of transfer. For example, **USD** or **EUR**. | getCurrency(): string | setCurrency(string currency): void |
| `priorities` | [`?(string(Priority1Enum)[])`](../../doc/models/priority-1-enum.md) | Optional | The list of priorities for the bank transfer. Priorities set the speed at which the transfer is sent and the fees that you have to pay. Multiple values can be provided.<br>Possible values:<br><br>* **regular**: For normal, low-value transactions.<br><br>* **fast**: A faster way to transfer funds, but the fees are higher. Recommended for high-priority, low-value transactions.<br><br>* **wire**: The fastest way to transfer funds, but this has the highest fees. Recommended for high-priority, high-value transactions.<br><br>* **instant**: For instant funds transfers within the United States and in [SEPA locations](https://www.ecb.europa.eu/paym/integration/retail/sepa/html/index.en.html).<br><br>* **crossBorder**: For high-value transfers to a recipient in a different country.<br><br>* **internal**: For transfers to an Adyen-issued business bank account (by bank account number/IBAN). | getPriorities(): ?array | setPriorities(?array priorities): void |

## Example

```php
use AdyenLib\Models\Builders\TransferRouteRequestBuilder;
use AdyenLib\Models\Builders\Counterparty1Builder;
use AdyenLib\Models\Builders\BankAccount11Builder;
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;
use AdyenLib\Models\Priority1Enum;

$transferRouteRequest = TransferRouteRequestBuilder::init(
    'balancePlatform8',
    'currency6'
)
    ->balanceAccountId('balanceAccountId2')
    ->counterparty(
        Counterparty1Builder::init()
            ->bankAccount(
                BankAccount11Builder::init(
                    AULocalAccountIdentificationBuilder::init(
                        'accountNumber4',
                        'bsbCode8'
                    )->build()
                )->build()
            )
            ->transferInstrumentId('transferInstrumentId4')
            ->build()
    )
    ->country('country0')
    ->priorities(
        [
            Priority1Enum::REGULAR,
            Priority1Enum::WIRE,
            Priority1Enum::CROSSBORDER
        ]
    )
    ->build();
```

