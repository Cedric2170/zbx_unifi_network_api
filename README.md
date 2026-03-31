<p align="center">
    <img src="docs/image/logo.avif" height="128" alt="Zabbix + UniFi Network logo">
    <h1 align="center">UniFi Network Zabbix Template</h2>
</p>

Zabbix template for monitor the UniFi Network application via the official API.

> [!NOTE]
> Community‑driven and not affiliated with Ubiquiti Networks.

> [!WARNING]
> It has been tested on UniFi Network Application 9.5.21, previous releases have not been tested.

> [!IMPORTANT]
> Only Zabbix 7.4 and above versions are supported as it required nested host discovery Features.

## Features

- UniFi Network Application version.
- Number of Clients connected per Site.
- Devices state.
- Devices uptime.
- Devices firmware version.
- Devices CPU and Memory usage.
- Devices uplink tx and rx rate.
- Devices Configuration changes.
- Devices port state and statistics.
- Devices radios state and statistics.
- Clients general info.

## How To Use

1. **Import the Zabbix template** file 'zbx_template_unifi_network_api.yaml' that matches your Zabbix Server version.
2. **Create a UniFi API key** in Settings → Control Plane → Integrations → Your API Keys, and set it to never expire.
3. **Create a Zabbix Host** without interfaces. **Assign the 'UniFi Network API' template**
        Macros 
        **Modify '{$UNIFI_NETWORK_API_ADDRESS}'**
        **Modify '{$UNIFI_NETWORK_API_KEY}'**
        **Modify '{$SITE_LABEL}'** (Site name for single or multi-site)

> [!NOTE]
> Update intervals, Triggers, History and Treands retantions can be personalized using 'Inherited and host macros'.

> [!WARNING]
> '{$UNIFI_NETWORK_API_ADDRESS}' Macros must contain only IP or DNS name.
> '{$SITE_LABEL}' Must be set with your site name, if blank, only 1 site (default) is permitted.

## Contribute

This template is on early stage and can bee improved. Feel free to fork and submit pull request. 🙏🏻

## License

Licensed under the [MIT license](https://github.com/MassimilianoPasquini97/zbx_unifi_network_api/blob/main/LICENSE.md).
