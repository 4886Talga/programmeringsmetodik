# Peer Code Review

Under kursernas gång har ni fått jobba tillsammans, mer eller mindre strukturerat. Ni har hjälpt personen som sitter bredvid er med att lösa en bit kod eller så kanske ni har skickat en färdig kodrad via slack och sen får den personen "hantera det".

Det finns såklart mer strukturerade sätt att jobba med kod och hur man hjälper varandra att skriva bättre kod. 

__Glöm inte att använda git under arbetets gång och commita för att ni ska skicka upp koden till GitHub och använda i en senare övning__

## Pair Programming

Sättet vi ska arbeta på är genom __Pair Programming__:
[WikiHow: How To Pair Program](http://www.wikihow.com/Pair-Program)

Detta betyder att båda "programmerare" ska arbeta utifrån samma dator och samma kod vi samma tillfälle men att personerna byter av varandra efter en viss stund. En person ska alltså köra, skriva själva koden. Den andra personen ska ge feedback och tänka på sätt man kan förbättra koden. Kommunikation är viktigt. Ett typiskt arbetsflöde kan se ut såhär:

1. Båda personerna definierar problemet så att båda personerna förstår vad som ska göras och vad resultatet blir
2. Båda sätter tillsammans upp en tidsram, hur lång tid ni tror att problemet kommer att ta att lösa.
3. Båda sätter tillsammans upp i vilket intervall ni ska bytas av. Detta kan dock vara lite flytande. Fastnar ena personen kan man bytas av.
3. Båda personerna sätter tillsammans upp en en grund för problemet i pseudokod.
4. Person __A__ sätter sig ned vid datorn och börjar skriva koden.
5. Person __B__ sitter/står/ligger bredvid och ska förse person __A__ med feedback. Vilken sorts feedback man ska ge kan dock vara svårt men det borde inte främst handla om att man missat en parantes semikolon. Ni borde istället fokusera på saker som:
    * Eventuella problem som kommer uppstå i framtiden. Behövs en if-sats här för att kolla ett visst villkor som kanske kan uppstå?
    * Eventuella ändringar man kan göra för att koden ska bli tydligare. Om din partner inte förstår vad som menas är det stor chans att framtida programmerare som ska ta över din kod inte heller gör det.
    * Person __B__ ser till så att person __A__ inte upprepar sig för mycket i sin kod, alltså håller koden DRY (Don't Repeat Yourself).
6. När det är tid att byta enligt utsatt schema eller när ni kört fast byter ni så att person __b__ skriver kod och person __a__ läser koden och kollar efter eventuella förbättringar.
7. Detta upprepas till problemet är löst och har uppnått förväntad lösning.


## Övning 1 - Every day problems

1. Ni ska välja ett problem som ni ska lösa. Vilket problem som ni ska lösa får ni välja själva. I denna första övning ska vi börja med problem vi är bekanta med för att sedan gå över till ett riktigt programmeringsproblem. Övningen handlar mer kring sättet att jobba än att vi faktiskt producerar kod som kan köras och användas. Exempel på problem: 
    * Laga punkan på cykeln
    * Hur tar jag mig till skolan enklast?
    * Vad ska jag äta till middag ikväll?
    * Hur ska vi skapa världsfred?
2. När ni har valt ett avgränsat problem ska ni försöka lösa det problemet. Ni ska börja med att försöka lösa problemet i pseudokod. Pseudokoden får skrivas som en enkel lista på vad som ska hända eller vara mer strukturerad enligt exemplet nedan. Ni får även skapa en __Flow Chart__ för att träna på det. Pseudokoden ska dock bara vara en __rough sketch__. Den ska inte vara detaljerad utan hålla sig på en grundlig nivå. Exempel nedan:

```
START
    Hire problemsolving monkeys to solve problem
    Make monkeys work 24/7
    if monkey rebellion
        Start war with monkeys
        Destroy monkey leader, "Big Boy Banana"
        Find hidden magic monkey gem that creates world peace
    else
        Monkeys find solution
    All happy    
STOP

```

3. När ni är klara med att skapa er pseudokod enligt ovan ska ni nu försöka omsätta detta till "riktig" pseudokod enligt exemplet nedan, samtidigt som ni jobbar utifrån __Pair Programming__-modellen. Den ena ska köra medan den andra ska ge feedback till den som kör. Dessa roller ska bytas flera gånger innan ni är klar med er pseudokod. Er nya pseudokod behöver inte vara som den ursprungliga pseudokoden utan det är meningen att den ska ändras samt bli mer detaljerad än föregående pseudokod. Exempel:

```javascript
function solveWorldPeace(){
    var satisfiedMonkeys = true;
    var worldPeace = false;
    while(!worldPeace){
        //Do monkey stuff
    }
    return worldPeace;
}
```


## Övning 2 - Every day coding problems

Vi ska nu försöka applicera föregående metod på ett riktigt programmeringsproblem istället. Välj ett programmeringsproblem som ni tror att ni kan lösa, att ni faktiskt löser problemet är inte lika viktigt. Antingen kan ni använda er utav en gammal uppgift som är olöst eller välja någon av exemplen nedan (ni får lösa ett helt annat problem):

* En funktion som beräknar BMI
* En funktion som tar din input och plockar ut den första och sista bokstaven
* En funktion som tar en PIN-kod. Du kan bara komma åt banksaldot om du skriver in rätt PIN-kod. Du har tre försök på dig.
* En funktion som är en enkel miniräknare.
* En funktion som rullar en tärning
* En funktion som rullar flera tärningar och läggar ihop summan av tärningarna.s


Välj ett problem som ni vill lösa. Jobba sedan enligt _Pair Programming_-modellen som tidigare:

1. Välja ett problem som båda är överens om.
2. Sätta upp en tidsram för problemet.
4. Sätt upp ett intervall som bestämmer när ni byter roller.
5. Sätta upp en pseudokod-ritning
6. Göra om pseudokoden till körbar kod.
7. Nå en lösning med hjälp av ovanstående metod :)


## När ni är klara

Pusha upp er lösning till ett repository på GitHub. Ta lunch.
