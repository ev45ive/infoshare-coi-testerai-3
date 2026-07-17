---
description: "Anonimizuj dane w pliku — pyta o plik, typy danych i sposób anonimizacji (nadpisanie lub skrypt Python)"
name: "Anonimizuj dane"
argument-hint: "Ścieżka do pliku lub opis zadania"
agent: "agent"
tools: [read_file, create_file, run_in_terminal]
---

Przeprowadź anonimizację danych w pliku. Wykonaj poniższe kroki **po kolei** — nie przechodź do następnego bez odpowiedzi użytkownika.

## Krok 1 — Wybór pliku

Zapytaj użytkownika:
> „Który plik chcesz zanonimizować? Podaj ścieżkę do pliku."

Odczytaj wskazany plik i wyświetl krótki podgląd (pierwsze 20 linii), aby potwierdzić, że to właściwy plik.

## Krok 2 — Typy danych do anonimizacji

Zapytaj użytkownika:
> „Jakie typy danych chcesz zanonimizować? Możesz wybrać kilka lub wpisać własne.
> 
> Domyślnie anonimizuję:
> - **Dane osobowe** — imiona, nazwiska, adresy, numery PESEL, e-maile, telefony
> - **Dane finansowe** — numery kart kredytowych, numery kont bankowych, kwoty powiązane z osobą
> 
> Czy chcesz zmienić lub rozszerzyć tę listę?"

Zapamiętaj potwierdzony zestaw typów danych.

## Krok 3 — Sposób anonimizacji

Zapytaj użytkownika:
> „W jaki sposób chcesz przeprowadzić anonimizację?
> 
> A) **Zmodyfikuj plik bezpośrednio** — dane zostaną zastąpione w kopii oryginalnego pliku (zapisuję jako `<nazwa>_anonymized.<rozszerzenie>`)
> B) **Utwórz skrypt Python** — wygeneruję plik `.py`, który po uruchomieniu automatycznie zanonimizuje dane i zapisze wynik

Wpisz A lub B."

## Krok 4 — Wykonanie

### Jeśli użytkownik wybrał A (zmodyfikuj plik):

1. Przeanalizuj zawartość pliku pod kątem wybranych typów danych.
2. Zastąp wrażliwe dane odpowiednimi placeholderami, np.:
   - Imię/nazwisko → `[IMIĘ]`, `[NAZWISKO]`
   - E-mail → `[EMAIL]`
   - Telefon → `[TELEFON]`
   - PESEL → `[PESEL]`
   - Numer konta → `[NUMER_KONTA]`
   - Numer karty → `[NUMER_KARTY]`
   - Adres → `[ADRES]`
3. Zapisz wynik do nowego pliku o nazwie `<oryginalna_nazwa>_anonymized.<rozszerzenie>` w tym samym katalogu.
4. Podsumuj, ile i jakich danych zostało zanonimizowanych.

### Jeśli użytkownik wybrał B (skrypt Python):

1. Wygeneruj skrypt `anonymize_<oryginalna_nazwa>.py` w tym samym katalogu co plik wejściowy.
2. Skrypt powinien:
   - Wczytać wskazany plik
   - Używać wyrażeń regularnych (`re`) do wykrywania wybranych typów danych
   - Zastępować je placeholderami (jak wyżej)
   - Zapisywać wynik do `<oryginalna_nazwa>_anonymized.<rozszerzenie>`
   - Wyświetlać podsumowanie liczby zastąpień
3. Pokaż użytkownikowi kod skryptu przed zapisaniem.
4. Zapisz skrypt.

## Krok 5 — Podsumowanie

Po zakończeniu poinformuj użytkownika:
- Jakie dane zostały zanonimizowane (typy + liczba wystąpień)
- Gdzie zapisano wynikowy plik
- Czy wykryto dane, których nie udało się zanonimizować automatycznie (wymagające ręcznej weryfikacji)
