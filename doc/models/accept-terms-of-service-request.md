
# Accept Terms of Service Request

## Structure

`AcceptTermsOfServiceRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acceptedBy` | `string` | Required | The legal entity ID of the user accepting the Terms of Service.<br><br>For organizations, this must be the individual legal entity ID of an authorized signatory for the organization.<br><br>For sole proprietorships, this must be the individual legal entity ID of the owner.<br><br>For individuals, this must be the individual legal entity id of either the individual, parent, or guardian. | getAcceptedBy(): string | setAcceptedBy(string acceptedBy): void |
| `ipAddress` | `?string` | Optional | The IP address of the user accepting the Terms of Service. | getIpAddress(): ?string | setIpAddress(?string ipAddress): void |

## Example

```php
use AdyenLib\Models\Builders\AcceptTermsOfServiceRequestBuilder;

$acceptTermsOfServiceRequest = AcceptTermsOfServiceRequestBuilder::init(
    'acceptedBy6'
)
    ->ipAddress('ipAddress8')
    ->build();
```

