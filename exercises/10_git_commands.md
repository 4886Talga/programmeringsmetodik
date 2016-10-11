# Git kommandon

Nedan kommer ett antal uppgifter gällande git där vi introducerar det grafiska gränssnittet `gitk` samt hur man gör en `rebase`. 

Kom ihåg att man alltid kan kolla statusen på sitt projekt med `git status`.

## Frågor

<details>
    <summary>Hur startar man ett lokalt git-repository i en mapp på sin dator?</summary>
    <br />
        `git init` initialiserar ett nytt tomt repository i mappen du står i. Detta kommando skapar en `.git`-mapp i mappen du står i. Git-mappen innehåller allt som git behöver för att fungera. Skulle du vilja ta bort ett repo eller börja om kan du radera den här mappen.
</details>

---

<details>
    <summary>Hur lägger man till en remote till sitt lokala repository</summary>
    <br />
    `git remote add origin https://link.to/your-repo.git` där länken byts ut till länken till ditt github-repo och origin blir namnet på din remote.
</details>

---

<details>
    <summary>Hur klonar man ner ett redan existerande repository från GitHub?</summary>
    <br />
    `git clone https://link.to/your-repo.git` där länken byts ut till länken till ditt repository.
</details>

---

<details>
    <summary>Hur kan man få en grafisk representation av hur ens commits ser ut?</summary>
    <br />
    Använd kommandot `gitk` i terminalen för att öppna den grafiska klienten för git. Här kan man se "trädet" för sina commits samt alla ändringar. Använd `gitk --all` för att se alla branches.
</details> 

## Övningar

### Skapa ett repo

<details>
    <summary>Skapa ett lokalt repo som du ska jobba utifrån där du skapar en fil: `main.txt`</summary>
    <br />
        `git init` för att skapa repot följt av `touch main.txt` för att skapa filen.
</details>

---

<details>
    <summary>Använd terminalen för att skriva *"This is a master edit"* i `main.txt`</summary>
    <br />
    `echo "This is a master edit" >> main.txt` för att lägga till en ny rad i filen.
</details>

---

<details>
    <summary>Lägg till dina ändringar som du gjorde i `main.txt` i staging area och gör sedan en commit med valfritt meddelande.</summary>
    <br />
        `git add .` följt av `git commit -m "My message"`. 
</details>

---

<details>
    <summary>Använd `gitk` för att se dina commits</summary>
    <br />
        `gitk` borde starta ett grafisk interface för ditt projekt.
</details>

---

### Branching out

<details>
    <summary>Skapa en ny branch som heter `fix` och lista sedan alla branches som du har skapat för att se att du har två olika branches, den ena ska vara master den andra ska vara `fix` som du precis skapade.</summary>
    <br />
    `git checkout -b fix` följt av `git branch` för att se alla branches.
</details>

---

<details>
    <summary>Lägg till *"This is a branch edit"* på rad 2 i `main.txt` Gör sedan en commit medan du står på branchen `fix`. Använd sedan `gitk --all` för att se hur dina commits ser ut.</summary>
    <br />
    `gitk --all`: flaggan --all meddelar om att vi vill se alla branches. --all kan användas på många fler ställen och kan vara bra att komma ihåg.
</details>

---

<details>
    <summary>Gå tillbaka till din master branch med `git checkout master` och ändra första raden i `main.txt` till *"This is a second master edit"*. Lägg till och commita din ändring. Använd sedan `gitk --all` för att se dina ändringar i alla branches. </summary>
    <br />
        Förut låg din branch före master eftersom den innehöll commits som inte master hade. Nu har du dock skapat en commit på master också, den commiten är nyare och därmed ligger master före här och vår branch visas på sidan av vår master som en förgrening.
</details>

---

<details>
    <summary>Gå till branchen `fix` med `checkout` och skapa ytterligare en ny branch medan du står på branchen `fix`. Döp den nya branchen till `fix-fix`
    </summary>
    <br />
    `git checkout fix` följt av `git checkout -b fix-fix`. Om man vill byta snabbt mellan de två senaste branchen man växlat mellan kan man använda `git checkout -`. Du borde nu ha tre branches, `master`, `fix` och `fix-fix` där `fix-fix` är en branch utav `fix`.
</details>

---

Gör en ändring i `main.txt` medan du är på branchen `fix-fix` där du lägger till följande på rad 3: *"This is a branch branch edit"* Lägg till och commita din ändring och använd sedan `gitk --all` för att se hur dina branches ser ut.

---

Gå tillbaka till `fix` branchen med `git checkout fix`. Gör sedan en ändring på fjärde raden: *"Edits never end!"*. Commita din ändring och använd sedan `gitk --all` för att se hur din struktur ser ut.


### Merging in

<details>
    <summary>Vi börjar med att merga in vår `fix-fix` i `fix`. D.v.s den "yttersta" branchen i den näst yttersta branchen med hjälp av `git merge`. nu måste vi också se till att lösa våra konfilkter.</summary>
    <br />
        Medan du står på `fix`: `git merge fix-fix` för att dra in ändringarna i `fix-fix` i `fix`. Lös eventuella konflikter genom att ändra innehållet i en texteditor och sedan commita den nya mergen.
</details>

---

När vi har löst eventuella konflikter i den första mergen kan vi merga in `fix`i master. Här kommer det även förekomma konflikter som vi måste lösa på samma sätt som tidigare genom att redigera textfilen samt göra en ny commit.

---

<details>
    <summary>Använd sedan `gitk` för att se hur din repository ser ut just nu</summary>
    <br />
        Nu borde du se en röra av olika branches och commits men din master borde vara uppdaterad med alla senaste ändringarna och master borde ligga högst/längst fram i ditt träd.
</details>

---

Nu borde `master` vara uppdaterad med både ändringar från `fix` och `fix-fix`. Dock så är inte merge optimalt i alla fall. Ibland kan det även vara bra att använda en **rebase**.

### Drop the rebase

Dock så ska man inte alltid merga, det är ganska vanligt att man istället använder en `rebase` för att få bättre struktur i sitt repository samt att det kan vara lättare att lösa konflikter ibland med en rebase. 

[Merge vs. Rebase](https://www.atlassian.com/git/tutorials/merging-vs-rebasing/)

---

Använd kommandot `git rebase` för att rebasea `fix-fix` in i master. Ställ dig först i master branch för att sedan använda kommandot `git rebase fix-fix`. Här kommer du att mötas av en rad konflikter precis som att du skulle göra en merge.

---
För att lösa konflikterna som uppstår här måste vi först ändra i textfilen `main.txt` så att allt som ska var kvar är där och det som ska tas bort raderas. När vi är klara med våra redigeringar skriver vi `git add main.txt` för att lägga till ändringarna. Sedan fortsätter vi vår rebase med att använda `git rebase --continue`. Beroende på hur många konflikter vi har får vi göra det här ett antal gånger.

---

Använd `gitk --all` för att nu se hur ditt projekt ser ut

---

Om man vill städa upp lite branches sina branches kan man använda `git branch -d fix` samt `git branch -d fix-fix` för att radera våra branches. Nu har vi antingen rebaseat eller mergat in våra ändringar så nu finns alla ändringar i `master`. Nu kan vi ta bort dessa branches eftersom de är nu överflödiga.

Om du fortfarande har ändringar kvar i någon av brancherna kan man använda stort `-D` istället för att tvinga git att ta bort branchen.

---

Nu borde du ha lyckats rebaseat alla ändring in i master!

## Använda Markdown

Markdown är ett **Markup Language**. Ni har sett det förut. Alla uppgifter och den här uppgiften är skriven i markdown. På GitHub och på många andra ställen används detta "språk" för att skapa informativ dokumentation till sina projekt. Markdown märker upp din text så att den formatteras med hjälp av HTML & CSS. Vi ska nu använda oss utav Markdown för att göra en färgstark README.md.

[https://guides.github.com/features/mastering-markdown/](https://guides.github.com/features/mastering-markdown/)

[Markdown Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

1. Skapa en `README.md` i mappen i ditt projekt som du jobbade på tidigare i denna uppgift. Du kan även skapa en readme.md i ett redan existerande repository som du har på GitHub för att använda GitHubs inbyggda redigerare.
2. Med hjälp av länkarna ovan. Formattera din README.md så att den ser ut som denna nedan:

---

# My Readme!

## This is a sub heading to my readme

### This is a sub sub heading

[Link to cool site](https://fend16.github.io/)

![Cool kitten](http://placekitten.com.s3.amazonaws.com/homepage-samples/408/287.jpg)

>Här är ett coolt blockcitat som får mig att ändra mina livsvanor

Här är en text med både **fet text** samt *kursiv text* samt ~~genomstruken text~~. 

#### Här är en ordnad lista på bra grejer

1. Bra grej 1
2. Bra grej 2
3. Bra grej 3

#### Här är oordnad lista på dåliga grejer

* Dålig grej 1
* Dålig grej 2
* Dålig grej 3

#### Här lägger jag in lite cool kod

```javascript
function stackMe(){
    stackMe();
}
```

Dålig grej | Bra grej
---|---
Dålig grej 1 | Bra grej 1
Dålig grej 2 | Bra grej 2
Dålig grej 3 | Bra grej 3

---


### GitHub Desktop

Installera GitHub Desktop om du inte redan har det: [GitHub Desktop](https://desktop.github.com/)

[Getting your project on GitHub](https://guides.github.com/introduction/getting-your-project-on-github/)


1. Du ska nu använda GitHub Desktop för att pusha upp ditt projekt sen tidigare till GitHub.
2. Via plusset i högra hörnet kan man välja mellan `add`, `create` samt `clone`. Vi vill lägga till ett redan existerande repository så vi väljer `add`, samt letar reda på mappen som vi ska lägga till.
3. Till skillnad mot kommandotolken är GitHub Desktop syncat mot GitHub i den grad att vi kan publicera repos direkt till GitHub utan att först skapa ett på hemsidan.
4. Skicka upp ditt repository till GitHub genom att trycka på knappen `Publish`. Här får du kanske logga in om du inte redan har gjort det. Sen är det bara att döpa repot till något och sedan trycka på "Publish Repository" så borde ditt repository finnas på din GitHub.







