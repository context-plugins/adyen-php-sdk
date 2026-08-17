
# SDK Ephem Pub Key 1

The `sdkEphemPubKey` value as received from the 3D Secure 2 SDK.

## Structure

`SDKEphemPubKey1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `crv` | `?string` | Optional | The `crv` value as received from the 3D Secure 2 SDK. | getCrv(): ?string | setCrv(?string crv): void |
| `kty` | `?string` | Optional | The `kty` value as received from the 3D Secure 2 SDK. | getKty(): ?string | setKty(?string kty): void |
| `x` | `?string` | Optional | The `x` value as received from the 3D Secure 2 SDK. | getX(): ?string | setX(?string x): void |
| `y` | `?string` | Optional | The `y` value as received from the 3D Secure 2 SDK. | getY(): ?string | setY(?string y): void |

## Example

```php
use AdyenLib\Models\Builders\SDKEphemPubKey1Builder;

$sDKEphemPubKey1 = SDKEphemPubKey1Builder::init()
    ->crv('crv6')
    ->kty('kty6')
    ->x('x4')
    ->y('y2')
    ->build();
```

