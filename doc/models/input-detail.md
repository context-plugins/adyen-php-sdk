
# Input Detail

## Structure

`InputDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `configuration` | `?array<string,string>` | Optional | Configuration parameters for the required input. | getConfiguration(): ?array | setConfiguration(?array configuration): void |
| `details` | [`?(SubInputDetail[])`](../../doc/models/sub-input-detail.md) | Optional | Input details can also be provided recursively. | getDetails(): ?array | setDetails(?array details): void |
| `inputDetails` | [`?(SubInputDetail[])`](../../doc/models/sub-input-detail.md) | Optional | Input details can also be provided recursively (deprecated). | getInputDetails(): ?array | setInputDetails(?array inputDetails): void |
| `itemSearchUrl` | `?string` | Optional | In case of a select, the URL from which to query the items. | getItemSearchUrl(): ?string | setItemSearchUrl(?string itemSearchUrl): void |
| `items` | [`?(Item[])`](../../doc/models/item.md) | Optional | In case of a select, the items to choose from. | getItems(): ?array | setItems(?array items): void |
| `key` | `?string` | Optional | The value to provide in the result. | getKey(): ?string | setKey(?string key): void |
| `optional` | `?bool` | Optional | True if this input value is optional. | getOptional(): ?bool | setOptional(?bool optional): void |
| `type` | `?string` | Optional | The type of the required input. | getType(): ?string | setType(?string type): void |
| `value` | `?string` | Optional | The value can be pre-filled, if available. | getValue(): ?string | setValue(?string value): void |

## Example

```php
use AdyenLib\Models\Builders\InputDetailBuilder;
use AdyenLib\Models\Builders\SubInputDetailBuilder;
use AdyenLib\Models\Builders\ItemBuilder;

$inputDetail = InputDetailBuilder::init()
    ->configuration(
        [
            'key0' => 'configuration4',
            'key1' => 'configuration3'
        ]
    )
    ->details(
        [
            SubInputDetailBuilder::init()
                ->configuration(
                    [
                        'key0' => 'configuration6',
                        'key1' => 'configuration7'
                    ]
                )
                ->items(
                    [
                        ItemBuilder::init()
                            ->id('id8')
                            ->name('name8')
                            ->build()
                    ]
                )
                ->key('key0')
                ->optional(false)
                ->type('type0')
                ->build(),
            SubInputDetailBuilder::init()
                ->configuration(
                    [
                        'key0' => 'configuration6',
                        'key1' => 'configuration7'
                    ]
                )
                ->items(
                    [
                        ItemBuilder::init()
                            ->id('id8')
                            ->name('name8')
                            ->build()
                    ]
                )
                ->key('key0')
                ->optional(false)
                ->type('type0')
                ->build()
        ]
    )
    ->inputDetails(
        [
            SubInputDetailBuilder::init()
                ->configuration(
                    [
                        'key0' => 'configuration6'
                    ]
                )
                ->items(
                    [
                        ItemBuilder::init()
                            ->id('id8')
                            ->name('name8')
                            ->build(),
                        ItemBuilder::init()
                            ->id('id8')
                            ->name('name8')
                            ->build(),
                        ItemBuilder::init()
                            ->id('id8')
                            ->name('name8')
                            ->build()
                    ]
                )
                ->key('key0')
                ->optional(false)
                ->type('type0')
                ->build()
        ]
    )
    ->itemSearchUrl('itemSearchUrl6')
    ->items(
        [
            ItemBuilder::init()
                ->id('id8')
                ->name('name8')
                ->build()
        ]
    )
    ->build();
```

