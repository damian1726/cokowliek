```mermaid
flowchart TD
    A((START)) --> B[Uruchomienie gry]
    B --> C[Wyświetlenie menu głównego]
    C --> D[Kliknięcie START]
    D --> E[Wczytanie poziomu 1]

    E --> F[Poruszanie bohaterem W A S D]
    F --> G{Kolizja ze ścianą?}
    G -->|Tak| F
    G -->|Nie| H{Znaleziono monetę?}
    H -->|Tak| I[Dodanie punktów]
    H -->|Nie| J{Znaleziono klucz?}
    I --> J
    J -->|Tak| K[Zebranie klucza]
    J -->|Nie| L{Kontakt z przeciwnikiem lub przeszkodą?}
    K --> L
    L -->|Tak| M[Utrata życia]
    L -->|Nie| N{Czy pozostały życia?}
    M --> N
    N -->|Nie| O[Wyświetlenie przegranej]
    N -->|Tak| P{Czy dotarto do drzwi?}
    P -->|Nie| F
    P -->|Tak| Q{Czy gracz ma klucz?}
    Q -->|Nie| F
    Q -->|Tak| R{Który poziom?}

    R -->|1| S[Ukończenie poziomu 1]
    S --> T[Wczytanie poziomu 2]
    T --> U[Ruchome przeszkody]
    U --> F

    R -->|2| V[Ukończenie poziomu 2]
    V --> W[Wczytanie poziomu 3]
    W --> X[Uruchomienie odliczania czasu]
    X --> Y[Labirynt z przeciwnikiem]
    Y --> Z{Czy czas się skończył?}
    Z -->|Tak| O
    Z -->|Nie| F

    R -->|3| AA[Ukończenie poziomu 3]
    AA --> AB[Wyświetlenie zwycięstwa]

    O --> AC((KONIEC))
    AB --> AC
