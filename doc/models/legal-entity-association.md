
# Legal Entity Association

## Structure

`LegalEntityAssociation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `associatorId` | `?string` | Optional, Read-only | The unique identifier of another legal entity with which the `legalEntityId` is associated. When the `legalEntityId` is associated to legal entities other than the current one, the response returns all the associations. | getAssociatorId(): ?string | setAssociatorId(?string associatorId): void |
| `entityType` | `?string` | Optional, Read-only | The legal entity type of associated legal entity.<br><br>For example, **organization**, **soleProprietorship** or **individual**. | getEntityType(): ?string | setEntityType(?string entityType): void |
| `jobTitle` | `?string` | Optional | The individual's job title if the `type` is **uboThroughControl** or **signatory**. | getJobTitle(): ?string | setJobTitle(?string jobTitle): void |
| `legalEntityId` | `string` | Required | The unique identifier of the associated [legal entity](https://docs.adyen.com/api-explorer/legalentity/latest/post/legalEntities#responses-200-id). | getLegalEntityId(): string | setLegalEntityId(string legalEntityId): void |
| `name` | `?string` | Optional, Read-only | The name of the associated [legal entity](https://docs.adyen.com/api-explorer/legalentity/latest/post/legalEntities#responses-200-id).<br><br>- For **individual**, `name.firstName` and `name.lastName`.<br>- For **organization**, `legalName`.<br>- For **soleProprietorship**, `name`. | getName(): ?string | setName(?string name): void |
| `nominee` | `?bool` | Optional | Default value: **false**<br>Set to **true** if the entity association `type` **director**, **secondaryPartner** or **shareholder** is also a nominee. Only applicable to New Zealand. | getNominee(): ?bool | setNominee(?bool nominee): void |
| `relationship` | `?string` | Optional | The individual's relationship to a legal representative if the `type` is **legalRepresentative**. Possible values: **parent**, **guardian**. | getRelationship(): ?string | setRelationship(?string relationship): void |
| `settlorExemptionReason` | `?(string[])` | Optional | Defines the KYC exemption reason for a settlor associated with a trust. Only applicable to trusts in Australia.<br><br>For example, **professionalServiceProvider**, **deceased**, or **contributionBelowThreshold**. | getSettlorExemptionReason(): ?array | setSettlorExemptionReason(?array settlorExemptionReason): void |
| `type` | [`string(Type142Enum)`](../../doc/models/type-142-enum.md) | Required | Defines the relationship of the legal entity to the current legal entity.<br><br>Possible value for individuals: **legalRepresentative**.<br><br>Possible values for organizations: **director**, **signatory**, **trustOwnership**, **uboThroughOwnership**, **uboThroughControl**, **ultimateParentCompany**, or **immediateParentCompany**.<br><br>Possible values for sole proprietorships: **soleProprietorship**.<br><br>Possible value for trusts: **trust**.<br><br>Possible values for trust members: **definedBeneficiary**, **protector**, **secondaryTrustee**, **settlor**, **uboThroughControl**, or **uboThroughOwnership**.<br><br>Possible value for unincorporated partnership: **unincorporatedPartnership**.<br><br>Possible values for unincorporated partnership members: **secondaryPartner**, **uboThroughControl**, **uboThroughOwnership** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\LegalEntityAssociationBuilder;
use AdyenLib\Models\Type142Enum;

$legalEntityAssociation = LegalEntityAssociationBuilder::init(
    'legalEntityId4',
    Type142Enum::TRUSTOWNERSHIP
)
    ->jobTitle('jobTitle2')
    ->nominee(false)
    ->build();
```

