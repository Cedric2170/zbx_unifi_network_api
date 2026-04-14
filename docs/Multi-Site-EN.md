# Changes

## Processing
- Added a JavaScript preprocessing step on sites to generate:
  - `site_label` (site label displayed in Zabbix),
  - `zbx_host` (unique host name: `site_label_slug + "-" + id`, otherwise `id`).
- Enriched clients/devices payloads by adding `site_label` (in addition to `site_name`).

## API
- Updated clients/devices API URLs:
  - `/sites/{HOST.HOST}/...` -> `/sites/{$SITE.ID}/...`
  - Goal: stop relying on UniFi's "Default" host name.

## Macros
- Sites: added LLD macros `{#SITE_LABEL}` and `{#ZBX_HOST}`.
- Template: added `{$SITE_LABEL}` (propagated at site level).
- Clients/Devices: added LLD macro `{#SITE_LABEL}`.

## Naming and Discovery
- Site host prototype:
  - `host: {#ID}` -> `host: {#ZBX_HOST}`
  - Display name now uses `{#SITE_LABEL}`.
- Clients/Devices: names and tags now use `SITE_LABEL` instead of `SITE.NAME`.
- Discovery names updated:
  - `Discovery Sites` -> `Sites`
  - `Discovery Ports` -> `Ports`
  - `Discovery Radios` -> `Radios`
  - `Discovery Radios Statistics` -> `Radios Statistics`
  - `Discovery Clients` -> `Clients`
  - `Discovery Devices` -> `Devices`

## Variables
- `{$SITE_LABEL}`: custom site label.
- `{#SITE_LABEL}`: discovered site label value.
- `{#ZBX_HOST}`: unique technical host name for Zabbix.
- `{$SITE.ID}`: site ID used in API URLs.

## Fork Author
- Cédric Baertschi ([`@Cedric2170`](https://github.com/Cedric2170))
