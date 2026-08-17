
# Relayed Authorisation Data

## Structure

`RelayedAuthorisationData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `metadata` | `?array<string,string>` | Optional | Contains key-value pairs of your references and descriptions, for example, `customId`:`your-own-custom-field-12345`. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `reference` | `?string` | Optional | Your reference for the relayed authorisation data. | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\RelayedAuthorisationDataBuilder;

$relayedAuthorisationData = RelayedAuthorisationDataBuilder::init()
    ->metadata(
        [
            'key0' => 'metadata9',
            'key1' => 'metadata8'
        ]
    )
    ->reference('reference8')
    ->build();
```

