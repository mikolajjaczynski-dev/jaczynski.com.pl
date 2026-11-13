# jaczynski.com.pl

Domena dodatkowa — **przekierowanie** na <https://modelesieci.pl/> (domena główna od 13.11.2026).

VH.pl bez hostingu nie oferuje przekierowania domeny, a GitHub Pages nie wysyła
nagłówka 301. Dlatego `index.html` i `404.html` to strony-przekierowania:

- `<meta http-equiv="refresh" content="0; url=…">`: natychmiastowe odświeżenie,
  które Google traktuje jak przekierowanie stałe,
- `<link rel="canonical">`: wskazuje modelesieci.pl jako adres kanoniczny,
- `location.replace(…)`: przekierowanie w JavaScripcie (bez wpisu w historii).

`404.html` sprawia, że każda podstrona (np. `jaczynski.com.pl/cokolwiek`) też przekierowuje.

Publikowana przez GitHub Pages (gałąź main, katalog główny), domena w `CNAME`.
Pełny opis strony i domen: README repozytorium `mikolajjaczynski-dev/modelesieci.pl`.
Poprzednia treść jest w historii gita.
