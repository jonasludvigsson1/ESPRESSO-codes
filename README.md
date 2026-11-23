This file contains codes to use in ESPRESSO studies.

## Liver outcome definitions (2026-11-18)

- MALO (major adverse liver outcome): `code_lists/malo_codes.csv`, `data_json/malo_codes.json`, `docs/malo_definition.md`
- Liver transplantation: `code_lists/liver_transplant_codes.csv`, `data_json/liver_transplant_codes.json`, `docs/liver_transplant_definition.md`
- Liver-related death: `code_lists/liver_related_death_codes.csv`, `data_json/liver_related_death_codes.json`, `docs/liver_related_death_definition.md`

Comments are kept out of the code rows: each code row has a `note_ids` column that points to the legend (`*_notes.csv`, the `notes` array in the JSON, and the legend table at the bottom of each `docs/*_definition.md`).

## Colorectal polyp precursor classification (2026-11-23)

- Polyp classification (normal mucosa, tubular, tubulovillous and villous adenoma, hyperplastic polyp, sessile serrated polyp): `code_lists/colorectal_polyp_precursor_codes.csv`, `data_json/colorectal_polyp_precursor_codes.json`, `docs/colorectal_polyp_precursor_definition.md`
- Notes legend: `code_lists/colorectal_polyp_precursor_codes_notes.csv`
