
# Policy

## Structure

`Policy`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `resources` | [`?(Resource2[])`](../../doc/models/resource-2.md) | Optional | An object containing the type and the unique identifier of the user of the component.<br><br>For [Onboarding components](https://docs.adyen.com/platforms/onboard-users/components), this is the ID of the legal entity that has a contractual relationship with your platform. For sole proprietorships, use the ID of the legal entity of the individual owner.<br><br>For [Platform Experience components](https://docs.adyen.com/platforms/build-user-dashboards), this is the ID of the account holder that is associated with the balance account shown in the component.<br><br>**Constraints**: *Unique Items Required* | getResources(): ?array | setResources(?array resources): void |
| `roles` | `?(string[])` | Optional | The name of the role required to use the component.<br><br>**Constraints**: *Unique Items Required* | getRoles(): ?array | setRoles(?array roles): void |

## Example

```php
use AdyenLib\Models\Builders\PolicyBuilder;
use AdyenLib\Models\Builders\Resource2Builder;

$policy = PolicyBuilder::init()
    ->resources(
        [
            Resource2Builder::init()
                ->type('Resource')
                ->build()
        ]
    )
    ->roles(
        [
            'roles8'
        ]
    )
    ->build();
```

