# Velora Web Themes

Shared themes for the **Velora Web** ecosystem: **Velora Music**, **Velora Receipts**, **Velora Finance** and future Velora web applications.

All 47 themes live in this one repository. Each theme keeps its own folder, manifest, stable ID and version, so you can install or update one theme without the others. **Light, Dark and Device** remain built-in application choices.

The theme format is implemented in Velora Music today. Receipts, Finance and other web apps can reuse the same palettes by implementing [Velora Web theme API 1](THEME_API.md); their integration is independent of this repository.

## Install a theme

1. Download or clone this repository.
2. Choose a folder under **themes/**, for example **themes/terracotta/**.
3. Copy that folder to your application's theme plugin directory, keeping **velora-plugin.json** at the theme folder's root.
4. Restart the application and choose the theme in Settings.

In **Velora Music**, install under `<private-data>/plugins/themes/<id>/`. Docker uses `/var/lib/velora/private/plugins/themes/<id>/` on the persistent private-data volume. The application user (UID 10001 in Docker) must be able to read the files. Copy all folders under **themes/** to install the whole collection; do not nest the repository itself as a theme.

A valid installed theme with the same ID overrides its shipped copy. Removing the installed copy and restarting restores the shipped version. Updates are explicit folder replacements; there is no automatic GitHub download or in-app installer yet.

## Themes

| Theme | Appearance | Version |
| --- | --- | --- |
| [Amethyst](themes/amethyst/) | Dark | 1.0.0 |
| [Apricot](themes/apricot/) | Light | 1.0.0 |
| [Arctic](themes/arctic/) | Light | 1.0.0 |
| [Aubergine](themes/aubergine/) | Dark | 1.0.0 |
| [Aurora](themes/aurora/) | Dark | 1.0.0 |
| [Blue Hour](themes/blue-hour/) | Dark | 1.0.0 |
| [Bordeaux](themes/bordeaux/) | Dark | 1.0.0 |
| [Breeze](themes/breeze/) | Light | 1.0.0 |
| [Buttercup](themes/buttercup/) | Light | 1.0.0 |
| [Cherry Blossom](themes/cherry-blossom/) | Light | 1.0.0 |
| [Christmas](themes/christmas/) | Dark | 1.0.0 |
| [Cobalt](themes/cobalt/) | Dark | 1.0.0 |
| [Copper](themes/copper/) | Dark | 1.0.0 |
| [Crimson](themes/crimson/) | Dark | 1.0.0 |
| [Deep Sea](themes/deep-sea/) | Dark | 1.0.0 |
| [Ember](themes/ember/) | Dark | 1.0.0 |
| [Espresso](themes/espresso/) | Dark | 1.0.0 |
| [Forest](themes/forest/) | Dark | 1.0.0 |
| [Garnet](themes/garnet/) | Dark | 1.0.0 |
| [Graphite](themes/graphite/) | Dark | 1.0.0 |
| [Harbor](themes/harbor/) | Dark | 1.0.0 |
| [Honey](themes/honey/) | Light | 1.0.0 |
| [Ink](themes/ink/) | Dark | 1.0.0 |
| [Lavender](themes/lavender/) | Light | 1.0.0 |
| [Linen](themes/linen/) | Light | 1.0.0 |
| [Marshmallow](themes/marshmallow/) | Light | 1.0.0 |
| [Matcha](themes/matcha/) | Light | 1.0.0 |
| [Midnight](themes/midnight/) | Dark | 1.0.0 |
| [Midnight Gold](themes/midnight-gold/) | Dark | 1.0.0 |
| [Monochrome](themes/monochrome/) | Dark | 1.0.0 |
| [Moonstone](themes/moonstone/) | Light | 1.0.0 |
| [Nordic](themes/nordic/) | Light | 1.0.0 |
| [Obsidian](themes/obsidian/) | Dark | 1.0.0 |
| [Ocean](themes/ocean/) | Dark | 1.0.0 |
| [Olive](themes/olive/) | Light | 1.0.0 |
| [Peach](themes/peach/) | Light | 1.0.0 |
| [Petrol](themes/petrol/) | Dark | 1.0.0 |
| [Plum](themes/plum/) | Dark | 1.0.0 |
| [Porcelain](themes/porcelain/) | Light | 1.0.0 |
| [Rosewood](themes/rosewood/) | Dark | 1.0.0 |
| [Ruby Night](themes/ruby-night/) | Dark | 1.0.0 |
| [Saffron](themes/saffron/) | Dark | 1.0.0 |
| [Sage](themes/sage/) | Light | 1.0.0 |
| [Sandstone](themes/sandstone/) | Light | 1.0.0 |
| [Sea Glass](themes/sea-glass/) | Light | 1.0.0 |
| [Slate](themes/slate/) | Dark | 1.0.0 |
| [Terracotta](themes/terracotta/) | Light | 1.0.0 |

## Create a theme

Copy an existing theme folder, assign a new ID and name, and adjust its colours and preview. Each folder contains **velora-plugin.json**, **README.md** and **LICENSE**. The README title follows **Terracotta for Velora Web**. See [THEME_API.md](THEME_API.md) for the manifest contract.

Themes contain colour data only. They do not execute code, load remote assets or change the application's layout or font selection.

## License

The existing license is retained in each theme's **LICENSE** file.
