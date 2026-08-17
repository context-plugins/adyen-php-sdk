
# Get Accepted Terms of Service Document Response

## Structure

`GetAcceptedTermsOfServiceDocumentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `document` | `?string` | Optional | The accepted Terms of Service document in the requested format represented as a Base64-encoded bytes array. | getDocument(): ?string | setDocument(?string document): void |
| `id` | `?string` | Optional | The unique identifier of the legal entity. | getId(): ?string | setId(?string id): void |
| `termsOfServiceAcceptanceReference` | `?string` | Optional | An Adyen-generated reference for the accepted Terms of Service. | getTermsOfServiceAcceptanceReference(): ?string | setTermsOfServiceAcceptanceReference(?string termsOfServiceAcceptanceReference): void |
| `termsOfServiceDocumentFormat` | [`?string(TermsOfServiceDocumentFormatEnum)`](../../doc/models/terms-of-service-document-format-enum.md) | Optional | The format of the Terms of Service document. | getTermsOfServiceDocumentFormat(): ?string | setTermsOfServiceDocumentFormat(?string termsOfServiceDocumentFormat): void |

## Example

```php
use AdyenLib\Models\Builders\GetAcceptedTermsOfServiceDocumentResponseBuilder;
use AdyenLib\Models\TermsOfServiceDocumentFormatEnum;

$getAcceptedTermsOfServiceDocumentResponse = GetAcceptedTermsOfServiceDocumentResponseBuilder::init()
    ->document('document2')
    ->id('id4')
    ->termsOfServiceAcceptanceReference('termsOfServiceAcceptanceReference4')
    ->termsOfServiceDocumentFormat(TermsOfServiceDocumentFormatEnum::TXT)
    ->build();
```

