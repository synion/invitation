# PROGRESS — Zaproszenie na 9 urodziny

## Stan: GOTOWE ✅
- Strona na żywo: https://synion.github.io/invitation/
- Hosting: GitHub Pages (branch `main`, katalog `/`), HTTPS wymuszony.
- Personalizacja imienia: parametr URL `?dla=Imię%20Nazwisko` (fallback: `?imie=`, `?name=`, `?goscie=`).
- Weryfikacja: HTTP 200, treść zawiera imię/licznik/telefon/ArcadeBee; sandbox claude.ai usunięty.

## Zadanie
Postawić za darmo interaktywne, spersonalizowane zaproszenie (imię gościa) na 9 urodziny.
Gotowy design przyszedł jako Claude Artifact — trzeba go było odkleić od sandboxa i wystawić publicznie.

## Rozważane alternatywy

### Decyzja 1 — Hosting

**Wybrane: GitHub Pages.**
Repo `synion/invitation` już istniało, dostęp push był, więc całość dało się postawić bez pracy usera.
Darmowe, stabilne, HTTPS, adres `synion.github.io/invitation`.

- **Netlify Drop / tiiny.host** — plusy: drag&drop bez konta; minusy: user musi zrobić to sam,
  domena bardziej losowa, przy zmianie treści trzeba wgrywać ręcznie. Odrzucone: skoro repo już
  jest i mam dostęp, GitHub Pages daje ten sam efekt + wersjonowanie git, zero pracy usera.
- **Płatna domena `.pl` + subdomeny per gość** (pierwotny pomysł usera `jan.invitation.pl`) —
  odrzucone: nie jest darmowe (domena płatna) ani „tymczasowe", wymaga wildcard DNS + Cloudflare
  Worker, a GitHub Pages nie obsługuje osobnej subdomeny per gość. Armata na muchę.

### Decyzja 2 — Personalizacja imienia

**Wybrane: parametr URL `?dla=` (jeden plik).**
Tak był już zbudowany artifact + ma wbudowany generator linków dla rodzica. Dodanie gościa =
tylko nowy link, nic nie wgrywamy.

- **Osobny plik/link per dziecko** (`/jan-kowalski`) — plusy: czysty adres bez `?`; minusy:
  regeneracja i push przy każdym nowym dziecku. Odrzucone: parametr działa od ręki i jest już gotowy.
- **Subdomena per dziecko** — odrzucone jak w Decyzji 1 (płatne + skomplikowane).

### Decyzja 3 — Kod ze sandboxa

Artifact z claude.ai miał na górze harness `__FRAME_PREAMBLE` (vite preload, postMessage do
rodzica-ramki). Poza claude.ai jest bezużyteczny/szkodliwy. Wyodrębniono czysty content do
samodzielnego `index.html`; logika i style usera 1:1.

## Aktualizacje (v2) — uwagi rodzica
- Dodane imię solenizanta **Aleksander** w tytule (pod „9") i w powitaniu.
- Separatory w imieniu gościa: `?dla=jan_kowalski` → „Jan Kowalski" (`_`/`+` → spacja
  + kapitalizacja pierwszych liter, działa też z polskimi znakami: `Łukasz Żabka`).
- Generator linków **ukryty dla gości**; dostępny tylko przez `?gen=1` (furtka rodzica).
- Zweryfikowano na żywo (curl) + logika imienia przetestowana w Node.

## TODO / opcjonalne
- [ ] Podmiana/dodanie finalnych grafik z „claude design", gdy będą gotowe.
- [ ] (opcja) Przycisk potwierdzenia jako SMS zamiast telefonu — instrukcja w README.
- [ ] (opcja) Rozesłać linki gościom (generator w stopce strony).
