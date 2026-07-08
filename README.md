# Zaproszenie na 9 urodziny 🎉🕹️

Interaktywne zaproszenie (styl arcade/neon, motyw ArcadeBee) postawione na GitHub Pages.

**Adres strony:** https://synion.github.io/invitation/

## Jak wysłać spersonalizowane zaproszenie

Każdy gość widzi swoje imię, bo imię przekazujemy w linku przez parametr `?dla=`.

Wzór linku:

```
https://synion.github.io/invitation/?dla=Imię%20Nazwisko
```

Spacje w linku zapisuje się jako `%20`. Przykłady:

| Gość | Link do wysłania |
|------|------------------|
| Jan Kowalski | `https://synion.github.io/invitation/?dla=Jan%20Kowalski` |
| Anna Nowak | `https://synion.github.io/invitation/?dla=Anna%20Nowak` |

### Najprościej — generator w środku strony

Nie trzeba ręcznie sklejać linków. Na dole zaproszenia jest przycisk
**„⚙ Generator zaproszeń dla rodzica"**:

1. Wejdź na https://synion.github.io/invitation/
2. Kliknij **⚙ Generator zaproszeń dla rodzica**.
3. Wpisz imię i nazwisko gościa → link tworzy się sam.
4. **Kopiuj** → wklej do SMS / WhatsApp i wyślij.

Powtórz dla każdego dziecka. Jeśli ktoś dojdzie później — po prostu wygeneruj
kolejny link, nic nie trzeba wgrywać.

## Co jest w środku

- Ekran startowy „Insert coin" → przycisk **Start** odsłania szczegóły.
- Imię gościa z linku (`?dla=`), z bezpiecznym limitem długości.
- Licznik do **17 lipca 2026, 17:00**.
- Data, miejsce (ArcadeBee, Galeria Sfera) + link do nawigacji Google Maps.
- Przycisk potwierdzenia obecności → dzwoni na **730 707 771** (`tel:`).
- Animowane pikselowe pszczółki (respektują „reduced motion").

## Jak zmienić treść

Cała strona to jeden plik: [`index.html`](index.html). Edytuj, `git commit`,
`git push` — GitHub Pages odświeży się w ~1 min.

Częste zmiany:
- **Rok/godzina licznika:** w `<script>` linia `var target = new Date(2026, 6, 17, 17, 0, 0)`
  (uwaga: miesiąc liczony od zera, `6` = lipiec).
- **Numer telefonu:** `href="tel:+48730707771"`.
- **Potwierdzenie SMS zamiast telefonu:** zmień `tel:+48730707771`
  na `sms:+48730707771?&body=Potwierdzam%20obecność`.
