
# Relayed Authorisation Data 2

If you are using relayed authorisation, this object contains information from the relayed authorisation response from your server.

## Structure

`RelayedAuthorisationData2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `metadata` | `?array<string,string>` | Optional | Contains key-value pairs of your references and descriptions, for example, `customId`:`your-own-custom-field-12345`. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `reference` | `?string` | Optional | Your reference for the relayed authorisation data. | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\RelayedAuthorisationData2Builder;

$relayedAuthorisationData2 = RelayedAuthorisationData2Builder::init()
    ->metadata(
        [
            'key0' => 'metadata5',
            'key1' => 'metadata4'
        ]
    )
    ->reference('reference4')
    ->build();
```

