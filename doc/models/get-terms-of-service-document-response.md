
# Get Terms of Service Document Response

## Structure

`GetTermsOfServiceDocumentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `document` | `?string` | Optional | The Terms of Service document in Base64-encoded format. | getDocument(): ?string | setDocument(?string document): void |
| `id` | `?string` | Optional | The unique identifier of the legal entity. | getId(): ?string | setId(?string id): void |
| `language` | `?string` | Optional | The language used for the Terms of Service document, specified by the two-letter [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) language code. Possible value: **en** for English or **fr** for French.<br><br>Note that French is only available for some integration types in certain countries/regions. Reach out to your Adyen contact for more information. | getLanguage(): ?string | setLanguage(?string language): void |
| `termsOfServiceDocumentFormat` | `?string` | Optional | The format of the Terms of Service document. | getTermsOfServiceDocumentFormat(): ?string | setTermsOfServiceDocumentFormat(?string termsOfServiceDocumentFormat): void |
| `termsOfServiceDocumentId` | `?string` | Optional | The unique identifier of the Terms of Service document. | getTermsOfServiceDocumentId(): ?string | setTermsOfServiceDocumentId(?string termsOfServiceDocumentId): void |
| `type` | [`?string(Type64Enum)`](../../doc/models/type-64-enum.md) | Optional | The type of Terms of Service.<br><br>Possible values:<br><br>* **adyenForPlatformsManage**<br>* **adyenIssuing**<br>* **adyenForPlatformsAdvanced**<br>* **adyenCapital**<br>* **adyenAccount**<br>* **adyenCard**<br>* **adyenFranchisee**<br>* **adyenPccr**<br>* **adyenChargeCard**<br>* **kycOnInvite** | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\GetTermsOfServiceDocumentResponseBuilder;

$getTermsOfServiceDocumentResponse = GetTermsOfServiceDocumentResponseBuilder::init()
    ->document('document2')
    ->id('id8')
    ->language('language0')
    ->termsOfServiceDocumentFormat('termsOfServiceDocumentFormat2')
    ->termsOfServiceDocumentId('termsOfServiceDocumentId6')
    ->build();
```

