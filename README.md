# Kodekurs👩‍💻

Kodekurset holdes etter samarbeid mellom Fremtind og NTNU (Norges teknisk-naturvitenskapelige universitet), og arrangeres i Oslo 5.april 2022.
Kurset arrangeres for påmeldte VGS elever (16-19 år) fra Oslo-området, og er tilknyttet Matematikk-OL som arrangeres i Oslo i juli samme år.

## Mastermind 💡

Mastermind er et spill som baserer seg på at det opprettes en sjult kode bestående av enten tegn, tall, bokstaver eller farger som brukeren skal klare å gjette seg frem til innen X antall forsøk. Spillet ble først gitt ut i 1971 som brettspill, med forskjellige varianter og vanskelighetsgrader av spillet ble lansert i årene som fulgte. London i år 1977 ble det for første gang arrangert VM i Mastermind, hvor en nordmann klarte å kapre 2.plassen etter at det ble spilt ekstraomganger i finalen.

Når brukeren har gjettet sin kombinasjon av koden, vil vedkommende få en tilbakemelding på om det er gjettet riktige tegn og hvorvidt disse er plassert i riktig rekkefølge som den opprinnelige koden. Derimot vil det ikke bli gitt hvilke tegn som er korrekt eller feil. Brukeren får så lov til å gjette ny kombinasjon basert på informasjonen som er gitt frem til alle forsøk er benyttet.

Spillet er opprettet i Jupyter Notebook, hvor vi benytter oss av C++ som kodespråk. En Jupyer 'kernel' for C++ er baser på 'cling C++ interpretor' og 'xeus native implemenation' av Jupyter protokollen.

<img src="https://www.lekolar.no/globalassets/inriver/resources/16907_075092.jpg" width="400">

## Capture The Flag 🚩

Capture The Flag (CTF) er opprinnelig en utendørssport som baserer seg på at to eller flere lag konkurrerer om å fange flagg. Hvordan poenggiving av dette gjøres er veldig forskjellig, og kan blant annet handle om å klare å beholde sitt ene flagg lengst mulig på sin banehalvdel. Andre måter å spille på kan være at man skal samle inn flest antall flagg, eller den høyeste totalverdien gitt av poeng per flagg.

I forbindelse med IT, brukes CTF gjerne når man prater om hacking. Hacking har for mange en negativ assosiasjon, da dette ofte er knyttet til uetisk bruk for å utnytte andre sine svakheter. Derimot handler hacking mye mer om å klare å finne riktig informasjon for å løse ulike problemer som skal oppstå, og heller dekke disse hullene får man blir utnyttet.

## Regler for denne CTF'en

Denne CTF'en varer i XX minutter.

På denne CTF'en gjelder følgende regler:

Det er om å gjøre å samle flest poeng. Hvert flagg (oppgave) har x antall poeng.

1. Dersom det er flere lag som har løst den samme oppgaven, får det laget med best tid maks poengscore, mens de andre får [maks poeng - (rangering-1)].
2. Dersom dere har løst en oppgave, får dere uansett poeng.
3. Dersom dere ikke får til en oppgave, kan dere spørre om hjelp. Det gis ikke minuspoeng for dette.
4. Alle hjelpemidler er lov.
5. Løsningen på hver oppgave er et norsk ord som er kryptert ved bruk av Cæsar-siffer, med mindre oppgaven spesifiserer noe annet.
6. Flagg kapres ved å hente fysiske flagg hos hovedkvarteret. Det finnes flere flagg per oppgave med tilhørende poeng. Dere må oppgi løsningen på oppgaven for å få flagg. Hvis dere ikke har fått til oppgaven, men har prøvd, kan dere forklare det, og allikevel få flagg (med lavere poeng).

## Tips

Bruk litt tid på å planlegge hvilke flagg dere skal prioritere å fange.
Det er lov å dele seg opp i subgrupper.
Dere har 45 minutter til rådighet -- tiden flyr.
Bruk [Cryptii.com](https://cryptii.com/) eller lignende til å dekode kodene.
Flagg med tilhørende poeng og oppgavetekst ligger i `flags.md`

### Oppgaver

Oppgavene ligger i mappen CTF, i filen `flags.md`.

<img src="https://northview.org/wp-content/uploads/2020/06/Capture-the-Flag.png" width="400">
