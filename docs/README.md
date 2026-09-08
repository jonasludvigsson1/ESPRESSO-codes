# ESPRESSO Code Lists Repository

Centralized repository for standardized medical coding systems used in the ESPRESSO research program.

## Overview

This repository contains code lists for:
- **ICD Codes** (ICD-10, ICD-9, ICD-8, ICD-7) - Diagnosis classifications
- **ATC Codes** - Medication classifications
- **Histology Codes** - Pathological findings
- Additional coding systems (Cancer, Mortality, Surgical/Procedure codes, etc.)

All code lists are available in multiple formats (CSV, JSON) and displayed on a searchable GitHub Pages website.

## Repository Structure

```
ESPRESSO-codes/
│
├── README.md                          # This file
├── docs/                              # GitHub Pages files
│   └── index.html                     # Main code list viewer
│
├── code_lists/                        # CSV format code lists
│   ├── icd_codes.csv                  # ICD diagnosis codes
│   ├── atc_codes.csv                  # ATC medication codes
│   ├── histology_codes.csv            # Histology pathology codes
│   ├── cancer_codes.csv               # Cancer diagnoses
│   ├── mortality_codes.csv            # Mortality classifications
│   ├── surgical_codes.csv             # Surgical procedure codes
│   └── procedure_codes_nonsurgical.csv # Non-surgical procedure codes
│
├── data_json/                         # JSON format (for programmatic access)
│   ├── icd_codes.json
│   ├── atc_codes.json
│   ├── histology_codes.json
│   └── ...
│
├── data_original/                     # Original Excel master files
│   └── ICD_diagnoses_soderling_2015.xlsx
│
└── CONTRIBUTING.md                    # Guidelines for contributions
```

## Quick Start

### 1. View Code Lists Online

Visit the GitHub Pages site: **[https://yourusername.github.io/ESPRESSO-codes](https://yourusername.github.io/ESPRESSO-codes)**

Features:
- **Search** across all code lists
- **Tab navigation** between code systems
- **Copy-friendly** format for codes
- **Responsive design** works on desktop and mobile

### 2. Download CSV Files

Clone the repository or download individual CSV files from `/code_lists/`:

```bash
git clone https://github.com/yourusername/ESPRESSO-codes.git
cd ESPRESSO-codes
```

CSV files can be opened in Excel, R, Python, or any data analysis tool.

### 3. Access JSON Format

For programmatic access, use the JSON files in `/data_json/`:

```python
import json

with open('data_json/icd_codes.json', 'r') as f:
    icd_data = json.load(f)
```

```r
library(jsonlite)
icd_data <- fromJSON("data_json/icd_codes.json")
```

## File Formats

### CSV (Comma-Separated Values)
- **Use case**: Spreadsheet analysis, general compatibility
- **Access**: Directly open in Excel, Google Sheets, or data analysis tools
- **Viewing**: Click any CSV file on GitHub to see formatted table

### JSON (JavaScript Object Notation)
- **Use case**: Programmatic access, web applications
- **Access**: Parse with JSON libraries in Python, R, JavaScript, etc.
- **Structure**: Hierarchical with metadata and code entries

### Excel (Master Files)
- **Use case**: Internal reference, original data source
- **Location**: `/data_original/`
- **Note**: Primary updates should be made here, then exported to CSV/JSON

## Code List Details

### ICD Codes (`icd_codes.csv`)

| Column | Description |
|--------|-------------|
| diagnosis | Full diagnosis name (English/Swedish) |
| abbreviation | Standard abbreviation (IBD, CD, UC, etc.) |
| icd_10 | ICD-10 code(s) |
| icd_9 | ICD-9 code(s) |
| icd_8 | ICD-8 code(s) |
| icd_7 | ICD-7 code(s) |
| classification | Montreal/Paris classification or other system |
| notes | Additional explanatory notes |

**Example:**
```
Crohn's Disease,CD,K50*,555*,563.00,572.00-572.09,L-class,
```

### ATC Codes (`atc_codes.csv`)

| Column | Description |
|--------|-------------|
| drug_group | Therapeutic category (e.g., IBD-läkemedel) |
| drug_family | Drug family (e.g., Aminosalicylates) |
| drug_name | Generic drug name |
| atc | ATC classification code |
| trade_names | Commercial/brand names |
| pediatric_flare_dose | Recommended dose for pediatric flare |
| pediatric_maintenance_dose | Recommended maintenance dose |

**Example:**
```
IBD-läkemedel,Aminosalicylates,Mesalazine,A07EC02,"Asacol, Pentasa",,,
```

### Histology Codes (`histology_codes.csv`)

| Column | Description |
|--------|-------------|
| code | Standardized histology code |
| abbreviation | Short abbreviation |
| grade_name | Full name of grade/finding |
| description | Detailed description |
| applicable_to | Which conditions (IBD, Celiac, etc.) |
| severity_level | Severity classification |
| notes | Additional clinical notes |

**Example:**
```
H_VILL_SUB,VS,Villus atrophy subtotal,"Villus-to-crypt ratio <1:1",Celiac,Moderate,"Marsh grade 3"
```

## Contributing

We welcome contributions! Ways to help:

### 1. Report Errors
- Found an incorrect code? Open an Issue with:
  - Which code list
  - The error
  - The correction with source

### 2. Suggest New Codes
- Submit a Pull Request with new codes in CSV format
- Include description and references

### 3. Add New Code Systems
- Propose a new code system by opening an Issue
- Submit data in CSV format with proper metadata

### 4. Improve Documentation
- Suggest clarity improvements
- Add examples or use cases

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

## How to Edit and Update

### For GitHub Users (Recommended)

1. **Fork this repository**
   ```bash
   # On GitHub, click "Fork"
   ```

2. **Make changes locally**
   ```bash
   git clone https://github.com/yourusername/ESPRESSO-codes.git
   cd ESPRESSO-codes
   # Edit files in code_lists/
   ```

3. **Update JSON files** (if adding new codes)
   ```bash
   python3 csv_to_json.py  # Utility script (optional)
   ```

4. **Commit and push**
   ```bash
   git add code_lists/
   git commit -m "Add new histology codes for Marsh classification"
   git push origin main
   ```

5. **Submit Pull Request**
   - Go to GitHub and create a Pull Request
   - Describe changes clearly

### For Excel Users (Direct)

1. **Edit in Excel**
   - Open `/data_original/ICD_diagnoses_soderling_2015.xlsx`
   - Add/modify codes in the appropriate sheet

2. **Export to CSV**
   - Select sheet
   - Save As → CSV format
   - Replace corresponding file in `/code_lists/`

3. **Upload to GitHub**
   - Use GitHub's web interface to upload new files
   - Or commit via git

## Data Quality Standards

When adding or modifying codes, ensure:

- ✅ **Accuracy**: Verify against authoritative sources
- ✅ **Completeness**: All relevant fields filled
- ✅ **Consistency**: Follows existing naming/formatting conventions
- ✅ **Documentation**: Notes field explains any deviations or special cases
- ✅ **References**: Include sources for new classifications

## Citation

If you use these code lists in research, please cite:

```
ESPRESSO Code Lists. Available at: https://github.com/yourusername/ESPRESSO-codes
Ludvigsson, J. F., & ESPRESSO Collaborators. (2015). [Original reference for 2015 codes]
```

## Contact

- **Maintained by**: [Your Name / Jonas Ludvigsson]
- **GitHub Issues**: [Report issues here](https://github.com/yourusername/ESPRESSO-codes/issues)
- **Questions**: Create a Discussion or email: [contact@example.com]

## License

These code lists are provided for research and educational use.
[Specify your license: MIT, CC-BY, etc.]

## Version History

- **2024-09-08**: Initial repository setup with 10% samples
  - ICD codes (10 entries)
  - ATC codes (6 entries)
  - Histology codes (12 entries template)
  - GitHub Pages interface
  
- **Planned**: Full datasets and additional code systems

---

## Technical Notes

### Building the GitHub Pages Site

The site is automatically deployed from the `docs/` folder.

To test locally:
```bash
python3 -m http.server 8000
# Visit http://localhost:8000/docs/
```

### CSV to JSON Conversion

To regenerate JSON from CSV files:
```bash
python3 scripts/csv_to_json.py
```

### Searching the Site

The web interface includes:
- Full-text search across all code lists
- Tab navigation
- Responsive design
- Mobile-friendly display

---

## FAQ

**Q: Can I use these codes commercially?**  
A: See LICENSE file for terms of use.

**Q: How often are these updated?**  
A: Code lists are versioned. Check the "Version History" section above.

**Q: What if I find an error?**  
A: Please open an Issue on GitHub with details and sources.

**Q: Can I embed these code lists on my site?**  
A: The data is available under the specified license. See terms for reuse.

**Q: How do I suggest a new code system?**  
A: Open an Issue with the code system details and we'll discuss inclusion.

---

*Last Updated: 2024-09-08*  
*Repository: https://github.com/yourusername/ESPRESSO-codes*
