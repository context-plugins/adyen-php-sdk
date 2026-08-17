
# Account Party

## Structure

`AccountParty`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `identity` | [`Identity2`](../../doc/models/identity-2.md) | Required | Contains the identity details of the party. | getIdentity(): Identity2 | setIdentity(Identity2 identity): void |
| `role` | [`string(PartyRole2Enum)`](../../doc/models/party-role-2-enum.md) | Required | Specifies a role or capacity of the party in relation to the bank account. | getRole(): string | setRole(string role): void |

## Example

```php
use AdyenLib\Models\Builders\AccountPartyBuilder;
use AdyenLib\Models\Builders\Identity2Builder;
use AdyenLib\Models\PartyRole2Enum;

$accountParty = AccountPartyBuilder::init(
    Identity2Builder::init(
        'fullLegalName2',
        'name4'
    )->build(),
    PartyRole2Enum::OTHER
)->build();
```

