# Porcelain for Velora Web

Cool white, porcelain grey and classic blue.

**Porcelain** is an independent theme in [Velora Web Themes](https://github.com/JROkkerman/Velora-Web-Themes). Version 1.0.0 uses Velora Web theme API 1. Its palette can be shared across compatible Velora web applications, including Music, Receipts and Finance, without depending on another theme.

## Install

Download or clone **Velora-Web-Themes**, then copy only the **themes/porcelain** folder into your application's **plugins/themes/porcelain** directory. Keep **velora-plugin.json** directly inside that folder. Do not copy the whole repository into a single theme directory.

In Velora Music, use the private-data directory's **plugins/themes/porcelain** folder, restart the application, and select **Porcelain** under Settings → Themes. In Docker the private-data directory is **/var/lib/velora/private**. Other Velora web apps need to implement theme API 1 and provide their own installation location.

An installed copy with the same ID overrides the shipped copy in Velora Music. Remove the installed folder and restart to return to the shipped version. Each theme can be updated independently.

## Customize

Edit [velora-plugin.json](velora-plugin.json). It declares the ID, version, API compatibility, colour scheme, colour tokens and preview. Values are hexadecimal colours; there are no scripts, raw CSS, remote assets or build steps. Keep the ID stable for updates; give a new theme its own ID and folder.

See [the shared theme API](../../THEME_API.md). Installation currently uses folder copying; an in-app GitHub installer is not included.

## License

See [LICENSE](LICENSE).
