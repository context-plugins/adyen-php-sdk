
# Enable Service Request

It conveys the services that will be enabled for the POI Terminal without the request of the Sale System, and a possible invitation for the Customer to start the services.
Content of the Enable Service Request message.

## Structure

`EnableServiceRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionAction` | [`string(TransactionAction1Enum)`](../../doc/models/transaction-action-1-enum.md) | Required | Action to realise on a transaction. In an `EnableService` request message:<br><br>- Starts a transaction by a swipe-ahead mechanism, with the services which are enabled.<br>- Aborts a swipe-ahead transaction or started by a `CardAcquisition`, and not followed by a service request from the Sale System to complete the transaction.<br>  Possible values:<br><br>* **AbortTransaction**<br>* **StartTransaction** | getTransactionAction(): string | setTransactionAction(string transactionAction): void |
| `servicesEnabled` | [`?(string(ServicesEnabledEnum)[])`](../../doc/models/services-enabled-enum.md) | Optional | Services which are enabled before the start-up of a transaction.<br>Mandatory if `TransactionAction` is `StartTransaction`, absent if not.<br>Possible values:<br><br>* **CardAcquisition**<br>* **Loyalty**<br>* **Payment** | getServicesEnabled(): ?array | setServicesEnabled(?array servicesEnabled): void |
| `displayOutput` | [`?DisplayOutput2`](../../doc/models/display-output-2.md) | Optional | Information to display and the way to process the display. | getDisplayOutput(): ?DisplayOutput2 | setDisplayOutput(?DisplayOutput2 displayOutput): void |

## Example

```php
use AdyenLib\Models\Builders\EnableServiceRequestBuilder;
use AdyenLib\Models\TransactionAction1Enum;
use AdyenLib\Models\ServicesEnabledEnum;
use AdyenLib\Models\Builders\DisplayOutput2Builder;
use AdyenLib\Models\Device11Enum;
use AdyenLib\Models\InfoQualify1Enum;
use AdyenLib\Models\Builders\OutputContent1Builder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;
use AdyenLib\Models\Builders\MenuEntryBuilder;
use AdyenLib\Models\OutputFormat2Enum;
use AdyenLib\Models\MenuEntryTag1Enum;
use AdyenLib\Models\Builders\PredefinedContentBuilder;

$enableServiceRequest = EnableServiceRequestBuilder::init(
    TransactionAction1Enum::STARTTRANSACTION
)
    ->servicesEnabled(
        [
            ServicesEnabledEnum::LOYALTY,
            ServicesEnabledEnum::CARDACQUISITION
        ]
    )
    ->displayOutput(
        DisplayOutput2Builder::init(
            Device11Enum::CASHIERDISPLAY,
            InfoQualify1Enum::STATUS,
            OutputContent1Builder::init(
                OutputFormat1Enum::XHTML
            )
                ->predefinedContent(
                    PredefinedContent1Builder::init(
                        'ReferenceID0'
                    )
                        ->language('Language2')
                        ->build()
                )
                ->outputText(
                    [
                        OutputTextBuilder::init(
                            'Text6'
                        )
                            ->characterSet(194)
                            ->startRow(74)
                            ->startColumn(220)
                            ->characterWidth(CharacterWidth1Enum::SINGLEWIDTH)
                            ->characterHeight(CharacterHeight1Enum::SINGLEHEIGHT)
                            ->build()
                    ]
                )
                ->outputXHTML('OutputXHTML2')
                ->outputBarcode(
                    OutputBarcode1Builder::init(
                        'BarcodeValue2'
                    )->build()
                )->build()
        )
            ->responseRequiredFlag(false)
            ->minimumDisplayTime(110)
            ->menuEntry(
                [
                    MenuEntryBuilder::init(
                        OutputFormat2Enum::XHTML
                    )
                        ->menuEntryTag(MenuEntryTag1Enum::SUBMENU)
                        ->defaultSelectedFlag(false)
                        ->predefinedContent(
                            PredefinedContentBuilder::init(
                                'ReferenceID0'
                            )
                                ->language('Language2')
                                ->build()
                        )
                        ->outputText(
                            [
                                OutputTextBuilder::init(
                                    'Text6'
                                )
                                    ->characterSet(194)
                                    ->startRow(74)
                                    ->startColumn(220)
                                    ->characterWidth(CharacterWidth1Enum::SINGLEWIDTH)
                                    ->characterHeight(CharacterHeight1Enum::SINGLEHEIGHT)
                                    ->build(),
                                OutputTextBuilder::init(
                                    'Text6'
                                )
                                    ->characterSet(194)
                                    ->startRow(74)
                                    ->startColumn(220)
                                    ->characterWidth(CharacterWidth1Enum::SINGLEWIDTH)
                                    ->characterHeight(CharacterHeight1Enum::SINGLEHEIGHT)
                                    ->build()
                            ]
                        )
                        ->outputXHTML('OutputXHTML8')
                        ->build(),
                    MenuEntryBuilder::init(
                        OutputFormat2Enum::XHTML
                    )
                        ->menuEntryTag(MenuEntryTag1Enum::SUBMENU)
                        ->defaultSelectedFlag(false)
                        ->predefinedContent(
                            PredefinedContentBuilder::init(
                                'ReferenceID0'
                            )
                                ->language('Language2')
                                ->build()
                        )
                        ->outputText(
                            [
                                OutputTextBuilder::init(
                                    'Text6'
                                )
                                    ->characterSet(194)
                                    ->startRow(74)
                                    ->startColumn(220)
                                    ->characterWidth(CharacterWidth1Enum::SINGLEWIDTH)
                                    ->characterHeight(CharacterHeight1Enum::SINGLEHEIGHT)
                                    ->build(),
                                OutputTextBuilder::init(
                                    'Text6'
                                )
                                    ->characterSet(194)
                                    ->startRow(74)
                                    ->startColumn(220)
                                    ->characterWidth(CharacterWidth1Enum::SINGLEWIDTH)
                                    ->characterHeight(CharacterHeight1Enum::SINGLEHEIGHT)
                                    ->build()
                            ]
                        )
                        ->outputXHTML('OutputXHTML8')
                        ->build()
                ]
            )
            ->outputSignature('OutputSignature4')
            ->build()
    )
    ->build();
```

