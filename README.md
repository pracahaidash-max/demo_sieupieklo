# Się Upiekło Wola — nowa strona

Nowa strona (od zera — brak wcześniejszej strony, tylko Instagram i Google Maps)
dla cukierni Się Upiekło Wola. Astro (statyczny build) + Decap CMS (Warstwa B).

## Do zrobienia przed wysyłką do klienta

- [ ] **E-mail** — brak adresu e-mail na Instagramie/Mapach, tylko telefon
      (796 039 089). Uzupełnić w `src/content/site.yaml` (`firma.email`).
- [x] **Zdjęcia** — sekcja „Realizacje" i hero używają 11 realnych zdjęć
      wyciętych z profilu Instagram @cukiernia_ciasta_torty (właściciela tej
      strony) — zapisane w `public/images/realizacje/`. Warto podmienić na
      zdjęcia w wyższej rozdzielczości prosto z telefonu klienta, gdy będą
      dostępne — obecne są przycięte ze zrzutów ekranu, więc jakość jest
      ograniczona.
- [ ] Domena i hosting — jak w poprzednich projektach: Netlify (Forms +
      Git Gateway pod Decap CMS bez dodatkowego backendu).

## Znak wodny „MID" (wersja demo)

`src/content/site.yaml` → `demo: true` włącza pełnoekranowy znak wodny i
plakietkę w rogu. Ustawić na `false` i zapisać dopiero po zaakceptowaniu
projektu i zapłacie — wtedy znika automatycznie z całej strony.

## Rozwój lokalnie

```bash
npm install
npm run dev       # podgląd na localhost:4321
npm run build     # build produkcyjny do dist/
```

## Wdrożenie na Netlify (Warstwa B — panel edycji dla klienta)

1. Połącz to repo z nowym site'em na Netlify (build: `npm run build`,
   publish dir: `dist` — ustawione w `netlify.toml`).
2. Site settings → Identity → Enable Identity.
3. Site settings → Identity → Services → Git Gateway → Enable.
4. Zaproś klienta jako użytkownika Identity (jego e-mail).
5. Klient edytuje treść na `twojadomena.pl/admin` — zmiana leci jako commit
   do `main`, strona przebudowuje się automatycznie.

Formularz zamówienia w sekcji „Kontakt” korzysta z **Netlify Forms**
(`data-netlify="true"`) — działa automatycznie po wdrożeniu na Netlify.

## Struktura treści

Cała edytowalna treść leży w `src/content/site.yaml`. Realne dane firmy
(adres, telefon, godziny, ocena, opinie) pochodzą z profilu Google Maps
i Instagrama — nic nie jest zmyślone poza znacznikami `TODO`.
