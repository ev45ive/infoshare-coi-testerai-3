---
description: "Interaktywne tworzenie manualnych przypadków testowych (test cases) krok po kroku: wybór dokumentu wymagań, sekcji, wypełnienie szablonu TC i zapis do pliku."
name: "Utwórz Test Case"
argument-hint: "Opcjonalnie: ID lub nazwa wymagania do pokrycia"
agent: "agent"
tools: []
---

Twoim zadaniem jest interaktywne przeprowadzenie użytkownika przez proces tworzenia manualnego przypadku testowego zgodnie z [wytycznymi TC](.github/instructions/test-case-guidelines.instructions.md).

## Zasady

- Tworzysz wyłącznie **testy manualne** — bez kodu i automatyzacji.
- Ściśle przestrzegaj szablonu i wymaganych sekcji z wytycznych.
- Prowadź proces **krok po kroku**, czekaj na odpowiedź użytkownika przed przejściem dalej.
- Nie wypełniaj sekcji na podstawie domysłów — dopytaj, jeśli brakuje informacji.
- Zapisz szkic do pliku `./testcases/<ID>-<nazwa>.testcase.md` przed rozpoczęciem iteracji.

---

## Krok 1 — Wybór dokumentu wymagań

Zapytaj użytkownika:

> Z którego dokumentu chcesz pobrać wymagania dla tego test case?  
> (podaj ścieżkę lub nazwę pliku, np. `exercises/01-prompts/ShopEasy-PRD.requirements.md`)

Poczekaj na odpowiedź. Nie szukaj plików samodzielnie.

---

## Krok 2 — Wybór sekcji lub wymagania

Po otrzymaniu dokumentu zapytaj:

> Którą sekcję lub konkretne wymaganie (np. US-03, FR-07) ma pokrywać ten test case?

Poczekaj na odpowiedź.

---

## Krok 3 — Szkic TC

Na podstawie zebranych informacji wypełnij szablon:

```
ID:               (zaproponuj kolejny wolny numer, np. TC-001)
Tytuł:            (co jest testowane + przy jakim warunku)
Priorytet:        [Low / Medium / High / Critical]
Autor:            (zapytaj użytkownika o imię i nazwisko, jeśli nieznane)
Data utworzenia:  (dzisiejsza data)

Warunki wstępne:

Dane testowe:

Kroki testowe:
  1.
  2.
  3.

Oczekiwany rezultat:

Powiązane wymagania:
```

Zapisz szkic do pliku `./testcases/<ID>-<nazwa>.testcase.md`, gdzie:
- `<ID>` to np. `TC-001`
- `<nazwa>` to skrócona nazwa scenariusza (bez polskich znaków, słowa rozdzielone myślnikiem)

---

## Krok 4 — Iteracyjne doprecyzowanie

### 4a. Sekcje nagłówkowe
Przedstaw użytkownikowi wypełnione sekcje: `ID`, `Tytuł`, `Priorytet`, `Warunki wstępne`, `Dane testowe`.  
Zapytaj:

> Czy akceptujesz te sekcje, czy chcesz coś zmienić?

Wprowadź poprawki, jeśli są.

### 4b. Kroki testowe
Zaproponuj listę kroków — numerowanych, atomowych (jedna akcja = jeden krok).  
Jeśli nie masz wystarczających informacji do opisania kroków, zapytaj użytkownika o szczegóły przepływu.  
Zapytaj:

> Czy akceptujesz kroki, czy chcesz je zmodyfikować?

### 4c. Oczekiwany rezultat
Zaproponuj konkretny, mierzalny oczekiwany rezultat.  
Zapytaj:

> Czy oczekiwany rezultat jest poprawny?

---

## Krok 5 — Zapis końcowy

Po akceptacji wszystkich sekcji zaktualizuj plik `./testcases/<ID>-<nazwa>.testcase.md` finalną wersją TC.  
Potwierdź: „TC zapisany: `./testcases/<ID>-<nazwa>.testcase.md`"

---

## Krok 6 — Kontynuacja

Zapytaj:

> Czy chcesz powtórzyć cały proces dla kolejnego test case?

Jeśli tak — wróć do **Kroku 1** (dokument może być ten sam lub inny).
