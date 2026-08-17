
# Get Terms of Service Document Request

## Structure

`GetTermsOfServiceDocumentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `language` | `string` | Required | The language to be used for the Terms of Service document, specified by the two-letter [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) language code. Possible values: **en** for English or **fr** for French. | getLanguage(): string | setLanguage(string language): void |
| `termsOfServiceDocumentFormat` | `?string` | Optional | The requested format for the Terms of Service document. Default value: JSON. Possible values: **JSON**, **PDF**, or **TXT**. | getTermsOfServiceDocumentFormat(): ?string | setTermsOfServiceDocumentFormat(?string termsOfServiceDocumentFormat): void |
| `type` | [`string(Type64Enum)`](../../doc/models/type-64-enum.md) | Required | The type of Terms of Service.<br><br>Possible values:<br><br>* **adyenForPlatformsManage**<br>* **adyenIssuing**<br>* **adyenForPlatformsAdvanced**<br>* **adyenCapital**<br>* **adyenAccount**<br>* **adyenCard**<br>* **adyenFranchisee**<br>* **adyenPccr**<br>* **adyenChargeCard**<br>* **kycOnInvite** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\GetTermsOfServiceDocumentRequestBuilder;
use AdyenLib\Models\Type64Enum;

$getTermsOfServiceDocumentRequest = GetTermsOfServiceDocumentRequestBuilder::init(
    'language0',
    Type64Enum::ADYENCARD
)
    ->termsOfServiceDocumentFormat('termsOfServiceDocumentFormat2')
    ->build();
```

