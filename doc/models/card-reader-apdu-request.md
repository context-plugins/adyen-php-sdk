
# Card Reader APDU Request

It contains the APDU request to send to the chip of the card, and a possible invitation message to display on the CashierInterface or the CustomerInterface.
Content of the Card Reader APDU Request message.

## Structure

`CardReaderAPDURequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `aPDUClass` | `string` | Required | Class field of the APDU command (CLA). APDU request for Card Reader device request. For specific card like synchronous card, a private value should be used in accordance to ISO 7816- 4 (private range D0-FE).<br><br>**Constraints**: *Pattern*: `^.{1,1}$` | getAPDUClass(): string | setAPDUClass(string aPDUClass): void |
| `aPDUInstruction` | `string` | Required | Instruction field of the APDU command (INS).<br><br>**Constraints**: *Pattern*: `^.{1,1}$` | getAPDUInstruction(): string | setAPDUInstruction(string aPDUInstruction): void |
| `aPDUPar1` | `string` | Required | Parameter 1 field of the APDU command (P1).<br><br>**Constraints**: *Pattern*: `^.{1,1}$` | getAPDUPar1(): string | setAPDUPar1(string aPDUPar1): void |
| `aPDUPar2` | `string` | Required | Parameter 2 field of the APDU command(P2).<br><br>**Constraints**: *Pattern*: `^.{1,1}$` | getAPDUPar2(): string | setAPDUPar2(string aPDUPar2): void |
| `aPDUData` | `?string` | Optional | Data field of the APDU command (Lc + Data).<br><br>**Constraints**: *Pattern*: `^.+$` | getAPDUData(): ?string | setAPDUData(?string aPDUData): void |
| `aPDUExpectedLength` | `?string` | Optional | Expected length of the data field of the APDU response to the command (Le).<br><br>**Constraints**: *Pattern*: `^.{1,1}$` | getAPDUExpectedLength(): ?string | setAPDUExpectedLength(?string aPDUExpectedLength): void |

## Example

```php
use AdyenLib\Models\Builders\CardReaderAPDURequestBuilder;

$cardReaderAPDURequest = CardReaderAPDURequestBuilder::init(
    'APDUClass4',
    'APDUInstruction8',
    'APDUPar12',
    'APDUPar28'
)
    ->aPDUData('APDUData6')
    ->aPDUExpectedLength('APDUExpectedLength0')
    ->build();
```

