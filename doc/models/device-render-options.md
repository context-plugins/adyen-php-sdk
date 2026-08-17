
# Device Render Options

Display options for the 3D Secure 2 SDK.
Optional and only for `deviceChannel` **app**.

## Structure

`DeviceRenderOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sdkInterface` | [`?string(SdkInterfaceEnum)`](../../doc/models/sdk-interface-enum.md) | Optional | Supported SDK interface types.<br>Allowed values:<br><br>* native<br>* html<br>* both<br><br>**Default**: `SdkInterfaceEnum::BOTH` | getSdkInterface(): ?string | setSdkInterface(?string sdkInterface): void |
| `sdkUiType` | [`?(string(SdkUiTypeEnum)[])`](../../doc/models/sdk-ui-type-enum.md) | Optional | UI types supported for displaying specific challenges.<br>Allowed values:<br><br>* text<br>* singleSelect<br>* outOfBand<br>* otherHtml<br>* multiSelect | getSdkUiType(): ?array | setSdkUiType(?array sdkUiType): void |

## Example

```php
use AdyenLib\Models\Builders\DeviceRenderOptionsBuilder;
use AdyenLib\Models\SdkInterfaceEnum;
use AdyenLib\Models\SdkUiTypeEnum;

$deviceRenderOptions = DeviceRenderOptionsBuilder::init()
    ->sdkInterface(SdkInterfaceEnum::BOTH)
    ->sdkUiType(
        [
            SdkUiTypeEnum::OUTOFBAND,
            SdkUiTypeEnum::SINGLESELECT
        ]
    )
    ->build();
```

