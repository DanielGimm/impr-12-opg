# Opgaver til IMPR Lektion 12
Husk at indstille 'Working Directory' (arbejdsmappe) for hvert program under 'Edit Configurations...' i drop-down menuen, hvor du vælger hvilket program du kører.
Filer, som dit program åbner, bliver fundet relativt til det 'Working Directory' du vælger.

## Gruppeopgaver
Disse opgaver laves sammen i gruppen. Der er rigeligt med opgaver.
Arbejd grundigt med de opgaver, I kan nå, i den skemalagte tid.

### [Opgave A](src/opgave-a.c): Læsning af k ord fra fil
Hvis I ikke allerede har lavet den som hjemmeopgave, så start med at lave denne. Det er Kurt Nørmarks [opgave 13.1](https://homes.cs.aau.dk/~normark/impr-c/io-seqfile-op-slide-exercise-1.html).
Du kan skrive dit program i filen [`opgave-a.c`](src/opgave-a.c).

> Skriv en funktion
> ```c++
> int getwords(FILE *ifp, int k, char *words)
> ```
> der, om muligt, læser `k` ord fra tekstfilen der er udpeget af pointeren `ifp`.
> Ordene skal læses over i tekststrengen `words` (som allokeres af den funktion, som kalder `getwords`).
> Hvis det ønskes kan ordene organiseres linjevis i `words`, eller blot med 'white space' imellem ordene.
>
> Den programmerede funktion skal returnere det faktiske antal af læste ord (som kan være mindre end `k`).

---
### [Opgave B](src/opgave-b.c): Læsning af personkartotek i komma-separeret tekstfil
Dette er Kurt Nørmark's [opgave 13.5](https://homes.cs.aau.dk/~normark/impr-c/io-extra-opgaver-slide-exercise-2.html).
Du kan skrive dit program i filen [`opgave-b.c`](src/opgave-b.c) og bruge filen [`personer-ind.txt`](personer-ind.txt).

> Skriv et program der indlæser [tekstfilen](personer-ind.txt) i et array af følgende struct:
> ```c++
> #define MAX_NAME_LGT 50
> struct person{
>     char fornavn[MAX_NAME_LGT];
>     char efternavn[MAX_NAME_LGT];
>     char vejnavn[MAX_NAME_LGT];
>     int vejnummer;
>     int postnummer;
>     char bynavn[MAX_NAME_LGT];
> };
> ```
> Indholdet af tekstfilen findes også nederst i opgaven.
> 
> Tekstfilen er linje-orienteret. Data om én person findes på én linje. Navne-delen, gade-delen og by-delen er adskilt af kommaer, 
> og linjen er afsluttet med et punktum. Der optræder ikke cifre i fornavn efternavne, gadenavne eller bynavne. 
> Hver person har ét fornavn og ét efternavn. Gadenavnet kan bestå af flere ord. Bynavnet består af netop et ord.
> 
> Overvej omhyggeligt hvordan du læser bestanddelene af en linje. 
> Det er måske nyttigt for dig at bruge [scansets](https://homes.cs.aau.dk/~normark/impr-c/io-slide-formatted-input-3.html) i din løsning, som et alternativ til `%s`. 
> Vær forsigtig med at ikke at få indlæst et komma som en del af efternavnet. 
> Vær også forsigtig med, at et vejnavn ikke ender med et 'space'.
> 
> Sorter de indlæste data efter efternavn og udskriv de sorterede data på en anden fil. 
> Filen skal have følgende simple linje-format:
> ```
> By: Efternavn
> ```
> 
> Her er input filen til programmet (ligger også i [`personer-ind.txt`](personer-ind.txt)):
> ```
> Lars Jensen, Engtoften 23, 7182 Bredsten.
> Bo Olsen, Gammel Vestergade 56, 4261 Dalmose.
> Kurt Jensen, Haderslevvej 15, 8370 Hadsten.
> Birte Madsen, Universitetsvej 899, 9000 Aalborg.
> Kaj Moberg, Halevindingevej 2, 2670 Greve.
> Bo Rise, Hadsund Landvej Nord 56, 8900 Randers.
> Ebbe Rise, Hadsund Landvej Syd 58, 9520 Hobro.
> Kalle Rastrup, Under Broen 567, 2650 Hvidovre.
> Emil Rask, Over Broen 765, 2650 Glostrup.
> Jens Larsen, Finkevej 1, 6682 Hovborg.
> Lars Olsen, Gammel Vindingevej 2, 7560 Hjerm.
> ```
> 
> Her er den forventede output fil fra programmet:
> ```
> Hadsten: Jensen
> Bredsten: Jensen
> Hovborg: Larsen
> Aalborg: Madsen
> Greve: Moberg
> Hjerm: Olsen
> Dalmose: Olsen
> Glostrup: Rask
> Hvidovre: Rastrup
> Randers: Rise
> Hobro: Rise
> ```

---
### [Opgave C](src/opgave-c.c): En simpel grep funktion
Dette er Kurt Nørmarks [opgave 13.2](https://homes.cs.aau.dk/~normark/impr-c/io-seqfile-op-slide-exercise-2.html).
Du kan skrive dit program i filen [`opgave-c.c`](src/opgave-c.c).

> `grep` er en Unix kommando der søger efter linjer i en tekstfil, som matcher en søgestreng. 
> I denne opgave vil vi programmere en meget simpel variant af `grep`, som udskriver de tekstlinjer, i hvilke et bestemt søgeord forekommer.
> 
> Vi ønsker at anvende det udviklede program således fra kommandolinjen:
> ```
> search programmering my-file.txt
> ```
> eller måske snarere:
> ```
> ./search programmering my-file.txt
> ```
> Dette skal udskrive alle de linjer i `my-file.txt` som indholder strengen `"programmering"`.
> 
> Programmet skal anvende programparametre, som forklaret på [denne slide](https://homes.cs.aau.dk/~normark/impr-c/strings-slide-prog-par.html).

---
### [Opgave D](src/opgave-d.c): Tynde matricer
Dette er Kurt Nørmarks [opgave 13.4](https://homes.cs.aau.dk/~normark/impr-c/io-extra-opgaver-slide-exercise-1.html).
Du kan skrive dit program i filen [`opgave-d.c`](src/opgave-d.c)

> En vilkårlig matrix kan generelt repræsenteres på en tekstfil, med én linje pr. række. 
> Første linje kan angive antallet af rækker og søjler i matricen (altså to heltal). 
> I denne opgave kalder vi dette for den *generelle tekstfil repræsentation* af vilkårlige matricer.
> 
> En *tynd matrix* er et array af to dimensioner, hvor mange af elementerne er nul.
> 
> I denne opgave vil vi skrive et program der understøtter en *speciel tekstfil repræsentation* af tynde matricer på tekstfiler, 
> som i visse tilfælde fylder mindre end den generelle repræsentation af matricer på tekstfiler. 
> I den nye repræsentation skal den første linje af tekstfilen indeholde dimensionerne af matricen - to heltal - antal rækker og antal søjler. 
> Hver af de efterfølgende linjer indholder tre tal: Rækkenummer, søjlenummer, og et tal fra matricen (som ikke er nul). 
> Om nødvendigt kan man gøre sig antagelser om rækkefølgen af linjer i den specielle tekstfil repræsentation.
> 
> Skriv først en funktion som læser en matrix fra den generelle repræsentation på en tekstfil, 
> og som udskriver den specielle tynde repræsentation på en ny tekstfil.
> 
> Skriv dernæst en funktion som løser det omvendte problem: 
> Læsning af en tynd matrix fra en tekstfil og skrivning af en tilvarende matrix på generel form på en anden tekstfil.
> 
> Som et eksempel svarer følgende generelle tekstfil repræsentation af matricen
> ```
> 4 3
> 0.0 0.0 1.0
> 0.0 0.0 0.0
> 2.0 0.0 0.0
> 0.0 3.0 0.0
> ```
> til følgende specielle tekstfil repræsentation af matricen - som er en tynd matrix
> ```
> 4 3
> 1 3 1.000000
> 3 1 2.000000
> 4 2 3.000000
> ```
> *Denne opgave svarer til opgave 4 side 679 i 6. udgave af lærebogen*

---
### [Opgave E](src/opgave-e.c): Input og Output af structs
Dette er Kurt Nørmarks [opgave 13.3](https://homes.cs.aau.dk/~normark/impr-c/io-struct-id-1-slide-exercise-1.html).
Du kan skrive dit program i filen [`opgave-e.c`](src/opgave-e.c)

> Vi vil antage at vi har en struct som beskriver data om en person, så som
> ```c++
> struct person {
>     char *name;
>     int age;
>     char sex;
> }
> ```
> hvor `sex` er enten tegnet 'm' eller 'f'. 
> I denne øvelse bliver du bedt om at programmere funktioner, som kan udskrive et antal personer på en fil, 
> og som efterfølgende kan indlæse disse igen.
> 
> Hvis det er hensigtsmæssigt, er det OK at allokere `name` som et char array: `char name[MAX_NAME_SIZE]`.
> 
> Konkret, skal der skrives to funktioner
> ```c++
> void print_person(struct person *p, FILE *ofp);
> person *read_person(FILE *ifp);
> ```
> Du kan vælge en tekst-baseret og linie-orienteret fremgangsmåde, som illustreret ved forelæsningen. 
> Som et noget lettere alternativ kan du vælge at anvende en binær fremgangsmåde ved brug af `fwrite` og `fread`.
> 
> Overvej hvad der skal til for at anvende `fwrite` og `fread` på `struct person`.



## Hjemmeopgaver
Dette er opgaver, som I kan arbejde med derhjemme.
Enten som forberedelse inden lektionen, eller som afrunding og repetition efter lektionen.

### [Opgave A](src/opgave-a.c): Læsning af k ord fra fil
Dette er Kurt Nørmarks [opgave 13.1](https://homes.cs.aau.dk/~normark/impr-c/io-seqfile-op-slide-exercise-1.html).
Du kan skrive dit program i filen [`opgave-a.c`](src/opgave-a.c).

> Skriv en funktion
> ```c++
> int getwords(FILE *ifp, int k, char *words)
> ```
> der, om muligt, læser `k` ord fra tekstfilen der er udpeget af pointeren `ifp`. 
> Ordene skal læses over i tekststrengen `words` (som allokeres af den funktion, som kalder `getwords`). 
> Hvis det ønskes kan ordene organiseres linjevis i `words`, eller blot med 'white space' imellem ordene.
> 
> Den programmerede funktion skal returnere det faktiske antal af læste ord (som kan være mindre end `k`).
