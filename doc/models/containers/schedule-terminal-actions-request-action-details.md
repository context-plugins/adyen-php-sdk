
# Schedule Terminal Actions Request Action Details

## Data Type

`ForceRebootDetails|InstallAndroidAppDetails|InstallAndroidCertificateDetails|ReleaseUpdateDetails|UninstallAndroidAppDetails|UninstallAndroidCertificateDetails`

## Cases

| Type |
|  --- |
| [`ForceRebootDetails`](../../../doc/models/force-reboot-details.md) |
| [`InstallAndroidAppDetails`](../../../doc/models/install-android-app-details.md) |
| [`InstallAndroidCertificateDetails`](../../../doc/models/install-android-certificate-details.md) |
| [`ReleaseUpdateDetails`](../../../doc/models/release-update-details.md) |
| [`UninstallAndroidAppDetails`](../../../doc/models/uninstall-android-app-details.md) |
| [`UninstallAndroidCertificateDetails`](../../../doc/models/uninstall-android-certificate-details.md) |

## ForceRebootDetails

### Initialization Code

#### Example

```php
$value = ForceRebootDetailsBuilder::init()
    ->type(Type210Enum::FORCEREBOOT)
    ->build();
```

## InstallAndroidAppDetails

### Initialization Code

#### Example

```php
$value = InstallAndroidAppDetailsBuilder::init()
    ->type(Type32Enum::INSTALLANDROIDAPP)
    ->build();
```

## InstallAndroidCertificateDetails

### Initialization Code

#### Example

```php
$value = InstallAndroidCertificateDetailsBuilder::init()
    ->type(Type42Enum::INSTALLANDROIDCERTIFICATE)
    ->build();
```

## ReleaseUpdateDetails

### Initialization Code

#### Example

```php
$value = ReleaseUpdateDetailsBuilder::init()
    ->type(Type61Enum::RELEASEUPDATE)
    ->build();
```

## UninstallAndroidAppDetails

### Initialization Code

#### Example

```php
$value = UninstallAndroidAppDetailsBuilder::init()
    ->type(Type71Enum::UNINSTALLANDROIDAPP)
    ->build();
```

## UninstallAndroidCertificateDetails

### Initialization Code

#### Example

```php
$value = UninstallAndroidCertificateDetailsBuilder::init()
    ->type(Type81Enum::UNINSTALLANDROIDCERTIFICATE)
    ->build();
```

