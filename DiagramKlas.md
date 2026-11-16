```mermaid
classDiagram
    direction TB

    class Gra {
        -int aktualnyPoziom
        -bool czyWygrana
        +rozpocznijGre()
        +zakonczGre()
        +przejdzDoNastepnegoPoziomu()
    }

    class Poziom {
        -int numer
        -int trudnosc
        -bool maLimitCzasu
        +wczytaj()
        +ukonczPoziom()
    }

    class LicznikPunktow {
        -int wartosc
        +dodaj(punkty)
    }

    class LicznikZycia {
        -int wartosc
        +odejmij()
    }

    class LicznikCzasu {
        -float pozostalyCzas
        +uruchom()
        +czyKoniec() bool
    }

    class ObiektGry {
        <<abstract>>
        #float x
        #float y
        +wykryjKolizje()
    }

    class Bohater {
        -int zycia
        -int punkty
        -bool maKlucz
        +poruszaj(klawisz)
        +stracZycie()
    }

    class Sciana
    class Moneta {
        -int wartosc
    }
    class Klucz
    class Drzwi {
        -bool otwarte
        +otworz()
    }
    class Przeszkoda {
        -float predkosc
        +poruszaj()
    }
    class Przeciwnik {
        +gon()
    }

    Gra "1" *-- "3" Poziom
    Gra "1" *-- "1" Bohater
    Gra "1" *-- "1" LicznikPunktow
    Gra "1" *-- "1" LicznikZycia
    Poziom "1" o-- "0..1" LicznikCzasu : poziom 3
    Poziom "1" *-- "*" ObiektGry

    ObiektGry <|-- Bohater
    ObiektGry <|-- Sciana
    ObiektGry <|-- Moneta
    ObiektGry <|-- Klucz
    ObiektGry <|-- Drzwi
    ObiektGry <|-- Przeszkoda
    Przeszkoda <|-- Przeciwnik

    Bohater ..> Klucz : zbiera
    Bohater ..> Drzwi : otwiera
```
