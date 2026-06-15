# VWS-Workbook — Änderungen für das Tool-Workbook

**Stand:** 2026-06-15
**Zweck:** Alle Korrekturen, die am Buch (KDP-Print) gemacht wurden, ins **Tool-Workbook** übernehmen
(`workbook_base.pdf` = DE, `workbook_base_en.pdf` = EN), das `generate-workbook.js` nach dem Kauf ausliefert.

---

## ⭐ WICHTIGSTER PUNKT — geändertes Vision-Beispiel (Kapitel 3)

Exakter Wortlaut (muss 1:1 so im Tool-Workbook stehen):

### Deutsch
> **Vision A:** „Ich will ein erfolgreiches Unternehmen aufbauen, das einen echten Mehrwert für die Menschen schafft."
>
> **Vision B:** „Ich führe eine Agentur, die mit Konventionen bricht und jungen Marken eine eigene Stimme gibt — und abends habe ich noch Energie für mein Leben und die Menschen, die mir etwas bedeuten."
>
> Vision A klingt gut — und sagt nichts. Zukunftsform, austauschbar, hilft bei keiner Entscheidung weiter. Vision B steht in der Gegenwart, hat eine Haltung, die nur zu dir gehört, und zieht eine klare Linie zwischen Arbeit und Leben. Nur eine davon ist ein Kompass. Welche hilft dir, bei einem Jobangebot Ja oder Nein zu sagen?

### Englisch
> **Vision A:** "I want to build a successful company that creates real value for people."
>
> **Vision B:** "I run an agency that breaks with convention and gives young brands a voice of their own — and in the evening I still have energy for my own life and the people who matter to me."
>
> Vision A sounds good — and says nothing. Future tense, interchangeable, no help with any decision. Vision B is in the present, holds a stance that is yours alone, and draws a clear line between work and life. Only one is a compass. Which one helps you say yes or no to a job offer?

**Achtung:** „Agentur" ist feminin → „**die** Agentur, **die** … bricht" (nicht „das"). Vision B endet auf „die mir etwas bedeuten" (NICHT „mehr Umsatz machen").

---

## Inhaltliche Korrekturen (DE + EN, sofern nicht anders vermerkt)

1. **Berater Kapitel 1:** „Marcus, 41" → **„Paul, 41"** (auch 2. Nennung: „Paul schweigt lange" / „Paul is silent for a long time"). Grund: zu nah an „Marc".
2. **Gründer-Profil:** „Marc, 41" → **„Marc, 43"** (auch auf der Fortsetzungs-/continued-Seite).
3. **Kaiser (nur DE):** durchgängig **„Marc Aurel"** (Porträt-Überschrift + Fließtext); „Marcus Aurelius" raus. → EN bleibt „Marcus Aurelius".
4. **Umlaut-Tippfehler (nur DE):** „UEBERDAUERT" → **„ÜBERDAUERT"** (Mandela-Header); „KRAEFTE" → **„KRÄFTE"** (Napoleon-Header).
5. **Vision-Selbsttest:** „zehn Jahre" → **„20 Jahre"** (DE) / „still true in ten years" → **„still true in 20 years"** (EN) — Abgleich mit den fünf Tests.
6. **Profil-Folgeseiten (nur EN):** deutsches „Fortsetzung" → **„continued"** (Julia/Marc/Sandra/Tim).
7. **Abschnitts-Kicker (nur EN):** deutsches „BEVOR DU BEGINNST" → **„BEFORE YOU BEGIN"** (S. 3).

## Titelseite (innen) — neue Cover-Logik

8. **DE:** war „Dein Coaching-Workbook" → jetzt
   - Zeile 1 (Crimson #8E1429, Lora-Italic ~24): **„Vision Werte Strategie"**
   - Zeile 2 (Navy #1A2744, groß): **„Dein Workbook"**
   - Sub (Taubenblau #5F7FA8, Lora-Italic): **„9 Kapitel · 4 Werkstätten · 6-Wochen-Coaching-Programm"**
   - (Neuer Absatzstil „cover_method" nötig; alter Kicker „VISION · WERTE · STRATEGIE" entfällt.)
9. **EN:** Titelseiten-Sub „The 6-Week Program" → **„6-Week Coaching Program"** (NUR die Titelseiten-Zeile, **nicht** der Programm-Abschnitt selbst). Titelseite war schon „Vision Values Strategy / Workbook".

## Layout

10. **DE — fast leere Seite 4 behoben:** Abstände auf der Seite „Wie du mit diesem Buch arbeitest" gestrafft, sodass „Gemeinsam gestalten wir deine Zukunft. / Werner" auf S. 3 sitzt.
    - „Drei Wege"-Block: leading 16,5 → **15,5**, spaceAfter 10 → **7**
    - Spacer vor „Vier Regeln": 8 → **3**
    - Spacer vor Schlusszeile: 12 → **6**
    - **Folge: Print-Seitenzahl 182 → 181.**
11. Frühere Fixes (falls im Tool-Workbook noch nicht enthalten): Foto auf der Zitatseite, Motor-Metapher raus → „…Und genau danach suchen wir hier.", Rand-Fix.

---

## Hinweise für die Umsetzung

- **Format:** Die KDP-Dateien sind die **Print-Version** (7×10″, Bleed). Das Tool nutzt die **digitale Fassung** → alle Änderungen im **`target='digital'`-Build** erzeugen.
- **Quell-Skripte:** `build_workbook_master.py` + `wb_ext.py` (DE); `build_workbook_master_en.py` + `wb_ext_en.py` (EN).
- **Nur die Basis-PDF tauschen:** `workbook_base.pdf` (DE) / `workbook_base_en.pdf` (EN). Personalisierter Kentaur + Profildaten kommen per `generate-workbook.js` drüber → daran nichts ändern.
- **Kentaur-Overlay-Position** in generate-workbook.js (DE oTop=493.95, EN oTop=454.11) nur prüfen, falls die neue Titelseite die Cover-Höhe minimal verschiebt.
