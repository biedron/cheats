# Cheklista

### Ogólne
- [ ] zmiana hasla root na stacji
- [ ] backup katalogu z aplikajcą z serwera www na osobna stacje
- [ ] zmiana hasel domyślnych podanych w scenariuszu i rekonfiguracja aplikacji
- [ ] sprawdzenie kluczy ssh
- [ ] sprawdzenie crona

### Webaplikacja
- [ ] Przeglad kodu aplikacji w php
 - [ ] command injection (w 2 (?)miejscach)
 - [ ] automatyczne dumpy wpisywanych hasel
 - [ ] sql injections w kodzie (zakomentowane linijki z poprawnym kodem)
 - [ ] sanityzacja inputów pod kątem SSTI, XSS (jest funckcja czyszcząca - clearString($value))
 - [ ] link do strony phishingowej w glownym menu aplikacji
 - [ ] mozliwosc dodawania ujemnych cen w koszyku
 - [ ] mass assignment przy zakladaniu konta i tworzenie kont admina z poziomu usera
 - [ ] potencjalnie nabijanie kasy przy zapraszaniu kont userów
 - [ ] coś z historią zamówień
