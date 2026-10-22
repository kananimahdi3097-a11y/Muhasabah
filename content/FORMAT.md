# Content packs for Muhasabah

Add a pack file here and list it in `index.json`. The app downloads new or updated packs on open.

## Short reminders (used in nudges, Wisdom tab, Ask)
```json
{ "id": "imam-zaman-2", "version": 1, "title": "Imam-e-Zamana — set 2",
  "items": [ { "id": "iz2-1", "ar": "…", "en": "…", "gu": "…", "src": "Book, ref", "topics": ["imamzaman"] } ] }
```

## Books (large: Quran, hadith collections, tafsir — searched by the Ask tab)
```json
{ "id": "al-kafi-2", "version": 1, "type": "library", "book": "al-Kafi vol. 2",
  "items": [ { "id": "kafi2-1-1", "ref": "Kitab al-Iman, ch. 1, h. 1", "ar": "…", "en": "…", "gu": "…", "topics": [] } ] }
```

`index.json`:
```json
{ "packs": [ { "id": "al-kafi-2", "version": 1, "title": "al-Kafi vol. 2", "file": "content/al-kafi-2.json" } ] }
```
