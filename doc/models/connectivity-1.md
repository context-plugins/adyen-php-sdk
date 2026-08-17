
# Connectivity 1

Settings for terminal connectivity features.

## Structure

`Connectivity1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `simcardStatus` | [`?string(SimcardStatusEnum)`](../../doc/models/simcard-status-enum.md) | Optional | Indicates the status of the SIM card in the payment terminal. Can be updated and received only at terminal level, and only for models that support cellular connectivity.<br><br>Possible values:<br><br>* **ACTIVATED**: the SIM card is activated. Cellular connectivity may still need to be enabled on the terminal itself, in the **Network** settings.<br>* **INVENTORY**: the SIM card is not activated. The terminal can't use cellular connectivity. | getSimcardStatus(): ?string | setSimcardStatus(?string simcardStatus): void |
| `terminalIPAddressURL` | [`?EventUrl3`](../../doc/models/event-url-3.md) | Optional | The list of local and public URLs to send notifications to when using local integrations. | getTerminalIPAddressURL(): ?EventUrl3 | setTerminalIPAddressURL(?EventUrl3 terminalIPAddressURL): void |

## Example

```php
use AdyenLib\Models\Builders\Connectivity1Builder;
use AdyenLib\Models\SimcardStatusEnum;
use AdyenLib\Models\Builders\EventUrl3Builder;
use AdyenLib\Models\Builders\UrlBuilder;

$connectivity1 = Connectivity1Builder::init()
    ->simcardStatus(SimcardStatusEnum::ACTIVATED)
    ->terminalIPAddressURL(
        EventUrl3Builder::init()
            ->eventLocalUrls(
                [
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password4')
                        ->url('url4')
                        ->username('username0')
                        ->build()
                ]
            )
            ->eventPublicUrls(
                [
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password8')
                        ->url('url8')
                        ->username('username4')
                        ->build(),
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password8')
                        ->url('url8')
                        ->username('username4')
                        ->build()
                ]
            )
            ->build()
    )
    ->build();
```

