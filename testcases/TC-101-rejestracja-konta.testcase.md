# TC-101 — Pomyślna rejestracja nowego konta z poprawnymi danymi

**ID:** TC-101  
**Tytuł:** Pomyślna rejestracja nowego konta z poprawnymi danymi  
**Priorytet:** High  
**Autor:** Mateusz Kulesza  
**Data utworzenia:** 2026-07-17  

---

## Warunki wstępne

- Użytkownik nie jest zalogowany
- Strona rejestracji (S-05) jest dostępna
- Baza danych jest w stanie normalnym (brak duplikatów e-maila)

---

## Dane testowe

| Pole | Wartość |
|------|---------|
| Imię i nazwisko | Jan Kowalski |
| E-mail | jan.kowalski@example.com |
| Hasło | SecurePass123! |
| Potwierdzenie hasła | SecurePass123! |

---

## Kroki testowe

1. Przejdź na stronę rejestracji
2. Wypełnij pole "Imię i nazwisko" wartością: Jan Kowalski
3. Wypełnij pole "E-mail" wartością: jan.kowalski@example.com
4. Wypełnij pole "Hasło" wartością: SecurePass123!
5. Wypełnij pole "Potwierdź hasło" wartością: SecurePass123!
6. Kliknij przycisk "Zarejestruj się"

---

## Oczekiwany rezultat

- Konto zostało utworzone w systemie
- E-mail weryfikacyjny wysłany na jan.kowalski@example.com z linkiem aktywacyjnym
- Konto jest w stanie **oczekującym na aktywację** (nieaktywne) — login niemożliwy do czasu potwierdzenia e-maila
- Wyświetlony komunikat: "Rejestracja pomyślna. Sprawdź e-mail, aby aktywować konto"
- Użytkownik został przekierowany na stronę potwierdzenia rejestracji lub logowania

---

## Powiązane wymagania

- **REG-01:** Użytkownik może zarejestrować konto podając: imię, nazwisko, adres e-mail, hasło, potwierdzenie hasła
- **REG-03:** Po rejestracji system wysyła e-mail weryfikacyjny. Konto jest aktywne dopiero po kliknięciu linku

---

## UWAGI DLA ANALITYKA

Część oczekiwań w "Oczekiwanym rezultacie" wynika wprost z REG-01 i REG-03:
- ✅ Konto utworzone, e-mail weryfikacyjny, stan konta — specyfikowane w wymaganiach
- ⚠️ Komunikat i przekierowanie — logika aplikacji, niespecyfikowana jawnie w REG-01/03
  - Testolog uzupełnił te oczekiwania na podstawie standardowych praktyk UX
  - Przed wykonaniem TC zalecane potwierdzenie z PM/DEV rzeczywistych komunikatów i przepływu
