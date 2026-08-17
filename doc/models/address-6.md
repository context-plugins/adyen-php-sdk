
# Address 6

## Structure

`Address6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | The name of the city.<br><br>Supported characters: **[a-z] [A-Z] [0-9] . - — / # , ’ ° ( ) : ; [ ] & \ \|** and Space.<br><br>> Required when the `category` is **card**.<br><br>**Constraints**: *Minimum Length*: `3` | getCity(): ?string | setCity(?string city): void |
| `country` | `string` | Required | The two-character ISO 3166-1 alpha-2 country code. For example, **US**, **NL**, or **GB**. | getCountry(): string | setCountry(string country): void |
| `line1` | `?string` | Optional | The first line of the street address.<br><br>Supported characters: **[a-z] [A-Z] [0-9] . - — / # , ’ ° ( ) : ; [ ] & \ \|** and Space.<br><br>> Required when the `category` is **card**. | getLine1(): ?string | setLine1(?string line1): void |
| `line2` | `?string` | Optional | The second line of the street address.<br><br>Supported characters: **[a-z] [A-Z] [0-9] . - — / # , ’ ° ( ) : ; [ ] & \ \|** and Space.<br><br>> Required when the `category` is **card**. | getLine2(): ?string | setLine2(?string line2): void |
| `postalCode` | `?string` | Optional | The postal code.<br>Maximum length:<br><br>* 5 digits for an address in the US.<br>* 10 characters for an address in all other countries.<br><br>Supported characters: **[a-z] [A-Z] [0-9]** and Space.<br><br>> Required for addresses in the US.<br><br>**Constraints**: *Minimum Length*: `3` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `stateOrProvince` | `?string` | Optional | The two-letter ISO 3166-2 state or province code. For example, **CA** in the US or **ON** in Canada.<br><br>> Required for the US and Canada. | getStateOrProvince(): ?string | setStateOrProvince(?string stateOrProvince): void |

## Example

```php
use AdyenLib\Models\Builders\Address6Builder;

$address6 = Address6Builder::init(
    'country2'
)
    ->city('city8')
    ->line1('line10')
    ->line2('line22')
    ->postalCode('postalCode0')
    ->stateOrProvince('stateOrProvince6')
    ->build();
```

