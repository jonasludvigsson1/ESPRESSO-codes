# ESPRESSO-codes Repository Setup Guide

Complete step-by-step instructions for setting up the ESPRESSO-codes repository structure on GitHub.

## Prerequisites

- ✅ GitHub account (you already have this)
- ✅ Git installed locally (or use GitHub web interface)
- ✅ Existing repo: `ESPRESSO-codes`

## Step 1: Create Folder Structure

Your repository should have this structure:

```
ESPRESSO-codes/
├── README.md
├── CONTRIBUTING.md
├── .gitignore
│
├── docs/
│   ├── index.html                    # GitHub Pages entry point
│   └── assets/
│       └── styles.css                # (Optional: separate CSS)
│
├── code_lists/
│   ├── histology_codes.csv           # ← START HERE (separate, as requested)
│   ├── icd_codes.csv
│   ├── atc_codes.csv
│   ├── cancer_codes.csv
│   ├── mortality_codes.csv
│   ├── surgical_codes.csv
│   └── procedure_codes_nonsurgical.csv
│
├── data_json/
│   ├── histology_codes.json
│   ├── icd_codes.json
│   ├── atc_codes.json
│   └── all_codes.json                # Combined reference
│
├── data_original/
│   └── ICD_diagnoses_soderling_2015.xlsx
│
└── scripts/ (optional)
    └── csv_to_json.py
```

## Step 2: Using GitHub Web Interface (Easiest)

### 2a. Create Folders

1. Go to your repo: `https://github.com/yourusername/ESPRESSO-codes`
2. Click **"Add file"** → **"Create new file"**
3. Type: `docs/index.html`
4. GitHub auto-creates the `docs/` folder
5. Paste the content from `index.html` (provided)
6. Click **"Commit new file"**

Repeat for:
- `code_lists/histology_codes.csv`
- `code_lists/icd_codes.csv`
- `code_lists/atc_codes.csv`
- `data_json/histology_codes.json`
- `data_json/icd_codes.json`
- `data_original/README.md` (just a note: "Original Excel files stored here")

### 2b. Upload Files Using GitHub Web

For larger files or multiple files:
1. Navigate to desired folder (e.g., `code_lists/`)
2. Click **"Add file"** → **"Upload files"**
3. Drag & drop CSV files
4. Click **"Commit changes"**

## Step 3: Using Git (Command Line)

```bash
# Clone your repository
git clone https://github.com/yourusername/ESPRESSO-codes.git
cd ESPRESSO-codes

# Create folder structure
mkdir -p docs code_lists data_json data_original scripts

# Copy files
cp index.html docs/
cp icd_codes_sample.csv code_lists/icd_codes.csv
cp atc_codes_sample.csv code_lists/atc_codes.csv
cp histology_codes_template.csv code_lists/histology_codes.csv
cp icd_codes_sample.json data_json/icd_codes.json
cp atc_codes_sample.json data_json/atc_codes.json

# Add .gitignore
cat > .gitignore << EOF
# OS files
.DS_Store
Thumbs.db

# Temporary files
*.tmp
*.bak
~*

# Python
__pycache__/
*.pyc

# Node (if used)
node_modules/
EOF

# Commit
git add .
git commit -m "Initial commit: code list structure with 10% samples"
git push origin main
```

## Step 4: Enable GitHub Pages

1. Go to repository settings: **Settings** tab
2. Scroll to **"Pages"** section (left sidebar)
3. Under **"Source"**, select:
   - Branch: `main` (or your default branch)
   - Folder: `/docs`
4. Click **"Save"**
5. GitHub will show: `Your site is published at https://yourusername.github.io/ESPRESSO-codes`

The site will be live within 1-2 minutes.

## Step 5: Verify Your Setup

✅ **Test each part:**

1. **GitHub Pages Working?**
   - Visit: `https://yourusername.github.io/ESPRESSO-codes`
   - Should see the blue/purple gradient interface

2. **CSV Files Readable?**
   - Navigate to: `https://github.com/yourusername/ESPRESSO-codes/blob/main/code_lists/histology_codes.csv`
   - Should see formatted table

3. **Search Function Working?**
   - On the GitHub Pages site, try searching for a code
   - Should filter results

## Step 6: Add Content (Going Forward)

### Adding New Codes

**Option A: Web Interface**
```
1. Go to code_lists/histology_codes.csv
2. Click "Edit" (pencil icon)
3. Add new row at bottom
4. Commit with message "Add histology code: H_xxx"
```

**Option B: Local Git**
```bash
# Edit CSV locally
nano code_lists/histology_codes.csv

# Add, commit, push
git add code_lists/histology_codes.csv
git commit -m "Add 5 new histology codes for Marsh grading"
git push origin main
```

### Updating JSON Files

If using JSON programmatically, update when adding codes:

**Python script to convert CSV → JSON:**
```python
# scripts/csv_to_json.py
import csv
import json

def csv_to_json(csv_file, json_file):
    data = []
    with open(csv_file, 'r', encoding='utf-8') as f:
        reader = csv.DictReader(f)
        for row in reader:
            data.append(row)
    
    with open(json_file, 'w', encoding='utf-8') as f:
        json.dump({
            "codes": data,
            "count": len(data)
        }, f, indent=2, ensure_ascii=False)

# Run for each code list
csv_to_json('code_lists/histology_codes.csv', 'data_json/histology_codes.json')
csv_to_json('code_lists/icd_codes.csv', 'data_json/icd_codes.json')
```

## Step 7: Protect Main Branch (Optional but Recommended)

1. Go to **Settings** → **Branches**
2. Add rule for `main` branch
3. Require pull request reviews
4. This prevents accidental direct pushes

## Step 8: Create CONTRIBUTING.md

File: `CONTRIBUTING.md`

```markdown
# Contributing to ESPRESSO Code Lists

## How to Contribute

### Small Updates (CSV only)
1. Fork the repo
2. Edit CSV files in `code_lists/`
3. Submit Pull Request

### New Code Systems
1. Prepare data in CSV format
2. Create new file: `code_lists/new_system.csv`
3. Optionally create JSON version
4. Submit Pull Request with description

### Reporting Issues
- Found an error? Open an Issue
- Include: which code, the error, the correction
- Provide source/reference if possible

## Code Quality

- Verify codes against official sources
- Use consistent formatting
- Include descriptions for non-obvious codes
- Test on the website before submitting

## Naming Conventions

- Files: lowercase_with_underscores.csv
- Codes: ALL_CAPS_SHORT (e.g., H_VILL_TOT)
- Columns: lowercase_with_underscores
```

## Step 9: Create .gitignore

```
# .gitignore file
*.xlsx~
*.xlsm
Thumbs.db
.DS_Store
~$*.xlsx
```

## Directory Checklist

- [ ] `docs/index.html` created
- [ ] `code_lists/histology_codes.csv` created (first, separate)
- [ ] `code_lists/icd_codes.csv` created
- [ ] `code_lists/atc_codes.csv` created
- [ ] `data_json/` folder with JSON files
- [ ] `data_original/` folder (can be empty or have README)
- [ ] `README.md` in root
- [ ] `CONTRIBUTING.md` in root
- [ ] `.gitignore` created
- [ ] GitHub Pages enabled (`/docs` source)
- [ ] Verified site is live at GitHub Pages URL

## Common Issues & Solutions

**Issue: Site not showing at GitHub Pages URL**
- Solution: Wait 2-3 minutes, then hard refresh (Ctrl+Shift+R)
- Check Settings → Pages to confirm `/docs` is selected

**Issue: CSV table not showing on GitHub**
- Solution: Make sure no commas in unquoted fields
- Verify UTF-8 encoding

**Issue: JSON import failing**
- Solution: Validate JSON syntax at jsonlint.com
- Ensure proper escaping of special characters

**Issue: Search not working on site**
- Solution: Check browser console (F12) for errors
- Verify JavaScript is enabled

## Next Steps

1. **After initial setup**: Add remaining code systems
2. **Establish workflow**: Decide on PR review process
3. **Version control**: Tag releases (e.g., v1.0.0)
4. **Documentation**: Create use-case examples for researchers

## Quick Links

- Your repo: `https://github.com/yourusername/ESPRESSO-codes`
- Your GitHub Pages site: `https://yourusername.github.io/ESPRESSO-codes`
- GitHub Docs on Pages: `https://docs.github.com/en/pages`

---

**Need help?** Open an issue in your repo or contact your ESPRESSO team leads.
