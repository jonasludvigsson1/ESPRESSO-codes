# Colorectal polyp precursor classification in ESPRESSO

SNOMED morphology codes and free-text term used to classify colorectal polyps (normal mucosa, tubular, tubulovillous and villous adenoma, hyperplastic polyp, sessile serrated polyp).

**Version:** 2026-11-23
**Source:** ESPRESSO Study; Polyp_ESPRSSO_23Nov_2026.xlsx

Machine-readable versions: `code_lists/colorectal_polyp_precursor_codes.csv` (codes), `code_lists/colorectal_polyp_precursor_codes_notes.csv` (notes) and `data_json/colorectal_polyp_precursor_codes.json` (both).

## Codes

Codes are listed per histological subtype. The column "Notes" refers to the legend below.

| Histological subtype | Type | Code or term | Label (Swedish SNOMED list) | Variant | Notes |
|---|---|---|---|---|---|
| Normal mucosa | SNOMED | M00100 | NORMAL MAKR MORF | main | N0, N5 |
| Normal mucosa | SNOMED | M00110 | NORMAL MIKR MORF | main | - |
| Tubular adenoma | SNOMED | M82100 | ADENOM TUBULÄRT (ADENOMATÖS POLYP) | main | - |
| Tubulovillous adenoma | SNOMED | M82630 | ADENOM TUBULOVILLÖST | main | - |
| Villous adenoma | SNOMED | M82611 | ADENOM VILLÖST | main | - |
| Hyperplastic polyp | SNOMED | M72040 | HYPERPLASI POLYPOID | main | - |
| Sessile serrated polyp (Morphology code) | SNOMED | M82160 | - | main | N4, N6 |
| Sessile serrated polyp (Morphology code) | SNOMED | M82130 | - | main | N1, N4, N6 |
| Sessile serrated polyp (Morphology code) | SNOMED | M72041 | - | conditional | N2, N4 |
| Sessile serrated polyp (Free text) | free text | gtand[ad] | - | main | N3 |

## Legend: notes and comments

"source" = comment taken from the source document; "curator" = added when the list was prepared for this repository.

| Note | Type | Text |
|---|---|---|
| N0 | source | Table "Polyp Classification in ESPRESSO" (histological subtype, SNOMED M code, free text), version of 2026-11-23. |
| N1 | source | M82130 may capture traditional serrated adenoma for a small group of people. |
| N2 | source | M72041 is used only if the code has been reported from Medilab. |
| N3 | curator | The free-text term is given exactly as in the source. It is probably a word stem for the Swedish "sågtandad" (serrated), and the brackets [ad] probably denote alternative word endings; confirm the exact search pattern before use. |
| N4 | curator | Labels come from the Swedish SNOMED list (SymPathy, 2007). M82160, M82130 and M72041 are not in that list, so no label is given. |
| N5 | curator | The source does not state a topography. Earlier ESPRESSO serrated-polyp analyses combined these morphology codes with colon and rectum (T67-T68); confirm for each study. |
| N6 | curator | An earlier annotated version (2026-11-18) described M82160 as traditional serrated adenoma in one IBD dysplasia study, whereas this table lists M82160 under sessile serrated polyp and flags M82130 as possibly capturing traditional serrated adenoma. Decide the intended meaning of each code before use. |
