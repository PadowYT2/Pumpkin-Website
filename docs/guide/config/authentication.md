# Authentication

Servers authenthicate with Mojang's session servers in order to ensure the client is playing on a legitimate, paid account. Pumpkin allows you to fully configure authentication.

> [!WARNING]
> Most servers should not change the default authenthication configuration. Doing so may have unintended consequnces. **Only change these settings if you know what you are doing!**

## `enabled`

Whether authenthication is enabled or not.

:::code-group
```toml [features.toml]
[authentication]
enabled = true # Boolean
```
:::

## `prevent_proxy_connections`

Whether to block proxy connections or not.

:::code-group
```toml [features.toml]
[authentication]
prevent_proxy_connections = false # Boolean
```
:::

## `url`

The URL to authenthicate with. Uses Mojang's session servers to authenthicate if not specified.

:::code-group
```toml [features.toml]
[authentication]
url = "" # String (optional)
```
:::

### Placeholders
- `{username}` - Player username
- `{server_hash}` - Hash of the server

## `prevent_proxy_connection_auth_url`

The URL to authenthicate with if `prevent_proxy_connections` is enabled. Uses Mojang's session servers to authenthicate if not specified.

:::code-group
```toml [features.toml]
[authentication]
prevent_proxy_connection_auth_url = "" # String (optional)
```
:::

### Placeholders
- `{username}` - Player username
- `{server_hash}` - Hash of the server
- `{ip}` - IP Address of the player

## `player_profile.allow_banned_players`

Allow players flagged by Mojang.

:::code-group
```toml [features.toml]
[authentication.player_profile]
allow_banned_players = false # Boolean
```
:::

## `player_profile.allowed_actions`

What actions are allowed if `allow_banned_players` is enabled.

:::code-group
```toml [features.toml]
[authentication.player_profile]
allowed_actions = ["FORCED_NAME_CHANGE", "USING_BANNED_SKIN"] # Array of enums (FORCED_NAME_CHANGE, USING_BANNED_SKIN)
```
:::

## `textures.enabled`

Whether to filter/validate player textures (e.g. Skins/Capes).

:::code-group
```toml [features.toml]
[authentication.textures]
enabled = true # Boolean
```
:::

## `textures.allowed_url_schemes`

Allowed URL Schemes for textures.

:::code-group
```toml [features.toml]
[authentication.textures]
allowed_url_schemes = ["http", "https"] # Array of strings
```
:::

## `textures.allowed_url_domains`
Allowed URL domains for textures.

:::code-group
```toml [features.toml]
[authentication.textures]
allowed_url_domains = [".minecraft.net", ".mojang.com"] # Array of strings
```
:::

## `textures.types.skin`

Whether to use player skins or not.

:::code-group
```toml [features.toml]
[authentication.textures.types]
skin = true # Boolean
```
:::

## `textures.types.cape`

Whether to use player capes or not.

:::code-group
```toml [features.toml]
[authentication.textures.types]
cape = true # Boolean
```
:::

## `textures.types.elytra`

Whether to use player elytras or not.

:::code-group
```toml [features.toml]
[authentication.textures.types]
elytra = true # Boolean
```
:::
