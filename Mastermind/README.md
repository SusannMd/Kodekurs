# Mastermind 🧠

I dette kurset skal dere lære dere en introduksjon til C++, og hvordan man kan lage spillet Mastermind ved å bruke programmering.

## Litt bakgrunnsinformasjon om spillet

Spillet går ut på at en spiller setter opp en skjult kombinasjon (kode), og så skal den andre spilleren forsøke å gjette hva denne kombinasjonen er. Etter hvert gjett skal spilleren få tilbakemelding på antall riktige man har hvor riktig farge/ bokstav er på riktig plass og hvor mange brikker som er riktig farge/bokstav og er feil plassert. Målet med spillet er å gjette koden ved å bruke færrest mulige forsøk. I denne implementasjonen av koden er det datamaskinen som skal sette opp en kode for brukeren, også skal vi kunne gjette hvordan det brukes.

### Oppgave 1

Lag en funksjon som genererer en tilfeldig streng Første funksjon vi ønsker å lage er en funksjon som lager en tilfeldig streng. Streng i dette tilfellet representerer kombinasjonen som er selve koden. Dette skal gjøres i funksjonen std::string randomizeString(int n, char nedre, char ovre). Dette definerer at funksjonen returnerer en streng, tar inn et heltall (int) og to bokstaver (char). Int er antall bokstaver i koden og bokstavene er nedre og øvre grense på hvilke bokstaver man kan gjette. I senere kode når vi skal teste den ønsker vi å kjøre int=4, nedre=A og øvre=F, men dette kan dere velge fritt ved å se i switchen etter alternativ 1 som er oppgave 1a). Når du har fått til denne oppgaven skal den skrive ut tilfeldige bokstaver.

Nyttig å vite: char-aritmetikk
En bokstav er egentlig en tallverdi. Vi kan dermed bruke regneoperasjoner på tallverdiene, hvor hver bokstav representerer tilhørende verdi (ASCII-verdi). Derfor kan man for eksempel finne den n-te bokstaven i alfabetet (A-Z) ved å bruke koden. I denne oppgaven ønsker vi å benytte oss av rand()-funksjonen.

```cpp
#include <iostream> //Benyttes til cout, cin
#include <string> //Benyttes til string

std::string randomizeString(int n, char nedre, char ovre)
{
    std::string str;
    for (int i = 0; i < 0/*TODO*/; ++i)
    {
        //str += /*TODO*/;
    }
    return str;
}
std::cout<<randomizeString(4,'A','F');
```

### Oppgave 2

Lag en funksjon som genererer streng fra input I denne oppgaven skal du definere funksjonen std::string readInputToString(int n, char nedre, char ovre). Denne skal returnere en string av lengde n, hvor den er begrenset av øvre og nedre grense for hvilke tegn som er tillatt. Denne strengen som skal returneres skal benytte konsollinput. Merk her at vi ønsker å gjøre om alle bokstaver store bokstaver. Denne koden gir deg mulighet til å hente inn bokstaver, du skal derfor finne ut hvordan du sjekker om disse er innenfor og legge de til i strengen str før den returneres.

```cpp
#include <locale> //Benyttes til funksjonen toupper()
#include <iostream> //Benyttes til cout, cin
#include <string> //Benyttes til string

std::string readInputToString(int n, char nedre, char ovre)
{
    std::string str;
    char bokstav;
    int storrelse=0;
    while(storrelse<n)
    {
        std::cout << "Skriv inn en bokstav: ";
        std::cin>>bokstav;
        bokstav=toupper(bokstav);
        /*TODO*/
        storrelse +=1; //Denne verdien skal økes hver gang man legger til en bokstav i strengen.
    }
    return str;
}
std::string str=readInputToString(4,'A','F');
std::cout<<str;
```

### Oppgave 3

Lag en funksjon som teller hvor mange ganger en char inntreffer i en string. Denne funksjonen returnerer antallet og tar inn linjen som skal sjekkes og bokstaven man vil telle. Når denne fungerer vil cellen nedenfor funksjonen skrive ut tallet 5.

```cpp
int countChar(std::string linje, char chr) {
    int count=0;

    /*TODO*/

    return count;
}
std::cout<<countChar("this is a line with 5 i",'i');
```

### Oppgave 4

Lag en funksjon som sjekker om en person sier ja til å fortsette spillet. Dette gjøres med konsollinput. Strengen som tas inn skal være spørsmålet som man skal svare ja eller nei på.

```cpp
bool askYesNoQuestion(std::string questionMessage)
//Returnere true når inputen fra brukeren er 'y', ellers false
{
    /*TODO*/
    return true; //Denne linjen skal endres, returnerer nå standard true
}
std::cout<<askYesNoQuestion("Vil du fortsette spillet?");
Oppgave 5
Lag en funksjon som sjekker om man har riktig bokstav på riktig plass.

int checkCharactersAndPosition(std::string guess,std::string code){
    int riktig_plass{0};
    /*TODO*/
    return riktig_plass;
}
std::cout<<checkCharactersAndPosition("ABCD","FECA");
```

For å ha en funksjon som sjekker om man har riktig bokstav, og ikke riktig plass kan man bruke koden nedenfor. Om man ønsker en annen løsning kan man legge til en ny celle og lage egen kode. Hvis man ikke gjør dette velger du cellen nedenfor og kjører ctrl+enter slik at den får et tall ved siden av.

```cpp
int checkCharacters(std::string guess,std::string code){
    int total{0};
    for (char x:"ABCDEF") {
        total += std::min(countChar(guess,x),countChar(code,x));
    }
    total -= checkCharactersAndPosition(guess,code);
    return total;
}
```

### Oppgave 6

Nå som vi har laget en del verktøy, kan disse settes sammen til et ferdig spill. Det hele skal vi nå gjøre i funksjonen playMastermind().

```cpp
void playMastermind(){
    constexpr int size = 4;
    constexpr int letters = 6;
    constexpr char startLetter = 'A';
    constexpr int maxTries = 6;

    bool playAgain = false;
    do {
        std::string code = "AAAA"/*TODO*/;
        std::string guess;
        int round = 0;
        std::cout << "*** Mastermind ***" << "\n";

        while (guess != code && round != maxTries) {
            std::cout << "What's your guess? (" << size << " chars) " << "\n";
            guess = "BBBB" /*TODO*/;
            std::cout << "Your guess: " << guess << "\n";
            ++round;

            int correct = 0 /*TODO*/;
            int correctChars = 0 /*TODO*/;

            if (correct == size) {
                break;
            }

            std::cout << "Correct characters: " << correctChars
                 << "\nCorrect positions: " << correct << "\n" << "You have " << maxTries - round
                 << " tries left." << "\n";
        }

        if (guess == code) {
            std::cout << "Congratulations, you cracked the code!" << "\n";
        } else {
            std::cout << "You didn't manage to crack the code..." << "\n";
            std::cout<<"Code was "<<code;
        }
        playAgain = false /*TODO*/;
    } while (playAgain);
}
playMastermind();
```
