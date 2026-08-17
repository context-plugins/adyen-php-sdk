
# Authorised Card Users

## Structure

`AuthorisedCardUsers`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `legalEntityIds` | `?(string[])` | Optional | The legal entity IDs of the authorized card users linked to the specified payment instrument. | getLegalEntityIds(): ?array | setLegalEntityIds(?array legalEntityIds): void |

## Example

```php
use AdyenLib\Models\Builders\AuthorisedCardUsersBuilder;

$authorisedCardUsers = AuthorisedCardUsersBuilder::init()
    ->legalEntityIds(
        [
            'legalEntityIds2'
        ]
    )
    ->build();
```

