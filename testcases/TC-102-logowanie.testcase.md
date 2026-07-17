# TC-102 — Pomyślne logowanie z poprawnymi danymi

**ID:** TC-102  
**Tytuł:** Pomyślne logowanie z poprawnymi danymi  
**Priorytet:** Critical  
**Autor:** Mateusz Kulesza  
**Data utworzenia:** 2026-07-17  

---

## Warunki wstępne

- Użytkownik posiada aktywne konto w systemie (e-mail potwierdzony)
- Użytkownik nie jest zalogowany
- Strona logowania (S-04) jest dostępna

---

## Dane testowe

| Pole  | Wartość                       |
|-------|-------------------------------|
| E-mail | jan.kowalski@example.com     |
| Hasło  | SecurePass123!               |

---

## Kroki testowe

1. Przejdź na stronę logowania `/login`
2. Wypełnij pole "E-mail" wartością: jan.kowalski@example.com
3. Wypełnij pole "Hasło" wartością: SecurePass123!
4. Kliknij przycisk "Zaloguj się"

---

## Oczekiwany rezultat

- Użytkownik zostaje zalogowany
- Użytkownik zostaje przekierowany na stronę główną `/`
- Sesja użytkownika jest aktywna

---

## Powiązane wymagania

- **REG-04:** Użytkownik może zalogować się e-mailem i hasłem.
