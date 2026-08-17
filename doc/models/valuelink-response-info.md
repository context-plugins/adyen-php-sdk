
# Valuelink Response Info

## Structure

`ValuelinkResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorisationMid` | `?string` | Optional | Authorisation Mid | getAuthorisationMid(): ?string | setAuthorisationMid(?string authorisationMid): void |
| `pinSupport` | [`?string(PinSupportEnum)`](../../doc/models/pin-support-enum.md) | Optional | PIN Support. For ecommerce, PIN is required. | getPinSupport(): ?string | setPinSupport(?string pinSupport): void |
| `submitterId` | `?string` | Optional | Submitter ID | getSubmitterId(): ?string | setSubmitterId(?string submitterId): void |
| `terminalId` | `?string` | Optional | Terminal ID | getTerminalId(): ?string | setTerminalId(?string terminalId): void |

## Example

```php
use AdyenLib\Models\Builders\ValuelinkResponseInfoBuilder;
use AdyenLib\Models\PinSupportEnum;

$valuelinkResponseInfo = ValuelinkResponseInfoBuilder::init()
    ->authorisationMid('authorisationMid6')
    ->pinSupport(PinSupportEnum::PIN)
    ->submitterId('submitterId2')
    ->terminalId('terminalId8')
    ->build();
```

