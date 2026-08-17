
# Balance Account

## Structure

`BalanceAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The unique identifier of the [account holder](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/accountHolders#responses-200-id) associated with the balance account. | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |
| `balances` | [`?(Balance[])`](../../doc/models/balance.md) | Optional | List of balances with the amount and currency. | getBalances(): ?array | setBalances(?array balances): void |
| `defaultCurrencyCode` | `?string` | Optional | The default three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes) of the balance account. This is the currency displayed on the Balance Account overview page in your Customer Area.<br>The default value is **EUR**.<br><br>> After a balance account is created, you cannot change its default currency. | getDefaultCurrencyCode(): ?string | setDefaultCurrencyCode(?string defaultCurrencyCode): void |
| `description` | `?string` | Optional | A human-readable description of the balance account, maximum 300 characters. You can use this parameter to distinguish between multiple balance accounts under an account holder.<br><br>**Constraints**: *Maximum Length*: `300` | getDescription(): ?string | setDescription(?string description): void |
| `id` | `string` | Required | The unique identifier of the balance account. | getId(): string | setId(string id): void |
| `metadata` | `?array<string,string>` | Optional | A set of key and value pairs for general use.<br>The keys do not have specific names and may be used for storing miscellaneous data as desired.<br><br>> Note that during an update of metadata, the omission of existing key-value pairs will result in the deletion of those key-value pairs. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `migratedAccountCode` | `?string` | Optional, Read-only | The unique identifier of the account of the migrated account holder in the classic integration. | getMigratedAccountCode(): ?string | setMigratedAccountCode(?string migratedAccountCode): void |
| `platformPaymentConfiguration` | [`?PlatformPaymentConfiguration1`](../../doc/models/platform-payment-configuration-1.md) | Optional | Contains key-value pairs to configure the sales day closing time and settlement delay for a balance account. | getPlatformPaymentConfiguration(): ?PlatformPaymentConfiguration1 | setPlatformPaymentConfiguration(?PlatformPaymentConfiguration1 platformPaymentConfiguration): void |
| `reference` | `?string` | Optional | Your reference for the balance account, maximum 150 characters.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): ?string | setReference(?string reference): void |
| `status` | [`?string(Status23Enum)`](../../doc/models/status-23-enum.md) | Optional | The status of the balance account, set to **active** by default. | getStatus(): ?string | setStatus(?string status): void |
| `timeZone` | `?string` | Optional | The time zone of the balance account. For example, **Europe/Amsterdam**.<br>Defaults to the time zone of the account holder if no time zone is set. For possible values, see the [list of time zone codes](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). | getTimeZone(): ?string | setTimeZone(?string timeZone): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceAccountBuilder;
use AdyenLib\Models\Builders\BalanceBuilder;

$balanceAccount = BalanceAccountBuilder::init(
    'accountHolderId4',
    'id2'
)
    ->balances(
        [
            BalanceBuilder::init(
                152,
                224,
                'currency0',
                158
            )
                ->pending(152)
                ->pendingAvailable(88)
                ->build(),
            BalanceBuilder::init(
                152,
                224,
                'currency0',
                158
            )
                ->pending(152)
                ->pendingAvailable(88)
                ->build(),
            BalanceBuilder::init(
                152,
                224,
                'currency0',
                158
            )
                ->pending(152)
                ->pendingAvailable(88)
                ->build()
        ]
    )
    ->defaultCurrencyCode('defaultCurrencyCode8')
    ->description('description2')
    ->metadata(
        [
            'key0' => 'metadata9',
            'key1' => 'metadata8'
        ]
    )
    ->build();
```

