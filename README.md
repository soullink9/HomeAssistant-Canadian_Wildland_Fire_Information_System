# Disclosure

This project was primarily created for personal use and for my family. While I may provide updates, they are not guaranteed. However, if you've stumbled upon this and find it interesting, feel free to download and use it. I had a great time building this and hope you enjoy it.

Note: Built with the assistance of Claude.ai. I’m putting it here now so you don't have to hunt for it below.

# Canadian Wildland Fire Information System (CWFIS)

Canada's national wildfire data in Home Assistant. See the national fire summary, every active fire on a map, how close fires are to you, and whether their smoke is likely to reach you. You don't need to live in Canada: smoke from Canadian fires regularly reaches the northern United States, which is why this was built.

[![Open your Home Assistant instance and open this repository in HACS.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=soullink9&repository=HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-&category=integration)
[![Open your Home Assistant instance and start setting up CWFIS.](https://my.home-assistant.io/badges/config_flow_start.svg)](https://my.home-assistant.io/redirect/config_flow_start/?domain=cwfis)

- The **national summary**, matching the CWFIS homepage: fires reported today, active, out, total and area burned this season.
- **This season against last year**, at exactly the same point in the season.
- A **per-province breakdown**, with optional sensors for the provinces you care about.
- **How close fires are** to Home and to any other zones you pick (a cottage, family, a trip): the nearest fire, fires inside your alert radius, satellite hotspots and fire perimeters, prescribed burns and the local fire danger.
- **Fire alerts**: a new fire near you, a change in its stage of control, a big jump in size, or a fire declared out.
- **Smoke**: a 24- and 48-hour PM2.5 forecast for Home, a **fire upwind** check using your own wind sensor, and a **wildfire smoke** check using your own air-quality sensor.
- **Maps**: a marker for every active fire on Home Assistant's built-in Map card, plus optional Canada-wide maps of fire danger, smoke and hotspots.
- Setup and settings are done entirely in the UI, with no YAML, API keys or extra packages.

Everything appears on a single **CWFIS** device, ready for dashboards, automations and notifications. This is a hobby project, not an emergency alert system. For evacuations and safety decisions, always follow your local authorities.

## Install

**Needs:** Home Assistant 2026.3 or newer.

1. **Download.** Use the HACS button above, or copy `custom_components/cwfis` into your `config/custom_components` folder. Then restart Home Assistant.
2. **Add the integration.** Go to Settings → Devices & services → Add integration → **Canadian Wildland Fire Information System**. It takes one click and uses your Home location.
3. **Configure.** Open the integration and choose **Configure** to set your alert and smoke radius, extra zones, your wind and PM2.5 sensors, provinces and maps. The [Settings](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/Settings) page helps you pick sensible distances.

## Documentation

The wiki has everything else:

| Page | What's in it |
|---|---|
| [Installation](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/Installation) | Installing with HACS or by hand, updating and removing |
| [Settings](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/Settings) | Every option on the Configure form, and how to choose your radii |
| [Entities](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/Entities) | Every sensor, binary sensor, event, map marker and map image |
| [Dashboards and Automations](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/Dashboards-and-Automations) | Ready-made cards and alert notifications |
| [How the Numbers Work](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/How-the-Numbers-Work) | Where each number comes from, season rules, smoke and wind |
| [Troubleshooting](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/Troubleshooting) | Debug logging, "Unknown" sensors and known issues |
| [Privacy](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/Privacy) | Exactly what is sent over the internet, and to whom |
| [Development](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/Development) | How the code is laid out and how it works inside |

## Privacy

There are no accounts, API keys or tracking. The integration only contacts Natural Resources Canada's fire data servers and Open-Meteo's air-quality forecast. To work out distances and the forecast, it sends the approximate coordinates of Home and your watch zones. The [Privacy](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/wiki/Privacy) page lists every request.

## Contributing

Bug reports and pull requests are welcome: [open an issue](https://github.com/soullink9/HomeAssistant-Canadian_Wildland_Fire_Information_System_-CWFIS-/issues). [CONTRIBUTING.md](CONTRIBUTING.md) explains where things live, how to check a change and how to release one.

## Credits

Code from other people in this project:

- None. The integration follows the patterns in the [Home Assistant developer documentation](https://developers.home-assistant.io/) and uses Home Assistant's built-in helpers.

Data this project uses:

- **Canadian Wildland Fire Information System (CWFIS)** and the **Canadian Wildland Fire Information Framework (CWFIF)**, from Natural Resources Canada, Canadian Forest Service. It provides reported and prescribed fires, hotspots, fire perimeters, fire danger and map images. *Contains information licensed under the [Open Government Licence – Canada](https://open.canada.ca/en/open-government-licence-canada).*
- **[Open-Meteo](https://open-meteo.com/)**, which provides the air-quality forecast, licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Its forecast comes from the **Copernicus Atmosphere Monitoring Service (CAMS)** and was generated using Copernicus Atmosphere Monitoring Service information.

This project is not affiliated with or endorsed by the Government of Canada, Natural Resources Canada, Open-Meteo or ECMWF. The icon is original artwork made for this project.

Everything else was written for this project, with help from Claude, Anthropic's AI model.

## License

[MIT License](LICENSE). You may use, copy, change and share this integration freely, as long as you keep the copyright notice. The data it retrieves stays under its providers' licences, listed above.
