# Kontrola spójności dokumentów w SQL

Zapytania SQL do analizy i kontroli danych w systemie handlowo-magazynowym: od zamówienia klienta, przez wydanie z magazynu, po fakturę i korektę.

---

## O projekcie

**Cel:**
Baza odwzorowuje uproszczony obieg dokumentów w firmie handlowej (ZMK → WZ → FV, dostawy PZ, zwroty ZW i korekty KOR). Zapytania odpowiadają na pytania, które w codziennej pracy zadaje dział sprzedaży, magazyn i księgowość, oraz wykrywają rozbieżności między dokumentami.

**Dane:** fikcyjne, wygenerowane z pomocą AI na potrzeby ćwiczeń (styczeń–wrzesień 2026). Zapytania, analiza i wnioski są moje. Data referencyjna w zapytaniach: 2026-09-30.

## Struktura bazy

| Tabela | Zawartość |
|--------|-----------|
| `kontrahenci` | Klienci i dostawcy |
| `towary` | Kartoteki towarowe z ceną i statusem aktywności |
| `zamowienia`, `zamowienia_pozycje` | Zamówienia klientów (ZMK) |
| `dokumenty_mag`, `dokumenty_mag_pozycje` | Dokumenty magazynowe: PZ, WZ, ZW |
| `faktury`, `faktury_pozycje` | Faktury sprzedaży (FV) i korekty (KOR) |

Stan magazynowy nie jest przechowywany w tabeli, tylko liczony z dokumentów, tak jak w systemach ERP.

## Co sprawdzają zapytania

**Raporty sprzedażowe:** wartość zamówień, top klienci, sprzedaż wg kategorii i miesięcy.

**Stany magazynowe:** bieżący stan każdego towaru, towary zalegające.

**Kontrola dokumentów:**
- wydania bez faktury,
- rozbieżności ilości między WZ a fakturą,
- korekty bez zwrotu na magazyn i zwroty bez korekty,
- ujemne stany magazynowe,
- sprzedaż towarów wycofanych,
- nieopłacone faktury po terminie.

## Najważniejsze wnioski

- 
- 
- 

## Pliki

- `baza_handel.db` – baza SQLite gotowa do otwarcia
- `baza_handel.sql` – skrypt tworzący tabele i dane
- `zapytania.sql` – wszystkie zapytania z komentarzami

## Tech Stack & Kompetencje

- **Silnik bazy:** SQLite
- **Narzędzia:** DB Browser for SQLite
- **SQL:** SELECT, JOIN (w tym LEFT JOIN do wykrywania braków), GROUP BY, HAVING, CASE, funkcje dat
- **Znajomość domenowa:** obieg dokumentów handlowych i magazynowych, fakturowanie i korekty, kontrola stanów
