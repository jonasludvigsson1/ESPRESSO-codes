# MALO (major adverse liver outcome) definition in ESPRESSO

Five-point composite: the first occurrence of any of compensated cirrhosis, decompensated cirrhosis, hepatocellular carcinoma, liver transplantation or liver-related death. Components 4 and 5 are defined in the separate liver_transplant and liver_related_death code lists.

**Version:** 2026-11-18
**Source:** ESPRESSO Study; MALO_definitions_ESPRESSO_261118.docx

Machine-readable versions: `code_lists/malo_codes.csv` (codes), `code_lists/malo_codes_notes.csv` (notes) and `data_json/malo_codes.json` (both).

## Codes

Codes are listed per component. The column "Notes" refers to the legend below.

### Compensated cirrhosis

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| Cirrhosis | 581 | 571,00, 571,9 | 571C, 571F | K70.3, K71.7, K74, K74.5, K74.6 | - | Patient Register | main | M8, M9, M11 |
| Non-bleeding varices | 462,10 | 456,00 | 456B | I85.9, I98.2, I86.4 (gastric varices) | - | Patient Register | main | M2, M11 |
| Portal hypertension | - | 571,9 | 572D | K76.6 | - | Patient Register | main | M3, M8, M11 |

### Decompensated cirrhosis

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| Variceal bleeding | - | - | 456A | I85.0, I98.3 | - | Patient Register | main | M2, M11 |
| Ascites | 785,39 | 785,30 | 789F | R18 | - | Patient Register | main | M7, M11 |
| Hepatic encephalopathy | - | 573,02 | 572C | K72.1, K72.9 | - | Patient Register | main | M10, M11 |
| Hepatorenal syndrome | - | - | 572E | K76.7 | - | Patient Register | main | M4, M11 |

### Hepatocellular carcinoma

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| HCC | 155,0 | 155,0 | 155A | C22.0 | - | Patient Register | main | M11, M12 |

### Liver transplantation

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| See liver_transplant code list | - | - | - | - | liver_transplant | Patient Register | main | M5 |

### Liver-related death

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| See liver_related_death code list | - | - | - | - | liver_related_death | Cause of Death Register | main | M6 |

## Legend: notes and comments

"source" = comment taken from the source document; "curator" = added when the list was prepared for this repository.

| Note | Type | Text |
|---|---|---|
| M0 | source | Definition agreed in discussion with Juan Vaz and Fahim Ebrahimi, 2026-11-18. |
| M1 | source | Compared with Yao et al (PMID 40093397): compensated and decompensated cirrhosis are separate events; non-bleeding varices count as compensated cirrhosis; liver failure and portal hypertension are no longer part of decompensation (portal hypertension is now under compensated cirrhosis). |
| M2 | source | ICD-7 (462,10) and ICD-8 (456,00) have a single code for esophageal varices without a distinction between bleeding and non-bleeding, so bleeding cannot be separated before ICD-9. These codes are counted as non-bleeding. |
| M3 | source | No specific ICD-7 code exists for portal hypertension. |
| M4 | source | There is no specific code for hepatorenal syndrome in ICD-7 or ICD-8. |
| M5 | source | Liver transplantation: see the separate liver_transplant code list. |
| M6 | source | Liver-related death: see the separate liver_related_death code list. Any of the codes in components 1-4 also count when listed as underlying cause of death. Only the underlying cause of death counts. |
| M7 | curator | ICD-8 ascites is 785,30 (the source document wrote 785,3; corrected 2026-11-18 on the code-owner's instruction). |
| M8 | curator | ICD-8 571,9 is listed in the source under both cirrhosis and portal hypertension. It is one code; it is kept under both components, so a hit counts as compensated cirrhosis either way. |
| M9 | curator | ICD-10 K74 is given as a whole category in the source and therefore also contains K74.0-K74.2 (fibrosis), K74.3 (primary biliary cirrhosis, which does not imply cirrhosis), K74.4, K74.5 and K74.6. K74.5 and K74.6 are also listed separately in the source, which is redundant. Decide whether the full K74 is intended. |
| M10 | curator | ICD-10 K72 (hepatic encephalopathy codes K72.1 and K72.9) is also the liver failure code, so counting encephalopathy by K72 captures liver failure as well. K72.0 is not listed in the source. |
| M11 | curator | The source does not state the register for components 1-4; the Patient Register is assumed. Liver-related death uses the Cause of Death Register. |
| M12 | curator | ICD-9 155A is the Swedish format used in the Patient Register. The Cause of Death Register uses the international ICD-9 (155.0, most often recorded as 1550). See the liver_related_death code list. |
