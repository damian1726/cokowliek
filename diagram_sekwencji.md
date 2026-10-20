``` mermaid
sequenceDiagram
    participant G as Gracz
    participant B as Bohater
    participant S as System gry
    participant P as Poziom gry

    G->>S: Uruchom gre
    activate S
    S->>P: Wczytaj poziom
    P-->>S: Poziom gotowy
    S-->>G: Rozpocznij gre
    deactivate S

    G->>B: Sterowanie WASD
    activate B
    B->>S: Ruch postaci
    activate S
    S->>P: Sprawdz kolizje
    P-->>S: Wynik kolizji
    S-->>B: Aktualizuj pozycje
    deactivate S

    B->>S: Zebranie monety
    activate S
    S->>S: Dodaj punkty
    S-->>B: Aktualizacja wyniku
    deactivate S

    B->>S: Podniesienie klucza
    activate S
    S->>S: Zapisz klucz
    S-->>B: Klucz zdobyty
    deactivate S

    B->>S: Dotarcie do drzwi
    activate S
    S->>S: Sprawdz klucz

    alt Gracz ma klucz
        S->>P: Otworz drzwi
        P-->>S: Drzwi otwarte
        S-->>G: Poziom ukonczony
    else Brak klucza
        S-->>G: Znajdz klucz
    end
    deactivate S
    deactivate B

    alt Sa kolejne poziomy
        G->>S: Przejdz dalej
        S->>P: Wczytaj kolejny poziom
        P-->>S: Nowy poziom gotowy
        S-->>G: Rozpocznij poziom
    else Ukonczono poziom trzeci
        S-->>G: Wygrana
    end
```
