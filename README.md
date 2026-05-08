# Blackfire GraphQL Command Builder

Prosta, statyczna aplikacja HTML do generowania komend `blackfire curl` dla requestów GraphQL, szczególnie pod Magento 2 uruchomione lokalnie lub w Dockerze.

Aplikacja działa w całości w przeglądarce. Nie ma backendu, nie wysyła requestów do Magento ani do Blackfire. Jej zadaniem jest tylko zbudowanie gotowej komendy, którą można skopiować i odpalić ręcznie w kontenerze.

---

## Do czego służy?

Podczas profilowania Magento 2 przez Blackfire często trzeba odpalać requesty w stylu:

```bash
blackfire curl -k \
  -H 'Host: example.local' \
  'https://magento_nginx/graphql?query=%7B__typename%7D'
```

Ręczne składanie takich komend jest niewygodne, szczególnie gdy GraphQL query jest długie i zawiera wiele pól, filtrów, wariantów, cen, galerii, kategorii albo custom attributes.

Ta aplikacja pozwala wkleić czytelne GraphQL query, uzupełnić endpoint oraz nagłówki, a następnie wygenerować gotowy request do Blackfire.

---

## Funkcje

* generowanie komendy `blackfire curl`,
* obsługa endpointu GraphQL, np. `https://magento_nginx/graphql`,
* obsługa nagłówka `Host`, np. `example.local`,
* obsługa metody `GET`, gdzie query trafia do parametru URL,
* obsługa metody `POST`, gdzie query trafia do JSON body,
* opcjonalne GraphQL variables,
* opcjonalne dodatkowe nagłówki, np. `Store`, `Authorization`, `Accept`,
* opcja dodania `-k` / `--insecure` dla lokalnych certyfikatów TLS,
* opcjonalna nazwa profilu Blackfire przez `--title`,
* przycisk kopiowania komendy do schowka,
* możliwość odkodowania query z istniejącego URL/curl,
* działa jako pojedynczy plik `index.html`, więc nadaje się bezpośrednio pod GitHub Pages.

---
