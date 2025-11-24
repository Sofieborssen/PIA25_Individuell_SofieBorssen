# Guide: Pusha till GitHub

## 1. Verifiera att allt är klart

Kontrollera att du har alla filer:
- ✅ schema_pgadmin.sql
- ✅ testdata.sql
- ✅ queries.sql (10 queries)
- ✅ queries_advanced.sql (6 queries - VG)
- ✅ optimization.sql (VG)
- ✅ database.py
- ✅ models.py
- ✅ queries.py
- ✅ main.py
- ✅ requirements.txt
- ✅ README.md
- ✅ REPORT.md (VG)

## 2. Initiera Git (om inte redan gjort)

```bash
cd "/Users/sofieborssen/Documents/Electronic Shop/electronics_shop"
git init
```

## 3. Skapa .gitignore

Skapa en `.gitignore`-fil:

```
# Python
__pycache__/
*.py[cod]
*$py.class
*.so
.Python
.venv/
venv/
ENV/
env/

# VS Code
.vscode/
*.code-workspace

# macOS
.DS_Store

# Miljövariabler
.env
.env.local

# Databas
*.db
*.sqlite
```

## 4. Lägg till filer

```bash
git add .
git commit -m "Initial commit: Electronics Shop database project"
```

## 5. Skapa GitHub repository

1. Gå till GitHub.com
2. Klicka "New repository"
3. Namn: `PIA25_Individuell_[DittNamn]` (eller valfritt namn)
4. Välj "Private" eller "Public"
5. **INTE** skapa README, .gitignore eller license (vi har redan dessa)
6. Klicka "Create repository"

## 6. Koppla till GitHub

```bash
git remote add origin https://github.com/[ditt-användarnamn]/[repo-namn].git
git branch -M main
git push -u origin main
```

## 7. Om du vill ta bort gamla commits/filer

### Alternativ A: Rensa Git-historik (nytt repo från scratch)

Om du vill börja om med en ren historik:

```bash
# Ta bort .git-mappen
rm -rf .git

# Börja om
git init
git add .
git commit -m "Initial commit: Electronics Shop project"
git branch -M main
git remote add origin https://github.com/[användarnamn]/[repo-namn].git
git push -u origin main
```

### Alternativ B: Ta bort specifika filer från historik

Om du vill ta bort gamla filer men behålla historik:

```bash
# Ta bort filer från Git (men behåll lokalt)
git rm --cached [filnamn]

# Eller ta bort hela mappar
git rm -r --cached [mappnamn]

# Commita ändringarna
git commit -m "Remove old files"
git push
```

### Alternativ C: Force push (om du redan pushat)

**VARNING:** Detta skriver över GitHub-historiken!

```bash
# Börja om med ny commit
git checkout --orphan new-main
git add .
git commit -m "Initial commit: Electronics Shop project"
git branch -D main
git branch -m main
git push -f origin main
```

## 8. Verifiera på GitHub

1. Gå till ditt repository på GitHub
2. Kontrollera att alla filer finns
3. Kontrollera att README.md visas korrekt

## Tips

- **Använd .gitignore** för att undvika att committa onödiga filer
- **Commit ofta** med beskrivande meddelanden
- **Push regelbundet** för att säkerhetskopiera

## Felsökning

**Problem:** "remote origin already exists"
```bash
git remote remove origin
git remote add origin https://github.com/[användarnamn]/[repo-namn].git
```

**Problem:** "failed to push"
```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

