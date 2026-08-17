
# Token Details

## Structure

`TokenDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `tokenData` | `?array<string,string>` | Optional | - | getTokenData(): ?array | setTokenData(?array tokenData): void |
| `tokenDataType` | `?string` | Optional | - | getTokenDataType(): ?string | setTokenDataType(?string tokenDataType): void |

## Example

```php
use AdyenLib\Models\Builders\TokenDetailsBuilder;

$tokenDetails = TokenDetailsBuilder::init()
    ->tokenData(
        [
            'key0' => 'tokenData7'
        ]
    )
    ->tokenDataType('tokenDataType0')
    ->build();
```

