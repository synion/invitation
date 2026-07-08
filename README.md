# Zaproszenie na 9 urodziny 🎉🕹️

Interaktywne zaproszenie (styl arcade/neon, motyw ArcadeBee) postawione na GitHub Pages.

**Adres strony:** https://synion.github.io/invitation/

## Jak wysłać spersonalizowane zaproszenie

Każdy gość widzi swoje imię, bo imię przekazujemy w linku przez parametr `?dla=`.

Wzór linku (spację zapiszesz jako `%20` **albo po prostu `_`**):

```
https://synion.github.io/invitation/?dla=jan_kowalski
```

`jan_kowalski` wyświetli się jako **Jan Kowalski** — podkreślnik zamienia się
w spację, a pierwsze litery robią się wielkie automatycznie. Przykłady:

| Wpiszesz w link | Gość zobaczy |
|------|------------------|
| `?dla=jan_kowalski` | **Jan Kowalski** |
| `?dla=anna_nowak` | **Anna Nowak** |
| `?dla=Jan%20Kowalski` | **Jan Kowalski** |

### Najprościej — ukryty generator (tylko dla Ciebie)

Generator jest **niewidoczny dla gości**. Ty otwierasz go tajnym adresem:

👉 **https://synion.github.io/invitation/?gen=1**

1. Wejdź na link z `?gen=1` powyżej — generator otworzy się od razu.
2. Wpisz imię i nazwisko gościa → link tworzy się sam.
3. **Kopiuj** → wklej do SMS / WhatsApp i wyślij.

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
