# Liver transplantation definition in ESPRESSO

Codes identifying liver transplantation (component 4 of MALO).

**Version:** 2026-11-18
**Source:** ESPRESSO Study; liver_transplant_definition_261118.docx

Machine-readable versions: `code_lists/liver_transplant_codes.csv` (codes), `code_lists/liver_transplant_codes_notes.csv` (notes) and `data_json/liver_transplant_codes.json` (both).

## Codes

Codes are listed per component. The column "Notes" refers to the legend below.

### Liver transplantation

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| Status/complication code | - | - | V42H (liver transplant status) | Z94.4 (liver transplant status), T86.4 (liver transplant failure and rejection) | - | Patient Register | main | T1, T3 |
| Procedure | - | - | - | - | 5200, JJC, DJ005, DJ006 | Patient Register | main | T2 |

## Legend: notes and comments

"source" = comment taken from the source document; "curator" = added when the list was prepared for this repository.

| Note | Type | Text |
|---|---|---|
| T0 | source | Definition agreed in discussion with Juan Vaz and Fahim Ebrahimi, 2026-11-18. |
| T1 | source | There is no ICD-7 or ICD-8 code for liver transplantation. |
| T2 | curator | The classification system of the procedure codes 5200, JJC, DJ005 and DJ006 is not stated in the source document; confirm it (for example Swedish operation/KVÅ codes) before use. |
| T3 | curator | ICD-9 V42H and ICD-10 Z94.4 describe transplant status and T86.4 describes transplant failure and rejection, so these can be recorded after the transplantation date. The procedure codes are the more reliable marker of the date. |
