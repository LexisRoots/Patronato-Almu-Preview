# PATRONATO — Piloto de transcripciones: handoff i plan rozwoju
Data rozpoczęcia: 24.11.2026  
Adres pilotażu: https://lexisroots.github.io/Patronato-Almu-Preview/piloto-transcripciones.html  
Repozytorium: https://github.com/LexisRoots/Patronato-Almu-Preview  
Baza: Master Catalog v8.2 (114 publicznych rekordów). Nie naruszać oryginałów Google Drive ani dotychczasowej strony głównej.

## 1. Co jest gotowe — zakres pilotażu
- Osobna podstrona `piloto-transcripciones.html`, bez zmiany `index.html`.
- Osiem dokumentów: `DGS-1546`, `C16-1945`, `C28-1948`, `GR-PRINT-1943-AUG`, `NEW-C08`, `C22-1946`, `BOL-1956-01`, `BOL-1956-02`.
- Dziesięć istniejących plików tekstowych i szesnaście JPG: pobieranie bezpośrednio z istniejących publicznych zasobów GitHub Pages. Nie powielono transkrypcji.
- Wyszukiwanie pełnotekstowe lokalnie w przeglądarce (hiszpańskie znaki diakrytyczne ignorowane przy porównaniu), lista dopasowań i fragment kontekstu.
- Czytnik dwukolumnowy: zdjęcie plus transkrypcja; nawigacja po JPG i częściach transkrypcji.
- Trzy ścieżki: moralidad pública, formación de celadoras, intervención institucional.
- Status dokumentu niekompletnego wyraźnie oznaczony dla `GR-PRINT-1943-AUG`.
- Pilotaż nie jest systemem RAG, nie odpowiada na pytania AI, nie synchronizuje akapitów automatycznie ze stronami i nie przeszukuje całych 93 transkrypcji.

## 2. Właściciele i zakres odpowiedzialności
| Rola | Właściciel | Odpowiedzialność |
|---|---|---|
| Product Owner | Użytkownik | Decyzja, czy i kiedy rozbudowywać oraz publicznie prezentować; priorytety i zakres. |
| Research Owner / tester merytoryczny | Almu | Ocenia praktyczną przydatność, ścieżki tematyczne, terminologię hiszpańską oraz sens materiałów dla badań. Nie musi robić QA technicznego. |
| Owner Friend i redaktor | ChatGPT | Wybór przypadków użycia, wymagania, struktura katalogu, powiązania źródeł, ocena wyników, końcowy raport QA. |
| Integrator techniczny | Antigravity | Gdy skala wymaga automatycznego indeksu, iteracyjnych zmian JS/CSS i prawdziwych testów przeglądarkowych: wdrożenie, regresja i deployment. Nie uruchamiać do każdej drobnej zmiany. |
| Niezależny QA źródłowy | Claude | Tylko gdy dodawane nowe transkrypcje lub występują kontrowersyjne odczyty; porównanie z JPG i jawne niepewności. |
| Końcowy gate publikacji | Product Owner + ChatGPT | Kontrola prywatności, praw do skanów i tekstów autorskich, linków, kompletności, wyników testów. |

## 3. Co robić później — decyzje etapowe
### Etap A — mały test z Almu (bez nowych funkcji)
Niech Almu spróbuje:
1. Znaleźć w tekstach wzmiankę o `playas` i przejść do oryginalnego zdjęcia.
2. Porównać dwie instrukcje z lat czterdziestych na temat moralności publicznej.
3. Otworzyć tekst dotyczący szkolenia celadoras i ocenić, czy pokazanie zdjęcia obok transkrypcji pomaga w pracy.
Zapytać tylko: **co pomogło? czego zabrakło? czy użyłaby tego ponownie?**

### Etap B — decyzja STOP / KEEP / EXPAND
- STOP: Jeśli nie przyspiesza badań, zachować działającą stronę bez rozbudowy.
- KEEP: Jeśli przydatna jest tylko wyszukiwarka, zachować lekkie rozwiązanie i naprawić 1–2 problemy UX.
- EXPAND: Jeśli użyteczne są pełnotekst i czytnik, zlecić Antigravity automatyczne wygenerowanie indeksu ze wszystkich **uprawnionych i sprawdzonych** transkrypcji publicznych. Nie kopiować całego katalogu bez filtrów praw/prywatności.

### Etap C — rozszerzenie techniczne po decyzji EXPAND
- Antigravity: automatyczny indeks tekstowy z wersjonowaniem, kategorie i filtry, wydajna wyszukiwarka po 93 lub mniejszej dopuszczonej liczbie tekstów, testy telefonu i komputera.
- ChatGPT: mapa tematów, ujednolicenie opisów, poziomy pewności i checklista QA; bez generowania bezźródłowych historii.
- Claude: tylko transkrypcje i kontrola trudnych fragmentów; nie powielać gotowego OCR/QA.
- Almu: wskazanie tematów badawczych i kontrola merytoryczna ścieżek; nie wymagać od niej instalowania narzędzi.

## 4. Kryteria jakości dla każdej kolejnej wersji
- Co najmniej 8/8 dokumentów i 10/10 tekstów pilotażu otwiera się poprawnie.
- Wyszukiwanie znajduje słowa we właściwym fragmencie, pokazuje identyfikator i umożliwia przejście do zdjęcia.
- Każdy wynik wskazuje źródło i status kompletności, bez pozornego uzupełniania brakujących stron.
- Wszystkie udostępniane JPG i teksty pochodzą z dopuszczonego zbioru, bez `RESTRICTED` i spornej broszury ONZ.
- Brak nowych publicznych kopii autorskich tekstów o niejasnym statusie; nie stosować automatycznego publicznego eksportu wszystkich Markdown.
- Minimalna regresja: komputer + telefon, zestaw zapytań hiszpańskich ze znakami i bez, sprawdzenie 8 kart i 16 JPG.
- Główna biblioteka i oryginalne materiały Google Drive pozostają bez zmian do czasu osobnej decyzji.

## 5. Zasady pracy (anti-potwór)
- Jeden widoczny produkt, jedna lista decyzji, małe zmiany i test.
- Nie uruchamiać automatycznych agentów działających stale, serwera, bazy, kosztownego RAG ani systemu logowania w tej fazie.
- Wszystkie wnioski i decyzje dopisać do tego pliku handoff, żeby nie ginęły w rozmowach.
