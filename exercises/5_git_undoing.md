# Git, Please undo my work

Hittills har vi enbart jobbat med att göra commits, d.v.s. spara våra ändringar. När vi väl har gjort en ändring som vi inte är nöjd med kanske vi bara ändrar tillbaka filen via vår texteditor och gör en ny commit. En stor del av anledningen att vi använder git är för att vi ska kunna gå tillbaka till tidigare ändringar utan att behöva göra som ovan.

För att göra uppgifterna ska ni jobba utifrån repot ni skapade i tidigare uppgift när ni skrev pseudokod. Ni borde ha en `.js`-fil med pseudokod som ni kan arbeta utifrån.

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

## Innan parövningen

Dessa steg ska ni testa individuellt men får gärna hjälp varandra i de par som ni jobbade på förra övningen. Sedan ska ni samarbeta på övningarna under samarbetsövningarna.

### Se dina gamla commits

1. Som vi tidigare nämnt har varje commit ett eget ID. Eftersom vi gör väldigt många commits skapas ett väldigt unikt ID eftersom Id på de olika commits inte ska skapa konflikter.
2. För att se alla sina commits kan man skriva `git log`. Använd `git log` för att se alla dina commits i din kod från tidigare uppgift.
3. Här ser man alla commits med ID, författare, datum och commit-meddelande.
4. Om man vill gå till en tidigare commit så kan man använda ett välkänt kommando: `git checkout`. Precis som att vi byter branches med `git checkout` kan vi även flytta oss mellan commits.
5. För att checka ut en specifik commit, skriv `git checkout <hash>` där du byter ut `<hash>` till hashen på din commit. Hashen kan se ut på liknande sätt: _b1926d4737eaf4161a8732be4f0faf91150f1cd0_. För att identifiera en hash behöver man dock bara skriva de 7 första tecken. Så i detta fall skulle man skriva: `git checkout b1926d4`. Checka ut en tidigare commit som ni har gjort, kolla sedan på filen om den är ändrad efter din checkout.
6. Om du inte vill använda den gamla commiten kan du gå tillbaka till master med `git checkout master`.
7. Om man vill använda sig av denna commit istället för den senaste. Då kan man stagea och commita filerna (`git add && git commit -m`) till den brachen man står på.

### Tagging

1. Det blir ju lite krångligt med de här långa namnen. Det finns dock ett sätt att märka upp olika commits: `git tag`.
2. Om du vill märka din senaste commit kan du skriva t.ex. `git tag v2` där `v2` blir namnet på commiten.
3. Vi kan nu nå den här specifika commiten genom `git checkout v2`.
4. Checka ut en tidigare commit och ge den sedan en tag med `git tag`. T.ex. `git tag beta`.
5. Checka ut till master igen
6. Checka tillbaka till beta-commiten via `git checkout beta`.

### Ta bort ändringar i Staging Area

Vi lägger till filer i staging area genom att skriva `git add` samt filen vi ska lägga till. Om vi vill lägga till alla filer vi gjort ändringar på 

`git checkout nameOfFile`

1. Skriv en riktigt ful kommentar i botten på er kod från förra övningen.
2. Lägg till ändringen med `git add .`
3. Kom på att den här koden ska delas med andra och att du vill ta bort ändringen men har redan lagt till den till _Staging Area_.
4. Använd `git status`
5. Använd kommandot `git checkout dinkod.js` för att ta bort ändringen på filen
6. Använd `git status`
7. Kolla på filen i din text editor, kommentaren borde nu vara borta

### Gå tillbaka en commit

1. Whoops, vi hann både använda `git add dinkod.js` samt även commita vår kommentar med `git commit -m "Minor text fixes`
2. Använd `git log` för att se att vår commit har lagts in
3. Detta kan vi dock lösa med `git revert`. För att gå tillbaka ett steg kan vi i detta fall använda `git revert HEAD`.
4. Om vi vill reverta till en annan commit än den precis innan kan vi skriva `git revert <hash>` där `<hash>` byts ut till den commiten du vill reverta till.
4. Kolla på filen i din text editor. Nu borde kommentaren vara borta.
5. Använd `git log` igen för att se vad som har skett och vilka commits vi har.

### Ta bort commits helt

2. Som vi ser i `git log` finns våra fortfarande våra commits kvar efter git revert men våra filer är ändrade.
1. Om du vill gå tillbaka en commit och helt glömma att den här commiten har hänt kan man använda `git reset --hard`.
2. För att gå tillbaka ett steg kan man använda `git reset --hard HEAD`
3. För att gå till en specifik commit kan man använda `git reset --hard <hash>`
4. Kolla `git log` för att se dina ändringar

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
8. Person __A__ använder sina nya kunskaper om `git revert` för att åtgärda problemet och återställa till en tidigare commit.
9. Person __A__ är dock inte helt nöjd, hen vill inte att de här ändringarna ska synas i `git log`. Person __A__ bestämmer sig därför för att använda sig av `git reset --hard` för att helt ta bort commitsen.
10. Person __A__ är nu nöjd och pushar upp den nya koden till GitHub igen.

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








