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
      "color": "#E6E6E6",
      "aliases": ["fnac", "fnac darty"]
    }
  ]
}
```

- `id` : unique slug
- `name` : display name
- `logo` : filename inside `logos/`
- `color` : optional brand accent (ARGB/hex)
- `aliases` : alternative spellings the app will match against

## How the app uses it

Base URL:
```
https://raw.githubusercontent.com/Borypb/loyalty-tracker-brand/main
```

When the user types a store name while adding a card, the app searches this catalog.  
If a match is found it offers the logo; otherwise the user can continue without one.

Logos are downloaded once and cached locally. No personal data is ever sent.
