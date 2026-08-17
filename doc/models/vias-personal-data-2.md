
# Vias Personal Data 2

Personal information of the individual.

## Structure

`ViasPersonalData2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateOfBirth` | `?string` | Optional | The person's date of birth, in ISO-8601 YYYY-MM-DD format. For example, **2000-01-31**. | getDateOfBirth(): ?string | setDateOfBirth(?string dateOfBirth): void |
| `documentData` | [`?(PersonalDocumentData[])`](../../doc/models/personal-document-data.md) | Optional | Array that contains information about the person's identification document. You can submit only one entry per document type. | getDocumentData(): ?array | setDocumentData(?array documentData): void |
| `nationality` | `?string` | Optional | The nationality of the person represented by a two-character country code,  in [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) format. For example, **NL**.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `2` | getNationality(): ?string | setNationality(?string nationality): void |

## Example

```php
use AdyenLib\Models\Builders\ViasPersonalData2Builder;
use AdyenLib\Models\Builders\PersonalDocumentDataBuilder;
use AdyenLib\Models\Type15Enum;

$viasPersonalData2 = ViasPersonalData2Builder::init()
    ->dateOfBirth('dateOfBirth4')
    ->documentData(
        [
            PersonalDocumentDataBuilder::init(
                Type15Enum::ID
            )
                ->expirationDate('expirationDate8')
                ->issuerCountry('issuerCountry0')
                ->issuerState('issuerState0')
                ->number('number8')
                ->build()
        ]
    )
    ->nationality('nationality0')
    ->build();
```

