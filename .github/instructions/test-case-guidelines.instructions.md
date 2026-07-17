---
description: "Use when writing, reviewing, or generating test cases, scenariusze testowe, przypadki testowe, Covers required sections, template, filled example, and good/bad practices for manual test case design.",
applyTo: '*/usecases/*.md, */*.use-case.md'
---

# Test Case Guidelines

## Zasady ogólne

- Test case opisuje **scenariusz (plan)** — nie stan wykonania
- Wersja aplikacji, środowisko, wynik rzeczywisty i status należą do **wykonania**, nie do TC
- Wszystkie sekcje są **wymagane**; jeśli nie dotyczą danego przypadku, wpisz `-- POMINIĘTO --`
- Jeden TC = jeden scenariusz (nie łącz kilku przypadków)
- Kroki muszą być **numerowane i atomowe** — każdy krok to jedna akcja

---

## Wymagane sekcje

| Sekcja | Opis |
|--------|------|
| `ID` | Unikalny identyfikator, np. `TC-001` |
| `Tytuł` | Krótki opis: co i przy jakim warunku jest testowane |
| `Priorytet` | `Low` / `Medium` / `High` / `Critical` |
| `Autor` | Imię i nazwisko osoby tworzącej TC |
| `Data utworzenia` | Format `YYYY-MM-DD` |
| `Warunki wstępne` | Stan systemu i danych przed wykonaniem |
| `Dane testowe` | Konkretne wartości wejściowe |
| `Kroki testowe` | Numerowana lista akcji |
| `Oczekiwany rezultat` | Dokładny, mierzalny wynik |
| `Powiązane wymagania` | ID wymagania z PRD / user story |

---

## Szablon

```
ID:
Tytuł:
Priorytet:         [Low / Medium / High / Critical]
Autor:
Data utworzenia:

Warunki wstępne:

Dane testowe:

Kroki testowe:
  1.
  2.
  3.

Oczekiwany rezultat:

Powiązane wymagania:
```

---

## Przykładowo wypełniony szablon

```
ID: TC-012
Tytuł: Logowanie z poprawnymi danymi
Priorytet: Critical
Autor: Anna Kowalska
Data utworzenia: 2026-07-17

Warunki wstępne:
  - Użytkownik posiada aktywne konto w systemie
  - Strona logowania jest dostępna

Dane testowe:
  - Login: test@example.com
  - Hasło: Test123!

Kroki testowe:
  1. Otwórz stronę /login
  2. Wprowadź login: test@example.com
  3. Wprowadź hasło: Test123!
  4. Kliknij przycisk "Zaloguj"

Oczekiwany rezultat:
  Użytkownik zostaje przekierowany na stronę /dashboard.
  W nagłówku widoczna jest nazwa użytkownika "Anna Kowalska".

Powiązane wymagania: PRD-UC-03
```

---

## Checklista — dobre i złe praktyki

### Dobre praktyki
- [ ] Jeden TC testuje dokładnie jeden scenariusz
- [ ] Oczekiwany rezultat jest konkretny i mierzalny
- [ ] Kroki są numerowane i każdy opisuje jedną akcję
- [ ] Dane testowe są wyodrębnione z kroków
- [ ] Tytuł zawiera: co jest testowane + przy jakim warunku
- [ ] Warunki wstępne są kompletne — test jest powtarzalny
- [ ] TC jest zrozumiały dla osoby, która nie pisała aplikacji

### Złe praktyki
- [ ] "Kliknij i sprawdź czy działa" — brak konkretnego oczekiwanego rezultatu
- [ ] Kroki zbyt ogólne: "Zaloguj się" zamiast rozpisanych akcji
- [ ] Brak warunków wstępnych — wynik zależy od losowego stanu systemu
- [ ] Jeden TC pokrywa wiele niezależnych scenariuszy
- [ ] Tytuł: "Test logowania 3" — nie mówi nic o scenariuszu
- [ ] Wersja aplikacji lub środowisko w TC (należą do wykonania)
