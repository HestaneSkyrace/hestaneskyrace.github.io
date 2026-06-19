# Hestane Skyrace — nettside

Informasjonsside for Hestane Skyrace 2026, bygd med [Quarto](https://quarto.org) og publisert til GitHub Pages.

## Struktur

```
.
├── _quarto.yml          # prosjekt- og nettsidekonfig (navbar, tema, meny)
├── theme.scss           # eige fargetema og typografi
├── index.qmd            # heimeside med hero
├── loype.qmd            # løypebeskriving + bilete
├── program.qmd          # tidsplan og program
├── utstyr.qmd           # obligatorisk utstyr + reglar + sikkerheit
├── praktisk.qmd         # reise, parkering, overnatting, kontakt
├── images/              # alle bilete
└── .github/workflows/
    └── publish.yml      # auto-bygg + publiser til Pages ved push
```

## Køyre lokalt

Installer Quarto frå <https://quarto.org/docs/get-started/>. Deretter:

```bash
quarto preview      # live forhandsvisning i nettlesar
quarto render       # bygg ferdig nettstad til _site/
```

## Publisere på GitHub Pages

1. Lag eit nytt repo på GitHub (t.d. `hestane-skyrace`).
2. Push alle filene i denne mappa til `main`:
   ```bash
   git init
   git add .
   git commit -m "Første versjon av nettsida"
   git branch -M main
   git remote add origin https://github.com/BRUKAR/hestane-skyrace.git
   git push -u origin main
   ```
3. På GitHub: **Settings → Pages → Source → GitHub Actions**.
4. Ved kvar push til `main` bygger og publiserer workflowen sida automatisk.
   URL blir `https://BRUKAR.github.io/hestane-skyrace/`.

### Eige domene (valfritt)

Vil du bruke t.d. `hestaneskyrace.no`: legg domenet under **Settings → Pages → Custom domain**, og oppdater `site-url` i `_quarto.yml`.

## Byte ut bilete

Legg nye bilete i `images/` og oppdater filnamna i `.qmd`-filene. Banner-bileta
(`cover_banner.png`, `banner_loype.png`, `banner_smal.png`) er breie utsnitt —
bruk gjerne liggande bilete der for best resultat.

## Oppdatere innhald

All tekst ligg i `.qmd`-filene (Markdown). Rediger fritt — endringar går live
automatisk ved neste push. Programtabellen ligg i `program.qmd`.
