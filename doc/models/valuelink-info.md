
# Valuelink Info

## Structure

`ValuelinkInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorisationMid` | `string` | Required | Authorisation Mid | getAuthorisationMid(): string | setAuthorisationMid(string authorisationMid): void |
| `pinSupport` | [`string(PinSupportEnum)`](../../doc/models/pin-support-enum.md) | Required | PIN Support. For ecommerce, PIN is required. | getPinSupport(): string | setPinSupport(string pinSupport): void |
| `submitterId` | `?string` | Optional | Submitter ID | getSubmitterId(): ?string | setSubmitterId(?string submitterId): void |
| `terminalId` | `?string` | Optional | Terminal ID | getTerminalId(): ?string | setTerminalId(?string terminalId): void |

## Example

```php
use AdyenLib\Models\Builders\ValuelinkInfoBuilder;
use AdyenLib\Models\PinSupportEnum;

$valuelinkInfo = ValuelinkInfoBuilder::init(
    'authorisationMid6',
    PinSupportEnum::PIN
)
    ->submitterId('submitterId2')
    ->terminalId('terminalId8')
    ->build();
```

