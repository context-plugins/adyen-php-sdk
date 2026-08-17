
# Individual Details

## Structure

`IndividualDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | [`?ViasName2`](../../doc/models/vias-name-2.md) | Optional | The name of the individual.<br><br>> Make sure your account holder registers using the name shown on their Photo ID.<br>> Maximum length: 80 characters<br>> Cannot contain numbers. /n Cannot be empty. | getName(): ?ViasName2 | setName(?ViasName2 name): void |
| `personalData` | [`?ViasPersonalData2`](../../doc/models/vias-personal-data-2.md) | Optional | Personal information of the individual. | getPersonalData(): ?ViasPersonalData2 | setPersonalData(?ViasPersonalData2 personalData): void |

## Example

```php
use AdyenLib\Models\Builders\IndividualDetailsBuilder;
use AdyenLib\Models\Builders\ViasName2Builder;
use AdyenLib\Models\GenderEnum;
use AdyenLib\Models\Builders\ViasPersonalData2Builder;
use AdyenLib\Models\Builders\PersonalDocumentDataBuilder;
use AdyenLib\Models\Type15Enum;

$individualDetails = IndividualDetailsBuilder::init()
    ->name(
        ViasName2Builder::init()
            ->firstName('firstName4')
            ->gender(GenderEnum::MALE)
            ->infix('infix4')
            ->lastName('lastName4')
            ->build()
    )
    ->personalData(
        ViasPersonalData2Builder::init()
            ->dateOfBirth('dateOfBirth2')
            ->documentData(
                [
                    PersonalDocumentDataBuilder::init(
                        Type15Enum::ID
                    )
                        ->expirationDate('expirationDate8')
                        ->issuerCountry('issuerCountry0')
                        ->issuerState('issuerState0')
                        ->number('number8')
                        ->build(),
                    PersonalDocumentDataBuilder::init(
                        Type15Enum::ID
                    )
                        ->expirationDate('expirationDate8')
                        ->issuerCountry('issuerCountry0')
                        ->issuerState('issuerState0')
                        ->number('number8')
                        ->build(),
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
            ->nationality('nationality4')
            ->build()
    )
    ->build();
```

