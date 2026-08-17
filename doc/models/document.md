
# Document

## Structure

`Document`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attachment` | [`?Attachment1`](../../doc/models/attachment-1.md) | Optional | Object that contains the document. | getAttachment(): ?Attachment1 | setAttachment(?Attachment1 attachment): void |
| `attachments` | [`?(Attachment[])`](../../doc/models/attachment.md) | Optional | Array that contains the document. The array supports multiple attachments for uploading different sides or pages of a document. | getAttachments(): ?array | setAttachments(?array attachments): void |
| `creationDate` | `?DateTime` | Optional, Read-only | The creation date of the document. | getCreationDate(): ?\DateTime | setCreationDate(?\DateTime creationDate): void |
| `description` | `string` | Required | Your description for the document. | getDescription(): string | setDescription(string description): void |
| `expiryDate` | `?string` | Optional | The expiry date of the document, in YYYY-MM-DD format. | getExpiryDate(): ?string | setExpiryDate(?string expiryDate): void |
| `fileName` | `?string` | Optional | The filename of the document. | getFileName(): ?string | setFileName(?string fileName): void |
| `id` | `?string` | Optional, Read-only | The unique identifier of the document. | getId(): ?string | setId(?string id): void |
| `issuerCountry` | `?string` | Optional | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code where the document was issued. For example, **US**. | getIssuerCountry(): ?string | setIssuerCountry(?string issuerCountry): void |
| `issuerState` | `?string` | Optional | The state or province where the document was issued (AU only). | getIssuerState(): ?string | setIssuerState(?string issuerState): void |
| `modificationDate` | `?DateTime` | Optional, Read-only | The modification date of the document. | getModificationDate(): ?\DateTime | setModificationDate(?\DateTime modificationDate): void |
| `number` | `?string` | Optional | The number in the document. | getNumber(): ?string | setNumber(?string number): void |
| `owner` | [`?OwnerEntity2`](../../doc/models/owner-entity-2.md) | Optional | Contains information about the resource that owns the document. | getOwner(): ?OwnerEntity2 | setOwner(?OwnerEntity2 owner): void |
| `type` | [`string(Type84Enum)`](../../doc/models/type-84-enum.md) | Required | Type of document, used when providing an ID number or uploading a document. The possible values depend on the legal entity type.<br><br>* For **organization**, the `type` values can be **proofOfAddress**, **registrationDocument**, **vatDocument**, **proofOfOrganizationTaxInfo**, **proofOfOwnership**, **proofOfIndustry**, **proofOfSignatory**, **proofOfDirector**, or **proofOfFundingOrWealthSource**.<br><br>* For **individual**, the `type` values can be **identityCard**, **driversLicense**, **passport**, **liveSelfie**, **proofOfNationalIdNumber**, **proofOfResidency**, **proofOfIndustry**, **proofOfIndividualTaxId**, **proofOfFundingOrWealthSource** or **proofOfRelationship**.<br><br>* For **soleProprietorship**, the `type` values can be **constitutionalDocument**, **proofOfAddress**, or **proofOfIndustry**.<br><br>* For **trust**, the `type` value is **constitutionalDocument**.<br><br>* For **unincorporatedPartnership**, the `type` value is **constitutionalDocument**.<br><br>* Use **bankStatement** to upload documents for a [transfer instrument](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/transferInstruments__resParam_id). | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\DocumentBuilder;
use AdyenLib\Models\Type84Enum;
use AdyenLib\Models\Builders\Attachment1Builder;
use AdyenLib\Models\Builders\AttachmentBuilder;

$document = DocumentBuilder::init(
    'description6',
    Type84Enum::PASSPORT
)
    ->attachment(
        Attachment1Builder::init(
            'content2'
        )
            ->contentType('contentType4')
            ->filename('filename0')
            ->pageName('pageName0')
            ->pageType('pageType6')
            ->build()
    )
    ->attachments(
        [
            AttachmentBuilder::init(
                'content4'
            )
                ->contentType('contentType6')
                ->filename('filename2')
                ->pageName('pageName2')
                ->pageType('pageType8')
                ->build(),
            AttachmentBuilder::init(
                'content4'
            )
                ->contentType('contentType6')
                ->filename('filename2')
                ->pageName('pageName2')
                ->pageType('pageType8')
                ->build(),
            AttachmentBuilder::init(
                'content4'
            )
                ->contentType('contentType6')
                ->filename('filename2')
                ->pageName('pageName2')
                ->pageType('pageType8')
                ->build()
        ]
    )
    ->expiryDate('expiryDate4')
    ->fileName('fileName0')
    ->build();
```

