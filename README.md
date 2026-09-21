# Hedda-Filter

Webbfilter for Hedda Wisingskolan med **66 207 statiska blockeringsregler** (MV3).

## Extension ID
```
blckbpgnnfgmjicijhdldnajllmicpod
```

## Filer att ladda upp till GitHub (detta repo)
| Fil | Beskrivning |
|-----|-------------|
| `Hedda-Filter.crx` | Det signerade tillägget |
| `update.xml` | Uppdateringsfil som Google Admin pekar på |

## ⚠️ Spara LOKALT – ladda ALDRIG upp
`hedda-filter-key.pem` – signeringsnyckeln. Krävs vid framtida uppdateringar.

---

## Installera via Google Admin

1. Gå till **admin.google.com**
2. **Devices → Chrome → Apps & extensions → Users & browsers**
3. Välj OU för eleverna
4. Klicka **+** → **Add Chrome app or extension by ID**
5. Välj **"From a custom URL"**
6. Fyll i:
   - Extension ID: `blckbpgnnfgmjicijhdldnajllmicpod`
   - URL: `https://raw.githubusercontent.com/s-vernberg/Hedda_Wisingskolan/main/update.xml`
7. Sätt **Installation policy** → **Force install**
8. **Save**

## Verifiera på Chromebook
- Gå till `chrome://extensions` → ska visa **"Installed by your administrator"**
- Gå till `chrome://policy` → klicka "Reload policies"

---

## Uppdatera listorna i framtiden
1. Bygg om tillägget med nya regler
2. Öka versionsnummer i `manifest.json` (t.ex. `1.0.1`)
3. Signera med **samma** `hedda-filter-key.pem`
4. Ersätt `Hedda-Filter.crx` och `update.xml` i repot
5. Chrome uppdaterar automatiskt på alla Chromebooks

## Blockerade kategorier
- Spel & gaming (66 000+ domäner)
- TikTok, Snapchat, Instagram
- Twitter/X, Reddit, Twitch, Roblox
- Facebook & WhatsApp
- VPN, proxy & DoH-bypass
- Dynamisk DNS
- Gratisvärdar
- Bedrägerisajter
