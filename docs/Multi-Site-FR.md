# Modifications

## Traitement
- Ajout d'un prétraitement JavaScript sur les sites pour générer:
  - `site_label`:     (Libellé de site affiché dans Zabbix),
  - `zbx_host`:       (Nom d'hôte unique: `site_label_slug + "-" + id`, sinon `id`).
- Enrichissement clients/devices: ajout de `site_label` (en plus de `site_name`).

## API
- URLs clients/devices modifiées:
  - `/sites/{HOST.HOST}/...` -> `/sites/{$SITE.ID}/...`
  - But: ne plus dépendre du nom d'hôte "Default" de Unifi.

## Macros
- Sites:              ajout des LLD `{#SITE_LABEL}` et `{#ZBX_HOST}`.
- Template:           ajout de `{$SITE_LABEL}` (propagée au niveau site).
- Clients/Devices:    ajout de la LLD `{#SITE_LABEL}`.

## Nommage et découvertes
- Host prototype des sites:
  - `host: {#ID}` -> `host: {#ZBX_HOST}`
  - Nom affiché basé sur `{#SITE_LABEL}`.
- Clients/Devices: noms et tags basés sur `SITE_LABEL` au lieu de `SITE.NAME`.
- Discoveries renommées:
  - `Discovery Sites`   -> `Sites`
  - `Discovery Ports`   -> `Ports`
  - `Discovery Radios`  -> `Radios`
  - `Discovery Radios Statistics`   -> `Radios Statistics`
  - `Discovery Clients` -> `Clients`
  - `Discovery Devices` -> `Devices`

## Variables
- `{$SITE_LABEL}`:    libellé personnalisé du site.
- `{#SITE_LABEL}`:    libellé de site issu de la découverte.
- `{#ZBX_HOST}`:      nom d'hôte technique unique pour Zabbix.
- `{$SITE.ID}`:       ID de site utilisé dans les URLs API.

## Fork Author
- Cédric Baertschi ([`@Cedric2170`](https://github.com/Cedric2170))
