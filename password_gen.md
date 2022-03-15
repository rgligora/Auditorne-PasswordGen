# Generator lozinki

## 1. Zadatak
Zadatak je implementirati generator lozinki koji preko argumenata komandne linije prima skup znakova koje smije koristiti kod generiranja.
Program prima sa standardnog ulaza veličine lozinki tako dugo dok se ne upiše "quit" ili skraćeno "q". Za svaku danu veličinu program ispisuje
na standardni izlaz novo generiranu slučajnu lozinku te veličine. Brojeve koje primate sa standardnog ulaza ne morate dodatno provjeravati.

U klasu `PasswordGenerator`, u paketu *hr.fer.oop.password.gen*, enkapsulirajte potrebne funkcionalnosti za generiranje lozinki, a u klasu `Main`, u paketu *hr.fer.oop.password*, smjestite statičku metodu `main` i potrebne funkcionalnosti za čitanje argumenata s komandne linije i veličini lozinki sa standardnog ulaza.

### `PasswordGenerator`
Klasa `PasswordGenerator` mora sadržavati samo jednu javnu metodu (osim konstruktora), `generirajLozinku(int velicina)` koja generira lozinku dane veličine, a preko
konstruktora primati skup znakova koji je tipa `String`.

### Primjer koda
```Java
...
// Nadodati argumente konstruktoru PasswordGenerator klase i
// čitanje argumenata s komandne linije
PasswordGenerator generator = new PasswordGenerator(...);
Scanner sc = new Scanner(System.in);
while(sc.hasNext()) {
    String line = sc.nextLine();
    if ("quit".equals(line) || "q".equals(line)) {
        System.out.println("Gotovo!");
        break;
    }
    int velicinaLozinke = Integer.parseInt(line.trim());
    String lozinka = generator.generirajSlucajnuLozinku(velicinaLozinke);
    System.out.println("Novo generirana lozinka: " + lozinka);
}
sc.close();
```

## 2. Zadatak
Izmijenite generator tako da preko argumenata sa komandne linije prima skupove znakova, a preko standardnog ulaza prima koliko se znakova iz kojeg skupa mora pojaviti u lozinci.
Npr. ako primimo sljedeće argumente programa `"123 abc !?"`. Na standardnom ulazu očekujemo 3 broja odvojena razmacima koji određuju koliko se iz svakog skupa pojavljuje znakova, npr.
`"2 5 1"`, bi značilo da se iz skupa `123` pojavljuje dva znaka, iz skupa `abc` pet znakova i iz skupa `!?` jedan znak. Znakova iz pojedinih skupova smiiju se ponavljati.
Ako koristite pomoćne metode za upravljanje poljima smjestite ih kao statičke metode u klasu `ArrayUtil` u paket *hr.fer.oop.password.util*.
Promijenite metodu `generirajLozinku` da prima polje cijelih brojeva u kojem je sadržano potreban broj znakova za svaki od skupova.


## Rješenja
Rješenja su vam dana u *ZIP* datoteci koju raspakirate u **svoj Eclipse workspace**. Nakon raspakiranja direktorij u kojem vam je raspakirano rješenje *importajte* u Eclipse kao **Maven projekt**.

## Pitanja i problemi
Za bilo kakva pitanja ili probleme oko zadataka možete se javiti na `mihael.kovac@fer.hr`.