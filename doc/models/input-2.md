
# Input 2

Data entered by the user, related to the input command.

## Structure

`Input2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `inputCommand` | [`string(InputCommand1Enum)`](../../doc/models/input-command-1-enum.md) | Required | Type of requested input. Can be: **GetConfirmation**, **TextString**, **DigitString**, **DecimalString** or **GetMenuEntry**.<br>Possible values:<br><br>* **DecimalString**<br>* **DigitString**<br>* **GetAnyKey**<br>* **GetConfirmation**<br>* **GetFunctionKey**<br>* **GetMenuEntry**<br>* **Password**<br>* **SiteManager**<br>* **TextString** | getInputCommand(): string | setInputCommand(string inputCommand): void |
| `confirmedFlag` | `?bool` | Optional | Indicates te response of the user from the `GetConfirmation` input command. | getConfirmedFlag(): ?bool | setConfirmedFlag(?bool confirmedFlag): void |
| `functionKey` | `?int` | Optional | The number of the function key which is typed by the Customer on the POI or the Cashier on the Sale Terminal. | getFunctionKey(): ?int | setFunctionKey(?int functionKey): void |
| `textInput` | `?string` | Optional | The text typed by the Customer on the POI or by the Cashier on the Sale Terminal. | getTextInput(): ?string | setTextInput(?string textInput): void |
| `digitInput` | `?int` | Optional | The digits typed by the Customer on the POI or by the Cashier on the Sale Terminal. | getDigitInput(): ?int | setDigitInput(?int digitInput): void |
| `password` | `?string` | Optional | The text password typed by the Customer on the POI or by the Cashier on the Sale Terminal. | getPassword(): ?string | setPassword(?string password): void |
| `menuEntryNumber` | `?(int[])` | Optional | The index of the menu item (from 1 to n) which is selected by the Cashier on the Sale Terminal. The value -1 indicates that the immediate upper level of the menu is requested. The value 0 indicates that the root of the menu is requested. | getMenuEntryNumber(): ?array | setMenuEntryNumber(?array menuEntryNumber): void |

## Example

```php
use AdyenLib\Models\Builders\Input2Builder;
use AdyenLib\Models\InputCommand1Enum;

$input2 = Input2Builder::init(
    InputCommand1Enum::DECIMALSTRING
)
    ->confirmedFlag(false)
    ->functionKey(166)
    ->textInput('TextInput2')
    ->digitInput(120)
    ->password('Password8')
    ->build();
```

