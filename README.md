# Loyalty Tracker – Brand assets

Public repository of brand logos and catalog used by **Loyalty Tracker** (offline-first loyalty cards app).

## Structure

```
catalog.json          # list of known brands + aliases
logos/
  carrefour.png
  fnac.png
  ...
```

## catalog.json format

```json
{
  "version": 1,
  "cards": [
    {
      "id": "fnac",
      "name": "Fnac",
      "logo": "fnac.png",
      "color": "#1A1A1A",
      "aliases": ["fnac", "fnac darty"]
    }
  ]
}
```

- `id` : unique slug  
- `name` : display name  
- `logo` : filename inside `logos/`  
- `color` : brand accent (hex)  
- `aliases` : alternative spellings matched when the user types a store name  

## How the app uses it

Base URL:
```
https://raw.githubusercontent.com/Borypb/loyalty-tracker-brand/main
```

When the user types a store name while adding a card, the app searches this catalog.  
If a match is found it offers the logo; otherwise the user can continue without one.

Logos are downloaded once and cached locally. No personal data is ever sent.

## Current coverage

~70 French retail & services brands (grocery, fashion, sport, beauty, DIY, telecom, culture, food service, etc.).

Placeholder logos ship as colored tiles with the brand name. Replace any file in `logos/` with the official asset (same filename) when available.
