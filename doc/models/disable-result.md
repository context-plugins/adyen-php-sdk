
# Disable Result

## Structure

`DisableResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | `?string` | Optional | Depending on whether a specific recurring detail was in the request, result is either [detail-successfully-disabled] or [all-details-successfully-disabled]. | getResponse(): ?string | setResponse(?string response): void |

## Example

```php
use AdyenLib\Models\Builders\DisableResultBuilder;

$disableResult = DisableResultBuilder::init()
    ->response('response4')
    ->build();
```

