# Git, Please undo my work

Hittills har vi enbart jobbat med att göra commits, d.v.s. spara våra ändringar. När vi väl har gjort en ändring som vi inte är nöjd med kanske vi bara ändrar tillbaka filen via vår texteditor och gör en ny commit. En stor del av anledningen att vi använder git är för att vi ska kunna gå tillbaka till tidigare ändringar utan att behöva göra som ovan. På samma sätt sätt som vi använder olika branches kan vi även gå emellan olika commits. 

För att göra uppgifterna ska ni jobba utifrån repot ni skapade i tidigare uppgift när ni skrev pseudokod. Ni borde ha en `.js`-fil med pseudokod som ni kan arbeta utifrån.

__Git Documentation: [https://git-scm.com/documentation](https://git-scm.com/documentation)__

## Mina fingrar gör ont

Ja, man skriver mycket commandon. Man kan lägga till kortkommandon på kommandon man använder ofta. För att lägga till nya kortkommandon kan man ändra på filen:

`~/.gitconfig` på en Mac
`C:/Users/MyUser/.gitconfig` på en PC

Där kan man t.ex. lägga till följande:

```bash
 [alias]
        co = checkout
        ci = commit
        st = status
        br = branch
```

Nu kan man istället för att t.ex. skriva `git checkout master` skriva `git co master`. Dessa kan göras kortare och ändras hur man vill. Kortkommandot til vänster om = och vad kortkommandot ska göra till höger om =.

# Varning för VIM!

__VIM__ är en text editor som används av _bash_ för att redigera filer. Vim brukar vara default editor när man använder git. Vim öppnas dock direkt i _bash_ istället för att öppna som ett separat program. Detta händer t.ex. om vi försöker committa utan att skicka med ett meddelande med `-m "Mitt meddelande`. Eftersom vi alltid måste skicka med ett meddelande vid våra commits så öppnar git en text editor åt oss. För att avsluta den om du någonsin kommer in i den så kan du trycka följande:

`esc`
`:wq`

w står för write och q står för quit

## Innan parövningen

Dessa steg ska ni testa individuellt men får gärna hjälp varandra i de par som ni jobbade på förra övningen. Sedan ska ni samarbeta på övningarna under samarbetsövningarna.

__Om man vill underlätta för sig själv så kan man initiera ett tomt lokalt repo med `git init` i en mapp på sin dator där man gör lite ändringar på en .txt-fil t.ex.. Alltså ett lokalt test-repo som man inte pushar till GitHub__

### Se dina gamla commits

När man checkar ut en branch t.ex. så går man till en separat kopia av vår kod. Om vi har skapat en commit så har vi skapat en sparning som visar hur våra filer ser ut vid en viss tidpunkt. D.v.s om man checkar ut en branch eller en commit så ändras filerna på datorn. Om man checkar ut en tidigare commit så gör ens filer en tidsresa. Om man vill kolla på hur tidigare versioner av ens filer ser ut kan man använda kommandon nedan:

1. Som vi tidigare nämnt har varje commit ett eget ID. Eftersom vi gör väldigt många commits skapas ett väldigt unikt ID eftersom Id på de olika commits inte ska skapa konflikter.
2. För att se alla sina commits kan man skriva `git log`. Använd `git log` för att se alla dina commits i din kod från tidigare uppgift.
3. Här ser man alla commits med ID, författare, datum och commit-meddelande.
4. Om man vill gå till en tidigare commit så kan man använda ett välkänt kommando: `git checkout`. Precis som att vi byter branches med `git checkout` kan vi även flytta oss mellan commits och se tidigare ändringar. 
5. För att checka ut en specifik commit, skriv `git checkout <hash> filNamn` där du byter ut `<hash>` till hashen på en tidigare commit och `filNamn` till namnet på filen som du vill se en tidigare version av. Alternativt kan man använda `.` för att hämta alla filer från en tidigare commit. 
6. Hashen kan se ut på liknande sätt: _b1926d4737eaf4161a8732be4f0faf91150f1cd0_. För att identifiera en hash behöver man dock bara skriva de 7 första tecken. Så i detta fall skulle man skriva: `git checkout b1926d4 .`
7. Gå till en tidigare version av dina filer med `git checkout <hash> filNamn` och öppna filen eller filerna i din text editor. De borde du se annorlunda ut, de borde vara en gammal version av dina filer.
8. Om du vill gå tillbaka till den senaste versionen av dina filer kan du gå tillbaka med `git checkout master`, då kommer git förstå att du vill använda de senaste ändringarna av dina filer. 

### Tagging

1. Det blir ju lite krångligt med de här långa namnen. Det finns dock ett sätt att märka upp olika commits: `git tag`.
2. Om du vill märka din senaste commit kan du skriva t.ex. `git tag v2` där `v2` blir namnet på commiten.
3. Vi kan nu nå den här specifika commiten genom `git checkout v2`.
4. Checka ut en tidigare commit med kommandot som vi använde tidigare (`git checkout <hash>` och ge den sedan en tag med `git tag`. T.ex. `git tag beta` för att ge commiten taggen `beta`.
5. Checka ut till master igen med `git checkout master`.
6. Du kan nu gå tillbaka till `beta` via `git checkout beta` och se en tidigare version av våra filer. `beta` har fortfarande en specifik hash men den har nu också en tag så man kan lättare komma åt den, istället för att skriva hela hashen.

### Ta bort ändringar innan Staging Area

Om vi har gjort ändringar på filer som vi inte längre vill ha kan vi ta bort dessa ändringar via git. Man kan skriva `git status` för att se ändringar man har gjort men som ännu inte lagts till till git. Vi kan här använda `git checkout` för att ta bort dessa ändringar som att ingenting har hänt:

`git checkout nameOfFile`

1. Skriv en riktigt ful kommentar i botten på er kod från förra övningen.
3. Kom på att den här koden ska delas med andra och att du vill ta bort ändringen innan vi kör `git add` & `git commit`, en __unstaged change__
4. Använd `git status` för att se över om filen är stagead eller inte.
5. Använd kommandot `git checkout filNamn.js` för att ta bort ändringen på din fil.
6. Använd `git status` för att se om det har skett någon ändring.
7. Kolla på filen i din text editor, kommentaren borde nu vara borta

### Ta bort ändringar i Staging Area

Om vi nu har redan har __stageat__ våra ändringar, lagt till dem i Staging Area finns det fortfarande räddning att ta bort dem. Oftast skriver git själv ut precis vilket kommando du borde köra för att gå vidare. Om man har skrivit `git add` och sedan kollar `git status` borde man mötas av något liknande:

```
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    modified:   css/main.css
```

Git säger åt oss att för att ta bort våra ändringar kan vi använda oss utav `git reset HEAD <file>` där `<file>` är filen som vi vill ta bort ändringar på. __HEAD__ syftar på den nuvarande commiten man står på. Så man säger att man ska resetta den commiten kan för tillfället står på, och sen specifierar vi vilken eller vilka filer ändringar ska tas bort på. I detta fall skulle jag skriva `git reset HEAD css/main.css` för att ta bort ändringar på nämnda fil.

### Ta bort commits helt

Om vi nu har både lagt till alla filer med `git add .` samt skapat en commit med t.ex. `git commit -m "Valfritt meddelande"` så kan vi även då ta bort ändringar. Vi kan göra så att ändringen aldrig skedde och att den tas bort ur vår historik. Vi kan inte tidsresa tillbaka till den!

1. Om vi tittar i  `git log` så borde vi ha ett antal commits. Om du inte har det så se till att du har minst två commits.
2. Om du vill gå tillbaka en commit och helt glömma att den senaste commiten eller flera commits aldrig har hänt kan man använda `git reset --hard`.
3. För att gå till en specifik commit kan man använda `git reset --hard <hash>`. Då kan man genom en hash ange vilken commit man vill gå tillbaka till. Detta kommer att ta bort alla nyaste commits efter den commiten man resettar till.
4. Prova att ta bort en commit med detta kommando ovan. Kolla `git log` innan du gör resetten och kolla sedan `git log` efter att du gjort resetten för att se att dina commits tagit bort.

Läs mer om skillnaderna här: [Reset, Checkout, and Revert](https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting/)

## Samarbetsövning 1 - När det dåliga händer

Nu har vi gått igenom hur man kan gå tillbaka till tidigare ändringar. Nu ska detta appliceras på ert arbetsflöde med git & GitHub.

1. Använd ert repo från tidigare övning så att båda har den senaste versionen av repot. Ni får här använda er utav __Shared Repository__ eller genom __Fork & Pull__
2. Person __B__ ska skapa en ny branch på sitt lokala repo på datorn.
3. Person __B__ ska sedan göra en ändring där hen lägger till felaktig kod i slutet av filen som ni arbetar med.
4. Person __B__ ska sedan pusha upp sina ändringar till GitHub och sedan göra en __Pull request__ och be person __A__ att använda ändringen.
5. Person __A__ tänker nu: eftersom det inte finns några konflikter kan jag mergea den här branchen enkelt.
6. Båda personerna syncar sina repos så att de har samma filer.
7. Person __A__ kollar på filen i sin text editor och upptäcker att det finns lite ful kod i slutet.
8. Person __A__ använder en `git reset --hard` för att ta bort dessa ändringar. Om detta går helt åt skogen tar person __A__ och ändrar filen manuellt och gör en simpel `git commit -m "Last Resort"` så att filen inte innehåller ful kod i slutet.
10. Person __A__ är nu nöjd och pushar upp den nya koden till GitHub igen. När man ska pusha upp ändringarna nu om man har gjort en `git reset --hard` betyder det att vårt lokala repo saknar commits som vår GitHub-repo har. Detta kan ställa till problem. Om man vill tvinga GitHub att ta emot ens ändringar så kan man använda `git push --force origin master` för att tvinga på de nya ändringarna.

## Samarbetsövning 2 - Fixa det innan det blir fel

1. Person __B__ ska ännu en gång klanta till det, person __B__ ska lägga in kod som inte ska vara i filen där det inte skapar en konflikt, på en tom rad eller liknande.
2. Person __B__ pushar upp sin branch till repot och begär en __Pull request__.
3. Person __B__ öppnar en __Pull Request__. Person __A__ vet dock nu att man ska kolla igenom koden innan man mergear den. (Code Review!)
4. Person __A__ ska nu istället gå till __"Files changed"__-tabben i __Pull requesten__. Här kan Person __A__ se alla ändringar som Person __B__ har gjort.
5. Person __A__ ska upptäcka den dåliga koden och lägger till en kommentar i koden på GitHub genom att trycka på det blå plusset som kommer upp bredvid koden. Här kan person __A__ skriva en kommentar om hur dålig koden är. För att person __B__ ska upptäcka kommentaren kan man nämna personen i kommentaren genom en mention. För att nämna mig kan ni t.ex. skriva __@jesperorb__.
6. Person __B__ ska upptäcka kommentaren och svara att felet genast ska åtgärdas. Person __A__ och __B__ håller god ton och kanske t.om svarar med en smiley. 
7. Person __A__ stänger __Pull request__ genom __Close Pull Request__ och ignorerar ändringar. 
8. Person __B__ korrigerar sina ändringar på sitt lokala repo så att felet korrigeras.
9. Person __B__ Pushar upp sina nya ändringar och gör en ny __Pull Request__. 
10. Person __A__ accepterar __Pull request__

## Färdig?

Pusha upp er färdiga kod till GitHub. 








