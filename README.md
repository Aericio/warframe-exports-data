# warframe-exports-data [![](https://data.jsdelivr.com/v1/package/gh/aericio/warframe-exports-data/badge)](https://www.jsdelivr.com/package/gh/aericio/warframe-exports-data)

This repository utilizes [warframe-exports-rust](https://github.com/Aericio/warframe-exports-rust), a Rust-based tool for downloading Warframe public export data, like manifests and images, from the Warframe content server. Updates are checked hourly on weekdays.

All exported content is provided as-is, if possible, from the content server. Modifications are listed below:
- `Export*.json` / `Export*.min.json` files contain text that include control characters (`\r`, `\n`), and are escaped during pre-processing.
- All images are flattened to the `/image` directory, and use their `unique_name` as the file name with `/` replaced with `.`.
- Downscaled versions of each image are stored in subfolders within `/image`, in the sizes `256x256`, `128x128`, `64x64`, and `32x32`.
  - Images in the root `/image` directory are rescaled to 512x512, if needed, for consistency; some images were originally smaller (e.g. `128x128`) or larger (e.g. `2048x2048`).
  - Scaling is performed using Lancozs3 interpolation.

You can access resources from this repository via jsDelivr's CDN, for example:
- `https://cdn.jsdelivr.net/gh/Aericio/warframe-exports-data/image/Lotus.Types.Items.MiscItems.Salvage.png`

This repository serves as the new data source for [Paroxity/FrameHub](https://github.com/Paroxity/FrameHub), superseding [WFCD/warframe-items](https://github.com/WFCD/warframe-items).

## Outputs
```
output/
├── export/
│   ├── ExportCustoms_en.json
│   ├── ExportCustoms_en.min.json
│   ├── ExportDrones_en.json
│   ├── ExportDrones_en.min.json
│   └── ...
├── image/
│   ├── Lotus.Characters.Tenno.Accessory.Scarves.GrnBannerScarf.GrnBannerScarfItem.png
│   ├── Lotus.Characters.Tenno.Accessory.Scarves.PrimeScarfD.Cloth.PrimeScarfDItem.png
│   ├── 256x256/
│   │   ├── Lotus.Characters.Tenno.Accessory.Scarves.GrnBannerScarf.GrnBannerScarfItem.png
│   │   └── ...
│   ├── 128x128/
│   │   └── ...
│   ├── 64x64/
│   │   └── ...
│   └── 32x32/
│       └── ...
├── export_hash.json
└── image_hash.json
```

## Content Disclosure
> All content retrieved in this repository is the property of Digital Extremes, Ltd.. warframe-exports-data is an independent project and is not affiliated with or endorsed by Digital Extremes, Ltd. or Warframe. This repository functions as a read-only mirror of Warframe’s publicly available export data.
