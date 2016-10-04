# JavaScript Tools

<!-- MarkdownTOC depth=3 -->

- Introduktion
- IDE kontra Text Editor
- Linta filer
- JSHint i olika Text Editorer
    - Atom - JSHint
    - Sublime Text - JSHint
    - Brackets - JSLint
- Övriga verktyg

<!-- /MarkdownTOC -->

##Introduktion

När vi arbetar med JavaScript ligger en stor del av frustrationen i att vi har missat ett semikolon, parantes eller liknande. Det är såklart bra träning att lära sig upptäcka sina egna fel. Dock ska vi inte lägga onödig tid på att felsöka en felaktig curly bracket `}` djupt inne i vår kod trots att vi redan har löst uppgiften. Detta stjäl mycket tid från att faktiskt lära sig att programmera i JavaScript. 

Vi har tidigare pratat om att JavaScript är "förlåtande" på många sätt. T.ex. säger JavaScript inte till oss att språket implicit konverterar en sträng till ett heltal eller liknande och man kan oftast lagra variabler hejvilt utan att vi får några errors. JavaScript är ett __dynamiskt__ språk där vi inte behöver definiera vilka typer vi använder oss av. Alla variabler är av typen `var` och kollas när programmet körs. JavaScript försöker sedan tolka vår kod som JavaScript tror att koden ska tolkas. Motsatsen till ett _dynamiskt_ språk är ett __statiskt__ språk. I ett statiskt språk måste man ange om man ska använda en sträng eller ett heltal. Istället för att direkt köras måste statiska språk först __kompileras__, alltså byggas ihop först. När koden byggs ihop kollas dessa värden så att de stämmer. Java och C# är exempel på statiska språk.

>Static typing means that programs are checked before being executed, and a program might be rejected before it starts. Dynamic typing means that the types of values are checked during execution, and a poorly typed operation might cause the program to halt or otherwise signal an error at run time.

## IDE kontra Text Editor

När vi har skrivit JavaScript har vi använt en textredigerare. När man programmerar använder man oftast ett __IDE__ (Integrated Development Environment) som är en sorts förlängning av en textredigerare. Ett IDE är en hel utvecklingsmiljö där många av de verktyg man behöver redan är inkluderade. Ett IDE är mer utav en komplett lösning inriktat oftast för att användas för ett specifikt språk medan t.ex. Sublime, Atom och Brackets är mer utav 'all purpose' och kan användas till många olika programmeringsspråk. När det kommer till JavaScript IDE finns det egentligen bara ett som används och det är __WebStorm__. WebStorm är ett väldigt bra IDE och har mycket av den funktionalitet man behöver när man utvecklar. Dock kostar WebStorm och är svårare att sätta sig in i, därför har vi jobbat med textredigerare.

En sådan funktionalitet som kan behöva läggas till i våra textredigerare är funktionen att söka efter syntax-fel i vår kod, att linta.

## Linta filer

Det finns verktyg som hjälper oss att kolla vår kod. När man felsöker JavaScript med hjälp av ett verktyg så brukar man säga att man __lintar__ js-filer. 

Det finns online-verktyg som kan kolla igenom kod som man skriver in. Ett av de mest använda verktygen är __[JSHint](http://jshint.com/)__. Här klistrar man helt enkelt in den kod man vill kolla på vänster sida och eventuella felmeddelanden dyker upp på höger sida. Ett alternativ till __[JSHint](http://jshint.com/)__ är den något äldre __[JSLint](http://www.jslint.com/)__. De gör samma sak, kollar efter fel i vår kod.

![Exempel på JSHint](http://i.imgur.com/LleDW7Z.png)
_Exempel på användning av JSHint_

JSHint och JSLint kan användas antingen som online-verktyg eller så kan man integrera dem i sin text editor, se nedan om du vill använda Lint i din textredigerare.

##JSHint i olika Text Editorer

### Atom - JSHint

Atom levereras med en inbyggd pakethanterare som används för att installera olika plugins som kan användas vid kodning. För att komma åt pakethanteraren letar man reda på `Preferences` i menyn längst upp. Här väljer man sedan `Packages` och söker sedan på den plugin man vill använda i sökrutan:

![Packages > Install](http://i.imgur.com/h6dPMZF.png)
_Installera Plugins i Atom_

Sedan trycker man på `Install och då borde vår plugin vara installerad. Om inte denna plugin har aktiverats, testa starta om Atom. 

Nu borde Atom ge varningar på de rader där du skriver felaktig syntax. 


### Sublime Text - JSHint

Av någon anledning har Sublime onödigt många steg för att installera en linter.

För att installera olika tillägg i Sublime Text måste man först installera __[Package Control](https://packagecontrol.io/installation)__. Detta gör man genom att gå till länken ovan och kopiera texten i den gråa rutan. Sedan öppnar man Sublime Text och går till `View` i menyn längst upp för att sedan trycka på `Show Console`. Nu borde du får upp en svart ruta längst ner i Sublime där du kan klistra in den kopierade texten. När du klistrat in texten från hemsidan så trycker du på `Enter` och väntar på att installationen är klar. Sedan startar du om Sublime. Nu har ni Package Control, härifrån kan man installera alla sorters olika verktyg för utveckling.

Nu kan man installera tillägg genom att trycka kombinationen `Shift + CMD + P` på Mac och `Ctrl + Shift + P` på Windows. Om det skulle misslyckas så kan man gå till `Tools > Command Palette`.

Här kan man börjas skriva det man letar efter så kommer en meny upp. För att installera ett paket kan vi börja att skriva `install package` och då borde vi få upp något liknande:

![Package Control - Install Package](http://i.imgur.com/rj4YQB8.png)
_Package Control - Install Package_

Tryck på `Enter` för att komma vidare. Nu kan vi söka på vilket packet vi vill använda. Installera först `SublimeLinter` genom att söka efter det och trycka på `Enter`. Installera sedan `SublimeLinter-JSHint`. 

Dock så behöver _SublimeLinter_ JSHint installerat på datorn. Detta görs enklast genom att installera `node` genom att ladda ner det här: [NodeJS](https://nodejs.org/en/). När node är installerat, öppna sedan en terminal och skriv in följande: `npm install -g jshint`. Nu borde JSHint vara installerat.

Om detta går åt skogen så skicka ett slack-meddelande och be om hjälp.

### Brackets - JSLint

Brackets levereras med JSLint redan installerat. JSLint är en äldre linter som ger ganska många onödiga varningar jämfört med JSHint. Dock så är funktionaliten densamma och du borde få upp varningar längst ner i ditt dokument som hjälper dig vid eventuella fel. 

Det ska gå att använda JSHint istället för JSLint om man följer dessa instruktioner: [Adds JSHint support to Brackets](https://github.com/cfjedimaster/brackets-jshint)

## Övriga verktyg

Sublime Text, Atom och Bracket har alla olika plugin managers. Sublime har [Package Control](https://packagecontrol.io/), Atom har [Packages](https://atom.io/packages) och Brackets har en [Extension Manager](https://github.com/adobe/brackets/wiki/Brackets-Extensions).

I alla dessa verktyg kan man söker efter specifika paket som löser specifika problem vi har. Jag vill t.ex. hålla koll på mina brackets, var de slutar och börjar. För att hjälpa mig med det har jag `BracketHighlighter` till Sublime som tydligt visar vilka brackets som hör ihop. 

Samma problem uppstår oberoende av vilken textredigerare man har. Brackets har som vi tidigare nämnt redan en linter installerad så mycket av funktionaliteten kan redan finnas i din textredigerare om du letar. Annars kan man söka efter specifika paket att installera som löser dessa problem. 

__Använd de olika pakethanterarna för att söka efter plugins som underlättar ditt kodande__

Om man vill ha olika tips så kan Google förse en med många svar: "Top 10 packages sublime/atom" eller liknande brukar förse en med massa alternativ. Sedan får man sålla efter de paket som passar ens behov.

På många textredigerar går det även att ställa in så att det __autosparas__. I varje pakethanterar kan man då söka på "Autosave" så borde man få upp ett paket som fixar det åt en.








