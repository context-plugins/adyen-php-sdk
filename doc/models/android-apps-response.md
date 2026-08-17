
# Android Apps Response

## Structure

`AndroidAppsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(AndroidApp[])`](../../doc/models/android-app.md) | Optional | Apps uploaded for Android payment terminals. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\AndroidAppsResponseBuilder;
use AdyenLib\Models\Builders\AndroidAppBuilder;
use AdyenLib\Models\Status7Enum;
use AdyenLib\Models\Builders\AndroidAppErrorBuilder;

$androidAppsResponse = AndroidAppsResponseBuilder::init()
    ->data(
        [
            AndroidAppBuilder::init(
                'id0',
                Status7Enum::INVALID
            )
                ->description('description0')
                ->errorCode('errorCode6')
                ->errors(
                    [
                        AndroidAppErrorBuilder::init()
                            ->errorCode('errorCode6')
                            ->terminalModels(
                                [
                                    'terminalModels3',
                                    'terminalModels4'
                                ]
                            )
                            ->build()
                    ]
                )
                ->label('label0')
                ->packageName('packageName6')
                ->build()
        ]
    )
    ->build();
```

