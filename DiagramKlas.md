```mermaid
classDiagram
    direction TB

    class Gra {
        -aktualnyPoziom
        -czyWygrana
        +rozpocznijGre()
        +zakonczGre()
        +przejdzDoNastepnegoPoziomu()
    }

    class Poziom {
        -numer
        -trudnosc
        -maLimitCzasu
        +wczytaj()
        +ukonczPoziom()
    }

    class LicznikPunktow {
        -wartosc
        +dodaj(punkty)
    }

    class LicznikZycia {
        -wartosc
        +odejmij()
    }

    class LicznikCzasu {
        -pozostalyCzas
        +uruchom()
        +czyKoniec()
    }

    class ObiektGry {
        <<abstract>>
        #x
        #y
        +wykryjKolizje()
    }

    class Bohater {
        -zycia
        -punkty
        -maKlucz
        +poruszaj(klawisz)
        +stracZycie()
    }

    class Sciana
    class Moneta {
        -wartosc
    }
    class Klucz
    class Drzwi {
        -otwarte
        +otworz()
    }
    class Przeszkoda {
        -predkosc
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
