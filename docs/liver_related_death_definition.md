# Liver-related death definition in ESPRESSO

Proposed code list for liver-related death (underlying cause of death), component 5 of MALO.

**Version:** 2026-11-18
**Source:** ESPRESSO Study; liver_related_deaths_definition_261118.docx

Machine-readable versions: `code_lists/liver_related_death_codes.csv` (codes), `code_lists/liver_related_death_codes_notes.csv` (notes) and `data_json/liver_related_death_codes.json` (both).

## Codes

Codes are listed per component. The column "Notes" refers to the legend below.

### Viral hepatitis

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| - | 092 | 070 | 070 | B15, B16, B17, B18, B19 | - | Cause of Death Register (underlying cause) | main | D1 |

### Primary liver tumours

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| - | 155,0 (liver, primary) | 155,0 | 155.0 (liver, primary), 155.1 (intrahepatic bile ducts), 155.2 (liver, not stated as primary or secondary) | C22 | - | Cause of Death Register (underlying cause) | main | D1 |

### Alcoholic and toxic liver disease, cirrhosis of various forms, liver failure, and other liver disease

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| - | 580, 581, 582, 583 | 570, 571, 572, 573 | 570, 571, 572, 573 | K70, K71, K72, K73, K74, K75, K76, K77 | - | Cause of Death Register (underlying cause) | main | D1, D7, D8 |

### Complications of cirrhosis and portal hypertension

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| Varices | 462,10 | 456,00 | 456.0, 456.1 | I85, I86.4 (gastric varices), I98.2 (esophageal varices), I98.3 (esophageal varices) | - | Cause of Death Register (underlying cause) | main | D1 |
| Ascites | 785,39 | 785,30 | 789.5 | R18 | - | Cause of Death Register (underlying cause) | main | D1, D9 |
| Cirrhosis with portal hypertension | - | 571,90 | - | - | - | Cause of Death Register (underlying cause) | main | D1, D9 |
| Hepatic coma | - | 573,02 | - | - | - | Cause of Death Register (underlying cause) | main | D1, D9 |

### Cholangitis, including PSC

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| - | 585,29 | 575,05 | 576.1 | K83.0 (cholangitis, includes sclerosing cholangitis) | - | Cause of Death Register (underlying cause) | main | D1, D6 |

### Metabolic liver disease

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| - | - | 273,20 (haemochromatosis), 273,30 (Wilson disease) | 275.0 (iron metabolism), 275.1 (copper metabolism) | E83.0 (Wilson disease), E83.1 (haemochromatosis), E88.0 (alpha-1-antitrypsin deficiency) | - | Cause of Death Register (underlying cause) | optional | D1, D5 |

### Not included

| Sub-group | ICD-7 | ICD-8 | ICD-9 | ICD-10 | Other | Register | Variant | Notes |
|---|---|---|---|---|---|---|---|---|
| - | - | - | - | C78.7 (secondary liver tumours), K80-K82 (gallbladder and bile duct disease), K83.1-K83.9 (gallbladder and bile duct disease), R16 (hepatomegaly (symptom)), R17 (jaundice (symptom)) | - | Cause of Death Register (underlying cause) | main, not_included | D4 |

## Legend: notes and comments

"source" = comment taken from the source document; "curator" = added when the list was prepared for this repository.

| Note | Type | Text |
|---|---|---|
| D0 | source | Definition agreed in discussion with Juan Vaz and Fahim Ebrahimi, 2026-11-18. |
| D1 | source | The Cause of Death Register uses the international ICD-9, so 155A (liver cancer) is recorded as 155.0 (or most often 1550). ICD-9 codes in this list are therefore written in the international format. |
| D2 | source | In a sensitivity analysis, consider also using secondary causes of death with a liver-related diagnosis. |
| D3 | source | Liver-related death is also a component of MALO. |
| D4 | source | Not included: secondary liver tumours (ICD-10 C78.7), gallbladder and bile duct disease (K80-K82, K83.1-K83.9), and jaundice and hepatomegaly as symptoms (R16, R17). |
| D5 | source | Metabolic liver disease is optional (variant "optional"); the source lists no ICD-7 code for it. |
| D6 | source | ICD-10 K83.0 is described in the source as cholangitis, including sclerosing cholangitis (PSC). |
| D7 | curator | Ranges are written as in the source: the three-digit ICD-8 and ICD-9 categories 570-573 and the ICD-10 range K70-K77 stand for the whole category. ICD-10 K75, K76 and K77 appear in the source after a semicolon. |
| D8 | curator | The source table has two empty sub-rows ("Cirrhosis, fibrosis, biliary cirrhosis" and "Liver failure, hepatitis and other liver disease") under the alcoholic/toxic row, with no codes entered. They are not represented here. |
| D9 | curator | ICD-8 571,90 is cirrhosis with portal hypertension, ICD-8 573,02 hepatic coma, ICD-8 785,30 ascites (the same ICD-8 ascites code as in the MALO list). |
