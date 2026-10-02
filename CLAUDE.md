# CLAUDE.md

Regeln für Claude Code in diesem Repo. Was drinliegt und woher, steht in `README.md`.

## Was das ist

Medienarchiv der @makesapps-Apps: Store-Texte und Screenshots je App, Version und
Sprache, dazu die veröffentlichten Kurzvideos als Release-Assets. Kein Code, keine
Entwürfe; der Renderer liegt in `~/GitHub/social-video`.

## Regeln

- Ablage `apps/<slug>/<plattform>-<version>/<locale>/` wie in `README.md`; PNGs
  laufen über Git LFS (`.gitattributes`).
- Abgenommene Screenshots und Store-Texte auch unveröffentlichter Versionen kommen
  hierher und werden in der App-README als „in Vorbereitung“ geführt; „verkauft:
  iOS x.y“ bleibt bei der Version im Store. Nach dem Release mit App Store
  Connect abgleichen.
- Rohaufnahmen und Entwürfe bleiben lokal in den App-Repos.
- Das Repo ist öffentlich (Ausnahme REMOTE in `~/GitHub/local-ci/ausnahmen.tsv`):
  nichts Internes, keine Schlüssel, keine unveröffentlichten Preise.
- Tests gibt es nicht (Ausnahme TEST-SH im Register). Uploads großer Dateien
  (LFS, Release-Assets) laufen über die Lauf-Warteschlange mit `--art netz`.
- Global gilt `~/.claude/CLAUDE.md`.
