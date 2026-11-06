# Rosario: municipal law history in git

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is the law of Rosario, Santa Fe, Argentina, which global-law reads at `argentina/santa-fe/rosario/acts/`.

The municipal law of the city of Rosario (Province of Santa Fe), Argentina, as a git history: one file per article, one commit per ordinance on the day it took effect. `git log` lists the changes; checking out a date gives the text the record holds for that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `ar-s-rosario/`. The province's law is in [lexifina/argentina-santa-fe-law](https://github.com/lexifina/argentina-santa-fe-law) and Argentina's national law in [lexifina/argentina-law](https://github.com/lexifina/argentina-law).

The text is in Spanish, exactly as the source prints it.

## What this repository holds

8 norms so far: its main codes and ordinances, each as its current consolidated text. Rosario has no carta orgánica yet (its first is to be drafted by a convention elected under Ordenanza 10.850/2025 on municipal autonomy); its organic law is the Province of Santa Fe's Ley Orgánica de Municipalidades, Ley 2756, which is provincial law and not included here. The autonomy ordinance comes first.

| Folder | Norm | History |
| --- | --- | --- |
| `ordenanza-10850-2025/` | Ordenanza 10850/2025: Autonomía municipal | current text only, as of 30 August 2026 |
| `ordenanza-10267-2021/` | Ordenanza 10267/2021: Código de Convivencia Ciudadana | current text only, as of 11 September 2026 |
| `ordenanza-6543-1998/` | Ordenanza 6543/1998: Código de Tránsito | current text only, as of 24 July 2026 |
| `decreto-ordenanza-9476-1978/` | Decreto-Ordenanza 9476/1978: Código Tributario Municipal | current text only, as of 25 July 2026 |
| `ordenanza-3574-1984/` | Ordenanza 3574/1984: Estatuto y Escalafón del Personal Municipal | current text only, as of 12 December 2025 |
| `decreto-ordenanza-19975-1957/` | Decreto-Ordenanza 19975/1957: Ordenanza de Contabilidad | current text only, as of 12 December 2025 |
| `ordenanza-4064-1986/` | Ordenanza 4064/1986: Ordenanza General Impositiva | current text only, as of 26 December 2025 |
| `decreto-438-1998/` | Decreto 438/1998: Reglamento de Compras | current text only, as of 1 October 2025 |

## Source

Municipalidad de Rosario, Normativa (www.rosario.gob.ar/mr/normativa) and its register of norms (www.rosario.gob.ar/normativa), <https://www.rosario.gob.ar/mr/normativa>. The municipality publishes the consolidated text (texto actualizado) of its main codes and ordinances, with notes naming and linking the norm that made each change; its register of norms gives each norm's Boletín Oficial number and publication date. Earlier consolidated versions are not published.

## Dates

- Each commit is dated at **noon, America/Argentina/Cordoba**. The source publishes only today's consolidated text of each norm. Each is shown as its current text only, the **oldest version available**, dated the day the latest amending norm linked in its notes took effect (the ninth day after that norm's publication in the Boletín Oficial, as its record gives it); its earlier wording is not shown.
- Versions that take effect after the retrieval day are on the `futuro` branch, never merged into `main`.

## Files

`<ordinance>/art-005.md` is Artículo 5; `encabezado.md` holds the number, the place and date, the expediente line and anything printed before Artículo 1. Signatures and annexes stay in the file of the article they follow. One paragraph per line.

## How it is checked

- Every version of every ordinance is read back from git on the day it took effect and on the day before (`tools/check_repo.py`); both must match `corpus.json`.
- The letters and digits of every version equal those of the source page it was read from (read again with an independent HTML reader), so no word is lost or added.
- Health checks: no merge commits, commit dates never go backwards, nothing dated in the future, and every commit's trailers parse.

## Limits

This is not an official publication. The binding text is the one published in the Boletín Oficial Municipal Electrónico de Rosario (B.O.M.E.). Only the norms listed above are included, each as its current consolidated text only.
