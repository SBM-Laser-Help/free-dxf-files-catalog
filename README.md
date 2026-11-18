# Free DXF files for laser cutting: catalog

Catalog of 4,480 free DXF drawings for laser, plasma and waterjet cutting in 25 categories: wall art, patterns and ornaments, screen panels, 3D puzzles, signs, boxes, BBQ braziers, fire pit bowls, clocks, lamps, maps, letters and more. Names in 12 languages, cut length and number of pierces for each drawing, a preview image and a link to its page on [sbmlaserhelp.com](https://sbmlaserhelp.com/dxf/).

This repository holds the catalog only, not the drawings. The DXF files themselves are free to download in the [SBM Laser Help](https://sbmlaserhelp.com/dxf/) app (web, Android, iOS, Telegram) with a free account.

Also on Hugging Face: [SBMLaserHelp/free-dxf-files-catalog](https://huggingface.co/datasets/SBMLaserHelp/free-dxf-files-catalog).

## Files

| File | Format |
|---|---|
| `data/free-dxf-files-catalog.csv` | CSV, UTF-8, comma-separated, header row |
| `data/free-dxf-files-catalog.jsonl` | JSON Lines, one object per drawing |

## Columns

| Column | Meaning |
|---|---|
| `id` | Stable id, `<category>/<drawing>` |
| `category` | Category id |
| `category_name` | Category name in English |
| `name_en`, `name_ru`, `name_pt_br`, `name_es`, `name_de`, `name_fr`, `name_it`, `name_pl`, `name_tr`, `name_ar`, `name_hi`, `name_uz` | Drawing name in 12 languages |
| `cut_length_m` | Total cut length, m (rounded) |
| `pierces` | Number of pierces (closed contours) |
| `preview_url` | Preview image of the drawing |
| `page_url` | Page of the drawing on sbmlaserhelp.com, or its category page if the drawing has no page yet |

Cut length and pierces help estimate cutting time and cost before you open the file.

## Example

```python
import pandas as pd

df = pd.read_csv("data/free-dxf-files-catalog.csv")
braziers = df[df.category == "mangaly-s"].sort_values("pierces")
print(braziers[["name_en", "cut_length_m", "pierces", "page_url"]].head(10))
```

## License

The catalog (names, categories, measurements) is released under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE). Attribution:

> Free DXF files catalog, SBM Laser Help, https://sbmlaserhelp.com/dxf/

The license covers this catalog only. It does not cover the drawings or the preview images; those stay on sbmlaserhelp.com and in the app.

## About

[SBM Laser Help](https://sbmlaserhelp.com/) is a helper for fiber laser cutting operators: cutting parameter tables, cut defect diagnosis from a photo, machine and chiller error codes, calculators and this DXF library. Web, Android, iOS and Telegram, 12 languages. Open cutting parameters: [SBM-Laser-Help/laser-cutting-parameters](https://github.com/SBM-Laser-Help/laser-cutting-parameters).
