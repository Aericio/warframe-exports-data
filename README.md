# warframe-exports-data [![](https://data.jsdelivr.com/v1/package/gh/aericio/warframe-exports-data/badge)](https://www.jsdelivr.com/package/gh/aericio/warframe-exports-data)

This repository utilizes [warframe-exports-rust](https://github.com/Aericio/warframe-exports-rust), a Rust-based tool for downloading Warframe public export data, like manifests and images, from the Warframe content server. Updates are checked hourly on weekdays.

All exported content is provided as-is, if possible, from the content server. Modifications are listed below:
- `Export*.json` files contain text that include control characters (`\r`, `\n`), and are escaped during pre-processing.
- All images are flattened to the `/image` directory, and use their `unique_name` as the file name with `/` replaced with `.`.

You can access resources from this repository via jsDelivr's CDN, for example:
- `https://cdn.jsdelivr.net/gh/Aericio/warframe-exports-data/image/Lotus.Types.Items.MiscItems.Salvage.png`

This repository serves as the new data source for [Paroxity/FrameHub](https://github.com/Paroxity/FrameHub), superseding [WFCD/warframe-items](https://github.com/WFCD/warframe-items).

## Content Disclosure
> All content retrieved in this repository is the property of Digital Extremes, Ltd.. warframe-exports-data is an independent project and is not affiliated with or endorsed by Digital Extremes, Ltd. or Warframe. This repository functions as a read-only mirror of Warframe’s publicly available export data.
