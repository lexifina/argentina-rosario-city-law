# How this repository was made (Rosario)

This file is written by the build on 2026-10-31, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Municipalidad de Rosario, Normativa (www.rosario.gob.ar/mr/normativa) and its register of norms (www.rosario.gob.ar/normativa) | <https://www.rosario.gob.ar/mr/normativa> | 2026-10-31 | Official municipal ordinances, published in the Boletín Oficial Municipal. Argentina's copyright law (Ley 11.723) has no express exclusion for them; ordinances are public acts of government, binding on everyone once officially published. The municipality's terms of use (Términos y condiciones, Decreto 2098/2021, Anexo II) say its published content may be used, reproduced and modified with reference to the Creative Commons 4.0 licence. Reproduced with attribution, following the official text. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `ordenanza-10850-2025` | Ordenanza 10850/2025: Autonomía municipal | 1 | 2026-08-30 to 2026-08-30 |
| `ordenanza-10267-2021` | Ordenanza 10267/2021: Código de Convivencia Ciudadana | 1 | 2026-09-11 to 2026-09-11 |
| `ordenanza-6543-1998` | Ordenanza 6543/1998: Código de Tránsito | 1 | 2026-07-24 to 2026-07-24 |
| `decreto-ordenanza-9476-1978` | Decreto-Ordenanza 9476/1978: Código Tributario Municipal | 1 | 2026-07-25 to 2026-07-25 |
| `ordenanza-3574-1984` | Ordenanza 3574/1984: Estatuto y Escalafón del Personal Municipal | 1 | 2025-12-12 to 2025-12-12 |
| `decreto-ordenanza-19975-1957` | Decreto-Ordenanza 19975/1957: Ordenanza de Contabilidad | 1 | 2025-12-12 to 2025-12-12 |
| `ordenanza-4064-1986` | Ordenanza 4064/1986: Ordenanza General Impositiva | 1 | 2025-12-26 to 2025-12-26 |
| `decreto-438-1998` | Decreto 438/1998: Reglamento de Compras | 1 | 2025-10-01 to 2025-10-01 |

The build made 8 commits:

| Commits | Kind |
| ---: | --- |
| 8 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futuro`: laws not yet in force on 2026-10-31.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 8 laws in the record.
- 8 tags.

## Dates

Each commit is dated at noon (America/Argentina/Cordoba) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: An ordinance takes effect on the day its own vigencia clause names; otherwise, as for any general norm, under Código Civil y Comercial de la Nación, art. 5 ("Las leyes rigen después del octavo día de su publicación oficial, o desde el día que ellas determinen"), counted under art. 6 (the day of publication excluded): the ninth day after its publication in the Boletín Oficial Municipal. https://servicios.infoleg.gob.ar/infolegInternet/anexos/235000-239999/235975/texact.htm

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `6224e0bfa5df66e58ed76f58822a65e344677f14997ea7a61fb7f1792ba626cb` (1170281 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3d00541d258745461ab52b1b0cb4e1716a27a95d`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

8 versions of 8 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Source: the consolidated texts (texto actualizado) the Municipalidad de Rosario publishes at www.rosario.gob.ar/mr/normativa. Earlier consolidated versions are not published, so each norm is shown as its current text only, the oldest version available.
- Date of each text: its notes link the norms that amended it to their records in the municipality's register of norms. The records of the latest-year norms linked (at most four) are read for their Boletín Oficial publication date; the text is dated the in-force day of the latest of them, the ninth day after its publication (Código Civil y Comercial, arts. 5 and 6). Where a note's link points to a different record than the norm it names, the record the link points to is used.
- Rosario has no carta orgánica yet; the autonomy ordinance (Ordenanza 10.850/2025) comes first, then the codes. The provincial Ley Orgánica de Municipalidades (Ley 2756) is provincial law and not included.
- Units: the heading (encabezado: everything before the first Artículo) and one file per article, holding the article and everything printed after it up to the next article (section headings, amendment notes, annexes). Where an approving ordinance's articles and the code's own articles share a number, the later ones are kept as separate files (-dup2). Nothing is dropped. One paragraph per line, spacing normalised.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- A model (Claude) wrote the fetch and parse code and chose which norms to include; it wrote no law text. Every word of law comes from the provincial source's own texts.
