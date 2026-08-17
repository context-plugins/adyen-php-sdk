
# Url

## Structure

`Url`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `encrypted` | `?bool` | Optional | Indicates if the message sent to this URL should be encrypted. | getEncrypted(): ?bool | setEncrypted(?bool encrypted): void |
| `password` | `?string` | Optional | The password for authentication of the notifications. | getPassword(): ?string | setPassword(?string password): void |
| `url` | `?string` | Optional | The URL in the format: http(s)://domain.com. | getUrl(): ?string | setUrl(?string url): void |
| `username` | `?string` | Optional | The username for authentication of the notifications. | getUsername(): ?string | setUsername(?string username): void |

## Example

```php
use AdyenLib\Models\Builders\UrlBuilder;

$url = UrlBuilder::init()
    ->encrypted(false)
    ->password('password8')
    ->url('url8')
    ->username('username6')
    ->build();
```

