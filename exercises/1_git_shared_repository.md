# Öva på samarbete med GIT

## Förberedelser

Vi ska nu jobba med git & GitHub enligt __Shared Repository Model__

Ni ska nu dela upp er i grupper. Grupper ska bestå av __3 personer__.
En av personerna i gruppen ska var __ägaren__ till repositoryt vi kommer att arbeta med. De andra två personerna kommer vara _Collaborators_ som ska skicka upp ändringar till originalet. Ni får själva utse rollerna.
Även fast det står att ni ska ha olika roller får ni hjälpa varandra om ni fastnar på något, det är en gruppuppgift.

Jag kommer referera till repository som repo och allting kommer att låta dumt när jag på svenska skriver alla termer: __gitpusha origin master attackmerga dina commits och fetcha branch remoteclonen__ (Det här är nonsens)

[GitHub Help](https://help.github.com/)

[git - the simple guide](http://rogerdudler.github.io/git-guide/)

## Övning - Storyteller

Repot ni skapar ska innehålla textfiler som tillsammans bildar en saga

Alla som bidrar till repot ska därmed bidra till sagan

Sagan behöver inte vara speciellt bra. Det är `git`-delen vi ska fokusera på.

Sagan ska skrivas på engelska och ska vara barnvänlig.

1. Personen som är ägare i gruppen ska skapa ett nytt repo på webben och kalla det:

`storyteller-by-förnamn-efternamn-klass`

2. Ägaren klonar ner repot till datorn

3. Ägaren skapar sedan följande tomma filer lokalt:
    1. 1_tale_begins.txt
    2. 2_villain.txt
    3. 3_hero_enters_tale.txt
    4. 4_epic_quest.txt
    5. 5_journey_through_land.txt
    6. 6_great_obstacle.txt
    7. 7_hero_wins.txt
    8. 8_moral_of_the_tale.txt
    9. 9_end.txt
    

Exempel på hur det kan se ut:
[https://github.com/jesperorb/storyteller-by-jesper-orb-fend16](https://github.com/jesperorb/storyteller-by-jesper-orb-fend16)

## Fyll på filerna

1. Ni som grupp ska nu fylla på filerna __1, 3, 5-9__ (Inte 2 och 4). Varje fil ska ha minst en mening (Se exemplet ovan). Här får ni hjälpas åt att skriva meningarna.

2. Ägaren lägger sedan till filerna till _Staging Area_, commitar med ett lämpligt meddelande och pushar till GitHub.

## Dela ut uppdrag

1. Se till så att samtliga deltagare är _Collaborators_ genom att gå till ditt repo sen trycka på _Settings > Collaborators_ och sedan bjuda in användarna.

1. Person __A__ och __B__ i din grupp ska klona ner repot lokalt, sedan ska de skapa var sin ny branch lokalt.

2. __A__ och __B__ får var sin uppgift:
    1. person __A__ i din grupp ska på sin branch editera fil __2__
    2. person __B__ i din grupp ska på sin branch editera fil __4__
    3. Person __A__ och __B__ ska sedan pusha upp sin branch till GitHub med `git push -u origin namnPåBranch`
    
3. Gå in på GitHub-repot och se till så att branches har pushats.


## Slå ihop alla samarbeten

[Creating a Pull Request](https://help.github.com/articles/creating-a-pull-request/)

[Using Pull Requests](https://help.github.com/articles/about-pull-requests/)

[Merging a Pull Request](https://help.github.com/articles/merging-a-pull-request/)

[Closing a Pull Request](https://help.github.com/articles/closing-a-pull-request/)


Nu har du som ägare fått en del input ifrån din grupp och det är dags att slå ihop alla branches in i din origin/master så du som ägare har en sammanslagen uppdaterad version av sagan.

1. Person A och B öppnar varsin __Pull Request__ och begär att ägaren mergar branchen med originalet.

2. Ägaren mergar alla __Pull Requests__

När allt ovan är klart går ni vidare till nästa steg.


## Dags för lite konflikter

Du ska nu ge ut nya uppdrag till din grupp:

1. __A__ får i uppgift att:

  1. i __fil 2__ lägga till några adjektiv i beskrivningen av skurken (beskrivande ord som ugly, evil osv)
    
  2. i __fil 3__ lägga till en kort beskrivning av hjältens side-kick
    
  3. i någon av filerna mot slutet av sagan lägga till något som denna side-kick gör för att bidra till sagan
    
2. __B__ får i uppgift att

  1. i __fil 3__ lägga till några adjektiv i beskrivningen av hjälten
    
  2. i __fil 2__ lägga till en kort beskrivning av skurkens husdjur
    
  3. i någon av filerna mot slutet av sagan lägga till något som detta husdjur gör för att bidra till sagan

Samtidigt som __A__ och __B__ arbetar på filerna __2__ och __3__ ska du som är ägare även gå in och lägga till att skurken har något vapen eller föremål samt att hjälten har något vapen eller föremål.

När allt ovan är klart går du vidare till nästa steg.


## Slå ihop alla samarbeten

1. Nu har du fått en del input ifrån din grupp och det är dags att slå ihop all input till en version. Vi ska nu merga alla våra branches till `origin/master` så du har en sammanslagen uppdaterad version av sagan. (merge pull request)

2. __Whoops!__ Eftersom flera användare har ändrat på filer på samma ställe vet inte git vilken version som git ska använda. Ska vi använda ägarens, person A eller person B version? Detta måste vi ange själva och vi kan inte gå vidare med att merga vår pull request.

3. Ägaren ska nu hämta ner alla nya ändringar. För att hämta ner de senaste ändringarna och merga dem med `git pull`.
4. Det kommer att uppstå __merge conflicts__ som ni måste lösa: [Resolve Merge Conflict](https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line/)
5. Öppna filerna som har konflikter med er Text editor och ändra till rätt innehåll
6. Stegea de ändrade filerna och committa
7. Checka ut till master
8. Mergea branchen till master
9. Pusha till GitHub

## Färdig?

Nu borde ni som grupp ha ett repo med en fin liten saga samtidigt som ni har lärt er att dela kod med git via GitHub. Detta är något vi kommer
att arbeta mer med så no sweat om det är mycket som är oklart fortfarande!

Om ni i gruppen är klara så kan ni fortsätta med uppgiften att skapa en [Fork](https://github.com/FEND16/exercises/blob/master/Fork.md)!
Instruktioner om det finns i Fork.md




