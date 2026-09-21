# Hedda_Wisingskolan
Detta är ett projekt att skapa ett plugin och lista för Hedda Wisingskolan


# Skolfilter - Chrome Extension

Webbfilter för skola med 66 253 blockerade domäner.
Kategorier: Spel, sociala medier, VPN/proxy, dynamisk DNS, bedrägerisajter.

## Extension ID
```
jamomeobfphlhfphbclfmclpmgphaabo
```
**Spara detta ID - ni behöver det i Google Admin.**

## Filer i detta repo
- `school-filter.crx` - Tillägget (signerat)
- `update.xml` - Uppdateringsfil som Google Admin pekar på
- `school-filter-key.pem` - ⚠️ LÄGG INTE UPP DENNA PÅ GITHUB - spara lokalt

---

## Steg 1: Ladda upp till GitHub

1. Skapa ett nytt **privat** eller publikt repo på GitHub (t.ex. `skolfilter`)
2. Ladda upp ENDAST dessa filer:
   - `school-filter.crx`
   - `update.xml`
3. Notera era GitHub-URL:er:
   - CRX: `https://raw.githubusercontent.com/ERAT-ANVANDARE/skolfilter/main/school-filter.crx`
   - Update: `https://raw.githubusercontent.com/ERAT-ANVANDARE/skolfilter/main/update.xml`

---

## Steg 2: Uppdatera update.xml med era riktiga URL:er

Ersätt i `update.xml`:
```
ERAT-GITHUB-ANVANDARE/ERAT-REPO-NAMN
```
Med ert riktiga GitHub-användarnamn och repo-namn.

---

## Steg 3: Konfigurera Google Admin

1. Gå till **admin.google.com**
2. Navigera till: **Devices → Chrome → Apps & extensions → Users & browsers**
3. Välj den OU som innehåller eleverna
4. Klicka **+** → **Add Chrome app or extension by ID**
5. Välj **"From a custom URL"**
6. Fyll i:
   - **Extension ID:** `jamomeobfphlhfphbclfmclpmgphaabo`
   - **URL:** `https://raw.githubusercontent.com/ERAT-ANVANDARE/skolfilter/main/update.xml`
7. Sätt **Installation policy** till **Force install**
8. Klicka **Save**

---

## Steg 4: Verifiera på en Chromebook

1. Öppna Chrome och gå till `chrome://extensions`
2. Tillägget ska synas med texten **"Installed by your administrator"**
3. Gå till `chrome://policy` och klicka "Reload policies" för att tvinga synk

---

## När ni vill uppdatera listorna

1. Bygg om tillägget med nya regler (ny rules_X.json)
2. Öka versionsnumret i `manifest.json` (t.ex. 1.0.1)
3. Signera om med **samma** `school-filter-key.pem`
4. Ladda upp ny `school-filter.crx` och uppdaterad `update.xml` till GitHub
5. Chrome hämtar automatiskt nya versionen till alla Chromebooks

⚠️ **Viktigt:** Använd alltid samma `school-filter-key.pem` vid ombyggnad.
Om ni tappar bort nyckeln måste ni byta Extension ID och konfigurera om Google Admin.

---

## Teknisk info
- Manifest version: 3 (MV3)
- Antal regler: 66 253 statiska DNR-regler
- Fördelade på 3 ruleset-filer (max 30 000 per fil)
- CRX SHA256: `ea2f507eb3a8c56085f086acd24250e92265abcc2562f35352434f93f9cee0cf`
