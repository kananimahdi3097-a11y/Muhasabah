# Muhasabah — weekly content process

The app shows one **"From the books"** hadith and one **"Tip of the day"** every day.
New items reach the phone through content packs listed in `content/index.json`. No app update is needed.

## Files
- `daily_candidates.json` — about 2,000 hadith pre-filtered from the Thaqalayn dataset (CC BY 4.0).
  These are **reliable-graded** (Sahih / Hasan / Muwaththaq / Mu'tabar by al-Majlisi, al-Behbudi, al-Muhsini or Hadi al-Najafi), or Nahj al-Balagha sayings.
  They are short and non-fiqh. Fields: id, ref, book, ar, en, who, grade[], tr, url, tafsir, topic.
- `daily_used_ids.json` — candidate ids already published (in order). Never publish an id twice.
- `daily-1.json`, `tips-1.json` — set 1 (also bundled inside the app).

## Weekly job (7 hadith + 7 tips)
1. Pick the next 7 unused candidates that are **self-contained wisdom**, not legal cases or dialogues.
   Mix the topics: Nahj, akhlaq, knowledge, imamat (Imam-e-Zamana), business, dua, Quran/tafsir.
2. Keep `ar`, `en`, `ref`, `grade`, `tr`, `url` exactly as in the candidate. Remove only footnote markers like `[1]`.
3. Add `gu`, `ur` and `hi` translations of `en`. These must be faithful and plain.
   - Name the speaker as in the English: Abu ʿAbd Allah = Imam Jaʿfar al-Sadiq; Abu Jaʿfar = Imam al-Baqir; Amir al-Mu'minin = Imam Ali.
   - Use the standard honorifics: (અ.સ.) / علیہ السلام / (अ.स.) and (સ.અ.વ.) / صلی اللہ علیہ وآلہ / (स.अ.व.).
4. Set `by` to the `who` code only when the English does not already name the speaker.
5. Write `content/daily-N.json` as `{"id":"daily-N","version":1,"type":"daily","title":"From the books — set N","items":[…]}`.
6. Write 7 new original tips: business for a one-person online store, health, wellness, money, mind, family.
   - Each tip needs a **real, checkable** source, or "Practical habit". Never invent studies.
   - Fields: id `tNNN`, cat, e, t, b, src, gt, gb, ut, ub, ht, hb.
   - Write them to `content/tips-N.json` with `"type":"tips"`.
7. Add both packs to `content/index.json` (not optional), append the used ids to `daily_used_ids.json`, then commit and push.
