# Git kommandon

Nedan kommer ett antal frågor som 

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
    `echo "This is a master edit" >> main.txt`
</details>
---
<details>
    <summary>Lägg till dina ändringar och gör en commit i git</summary>
    <br />
        `git add .` följt av `git commit -m "My message"`. 
</details>
---
<details>
    <summary>Använd `gitk` för att se dina commits</summary>
    <br />
        A:
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
    <summary>Gå tillbaka till din master branch med `git checkout master` och ändra raden i `main.txt` till *"This is a second master edit"*. Lägg till och commita din ändring. Använd sedan `gitk --all` för att se dina ändringar i alla branches. </summary>
    <br />
        Förut låg din branch före master eftersom den innehöll commits som inte master hade. Nu har du dock skapat en commit på master också, den commiten är nyare och därmed ligger master före här och vår branch visas på sidan av vår master som en förgrening.
</details>
---
<details>
    <summary>Gå till branchen `fix` med `checkout` och skapa ytterligare en ny branch medan du står på branchen `fix`. Döp den nya branchen till `fix-fix`
    </summary>
    <br />
    `git checkout fix` följt av `git checkout -b fix-fix`. Om man vill byta snabbt mellan de två senaste branchen man växlat mellan kan man använda `git checkout -`
</details>
---
<details>
    <summary>Gör en ändring i `main.txt` medan du är på branchen `fix-fix` där du lägger till följande på rad 3: *"This is a branch branch edit"* Lägg till och commita din ändring och använd sedan `gitk --all` för att se hur dina branches ser ut</summary>
    <br />
</details>
---
<details>
    <summary>Gå tillbaka till `fix` branchen med `git checkout fix`. Gör sedan en ändring på fjärde raden: *"Edits never end!"*. Commita din ändring och använd sedan `gitk` för att se hur din struktur ser ut.</summary>
    <br />
</details>

Nu när du ser över hur dina olika branches ser ut, vågar man ens merga?


### Merging in

<details>
    <summary>Vi börjar med att merga in vår `fix-fix` i `fix. D.v.s den "yttersta" branchen i den näst yttersta branchen med hjälp av `git merge`. nu måste vi också se till att lösa våra konfilkter.</summary>
    <br />
        Medan du står på `fix`: `git merge fix-fix` för att dra in ändringarna i `fix-fix` i `fix`. Lös eventuella konflikter genom att ändra innehållet i en texteditor och sedan commita.
</details>
---
<details>
    <summary>När vi har löst eventuella konflikter i den första mergen kan vi merga in `fix` i master. Här kommer det även förekomma konflikter som vi måste lösa.</summary>
    <br />
</details>
---
<details>
    <summary>Använd sedan `gitk` för att se hur din repository ser ut just nu</summary>
    <br />
        A:
</details>
---

### Drop the rebase

Dock så ska man inte alltid merga, det är ganska vanligt att man istället använder en `rebase` för att få bättre struktur i sitt repository samt att det kan vara lättare att lösa konflikter ibland med en rebase. 

[Merge vs. Rebase](https://www.atlassian.com/git/tutorials/merging-vs-rebasing/)

Använd kommandot `git rebase` för att rebasea `fix-fix` in i master. Ställ dig först i master branch för att sedan använda kommandot `git rebase fix-fix`. Här kommer du att mötas av en rad konflikter precis som att du skulle göra en merge.
---
För att lösa konflikterna som uppstår här måste vi först ändra i textfilen `main.txt` så att allt som ska var kvar är där och det som ska tas bort raderas. När vi är klara med våra redigeringar skriver vi `git add main.txt` för att lägga till ändringarna. Sedan fortsätter vi vår rebase med att använda `git rebase --continue`. Beroende på hur många konflikter vi har får vi göra det här ett antal gånger.
---
Använd `gitk --all` för att nu se hur ditt projekt ser ut
---
Om man vill städa upp lite branches sina branches kan man använda `git branch -d fix` samt `git branch -d fix-fix` för att radera våra branches. Nu har vi antingen rebaseat eller mergat in våra ändringar så nu finns alla ändringar i `master`. Nu kan vi ta bort dessa branches eftersom de är nu överflödiga.

Om du fortfarande har ändringar kvar i någon av brancherna kan man använda stort `-D` istället för att tvinga git att ta bort branchen.


### GitHub Desktop

Installera GitHub Desktop om du inte redan har det: []()

[](https://guides.github.com/introduction/getting-your-project-on-github/)




