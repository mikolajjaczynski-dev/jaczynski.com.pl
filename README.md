# jaczynski.com.pl

Strona „w budowie” — Mikołaj Jaczyński · Sieci wod-kan w praktyce.
Publikowana przez GitHub Pages (gałąź main, katalog główny).

## Domeny dodatkowe — przekierowania

`jaczynski.com.pl` jest jedyną domeną z treścią (domena kanoniczna dla Google).
Pozostałe domeny przekierowują tutaj. Identyczna treść pod trzema domenami
byłaby dla Google duplikatem.

| Domena | Repozytorium | Przekierowanie |
| --- | --- | --- |
| `modelesieci.pl` | `mikolajjaczynski-dev/modelesieci.pl` | → `https://jaczynski.com.pl/` |
| `praktykasieci.pl` | `mikolajjaczynski-dev/praktykasieci.pl` | → `https://jaczynski.com.pl/` |

**Dlaczego tak:** VH.pl bez hostingu nie ma opcji przekierowania domeny, a
GitHub Pages nie wysyła nagłówka HTTP 301. Dlatego oba repozytoria zostały na
GitHub Pages (DNS bez zmian: A×4 na GitHub, `www` CNAME, TXT weryfikacji), ale
ich `index.html` i `404.html` to strony-przekierowania:

- `<meta http-equiv="refresh" content="0; url=https://jaczynski.com.pl/">`:
  natychmiastowe odświeżenie, które Google traktuje jak przekierowanie stałe,
- `<link rel="canonical" href="https://jaczynski.com.pl/">`,
- `location.replace(…)` w JavaScripcie.

Dzięki `404.html` każda podstrona domeny dodatkowej też przekierowuje.
HTTPS działa, bo certyfikat wystawia GitHub Pages.

**Nie usuwaj tych repozytoriów.** Bez nich domeny pokażą błąd 404 z GitHuba.
Gdyby kiedyś któraś domena miała dostać własną treść, wystarczy podmienić
`index.html` w jej repozytorium (poprzednia wizytówka jest w historii gita).
