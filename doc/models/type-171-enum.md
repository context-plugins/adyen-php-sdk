
# Type 171 Enum

Type of trust.

See possible values for trusts in [Australia](https://docs.adyen.com/platforms/verification-requirements/?tab=trust_3_4#trust-types-in-australia) and [New Zealand](https://docs.adyen.com/platforms/verification-requirements/?tab=trust_3_4#trust-types-in-new-zealand).

## Enumeration

`Type171Enum`

## Fields

| Name |
|  --- |
| `BUSINESSTRUST` |
| `CASHMANAGEMENTTRUST` |
| `CHARITABLETRUST` |
| `CORPORATEUNITTRUST` |
| `DECEASEDESTATE` |
| `DISCRETIONARYTRUST` |
| `DISCRETIONARYINVESTMENTTRUST` |
| `DISCRETIONARYSERVICESMANAGEMENTTRUST` |
| `DISCRETIONARYTRADINGTRUST` |
| `FAMILYTRUST` |
| `FIRSTHOMESAVERACCOUNTSTRUST` |
| `FIXEDTRUST` |
| `FIXEDUNITTRUST` |
| `HYBRIDTRUST` |
| `LISTEDPUBLICUNITTRUST` |
| `OTHERTRUST` |
| `POOLEDSUPERANNUATIONTRUST` |
| `PUBLICTRADINGTRUST` |
| `UNLISTEDPUBLICUNITTRUST` |

## Example

```php
use AdyenLib\Models\Type171Enum;

$type171 = Type171Enum::CHARITABLETRUST;
```

