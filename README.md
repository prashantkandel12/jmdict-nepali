# jmdict-nepali: Nepali glosses for JMdict and kanji meanings from KANJIDIC2

Nepali translations for the Japanese-English dictionary **JMdict** (all 219,091 entries) and Nepali meanings for
10,381 kanji from **KANJIDIC2**, made for the Putali JLPT study app. The data is machine-generated and automatically validated; it may contain errors.

| File | Content |
|---|---|
| `data/dictionary_ne.jsonl` | One JSON object per JMdict entry: `id` (JMdict `ent_seq`), `w` (written form), `ne` (Nepali meaning), `src` (model that produced it, or `merge`), `confidence` (judge score 0-1, `null` if not judged), `judged` |
| `data/kanji_meanings_ne.json` | Keyed by kanji character: `ne` / `en` short core meaning, `src` |

## Sources and attribution (required)

This work is derived from **JMdict** and **KANJIDIC2**, files of the [Electronic Dictionary Research and Development Group](https://www.edrdg.org/) (EDRDG),
used in accordance with the [EDRDG licence](https://www.edrdg.org/edrdg/licence.html). JMdict was taken from the English-glossed
`jmdict-simplified` JSON release 3.6.2 (JMdict dated 2026-11-16, <https://github.com/scriptin/jmdict-simplified>).
Project pages: <https://www.edrdg.org/wiki/index.php/JMdict-EDICT_Dictionary_Project> and <https://www.edrdg.org/wiki/index.php/KANJIDIC_Project>.
Copyright in JMdict and KANJIDIC2 remains with James William Breen and EDRDG.

## License: CC BY-SA 4.0

Licensed under **Creative Commons Attribution-ShareAlike 4.0 International** (see `LICENSE`), the same license as JMdict and KANJIDIC2.

- **Attribution**: credit JMdict/KANJIDIC2 (EDRDG) and this repository, link to the license, and indicate changes. Apps must show the acknowledgement on a dedicated "About/Sources" screen (not just a launch screen) and link to the EDRDG pages above.
- **ShareAlike**: if you adapt or build on this data, distribute the result under CC BY-SA 4.0 or a compatible license.
- Keep derived data reasonably current with new JMdict releases (EDRDG licence section 4).
- No warranty.

## How it was generated

Providers' Batch APIs with strict JSON output and programmatic validation (Devanagari present, no stray Latin letters, structure checks; failed items retried).

| Data | Generation | Judge |
|---|---|---|
| JLPT/common dictionary entries (23,149 judged) | `gpt-6-luna` and `gemini-3.5-flash-lite`, blind and independent | `gpt-6.1-terra` picks the better or merges (randomized order), confidence score |
| All other dictionary entries | `gpt-6-luna` only | none (`judged: false`) |
| Kanji meanings | produced together with the kanji explanations (not published here): `gpt-6.1-terra` + `gemini-3.8-flash` judged by `gpt-6.1-terra` for core kanji, `gpt-6-luna` for rare kanji | see `src` |

Generated 2026-11-20 for the Putali JLPT app by Prashant Kandel (<https://github.com/prashantkandel12/jmdict-nepali>).
