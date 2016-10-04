# Kodstandard

## Indentering 

Under kursernas gång har vi inte tagit upp vilken best practice man ska använda sig av, vilka "regler" man ska förhålla sig till när man kodar. Detta är delvis eftersom det finns många delade meningar om vad som är best practice. Det är inte heller säkert att alla företag användas sig av samma standard. Många företag har egna standarder som de sätter upp angående hur man ska skriva JavaScript. Det som alla är överens om är dock att man måste __indentera__. Varje kodblock ska tabbas in för att öka läsligheten. Så här ska det inte se ut:

```javascript
//bad
function badFunction()
{
if(true)
{
return false;
}
}
```

Så här ska det se ut:

```javascript
function badFunction(){
    if(true){
        return false;
    }
}
```

På detta sätt blir det tydligare att `if`-satsen är inuti funktionen samt att inuti `if`-satsen returneras ett värde. Dock kan det finnas olika sätt att skriva det här också. Vissa föredrar detta sätt att lägga upp det:

```javascript
function badFunction()
{
    if(true)
    {
        return false;
    }
}

```

## Tabs vs. Spaces

Att indentera är dock, trots vad man skulle kunna tro, ett känsligt ämne. Vissa indenterar med tabbar och vissa indenterar med mellanslag och när det blir snack om vilket som är bäst blir det dålig stämning. Vilket sätt ni än väljer att indenterar på spelar ingen roll för våra kurser, det som är viktigt är dock att ni indenterar tydligt så att koden är lättläst.

För inte så länge sen analyserades en stor del av GitHubs repository och man tog fram data vad som var mest använt och tydligen stod __spaces__ (alltså mellanslag) som klar vinnare:

![Tabs vs. Spaces](http://i.imgur.com/KypjSb4.png)
_Tabs vs. Spaces @ GitHub. Länk: [Tabs vs. Spaces: Blogpost @ Medium](https://medium.com/@hoffa/400-000-github-repositories-1-billion-files-14-terabytes-of-code-spaces-or-tabs-7cfe0b5dd7fd#.8ahftovun)_


## Naming conventions

Att namnge en variabel är också svårare än det låter. Det finns ett antal olika sätt att skriva variabler på och detta brukar variera beroende på vad man gör och jobbar med samt vilket programmeringsspråk det gäller. Följande __naming conventions__ brukar höra till de vanligaste när man programmerar:

* __camelCase__ - Första bokstaven är liten, varje nytt ord i variabeln får stor bokstav
* __PascalCase__ - Varje ord i variabeln får en står bokstav
* __snake_case__ - Varje ord separeras med ett understreck
* __hypen-case__ - Varje ord separeras med ett streck (vissa kallar även denna för kebab-case)

## Övning - Best Practice

Att veta vad som är rätt är inte lätt. Vi ska ännu en gång spana på internet men nu inte efter trender utan best practice. Din uppgift blir nu att försöka leta reda på rätt sätt att skriva JavaScript. Använd flera källor och se om du hittar en gemensam nämnare bland källorna för hur man ska ska arbeta med JavaScript. Psst, det är inte säkert att det finns ett "rätt sätt". 

1. Sök på nätet (alla källor är tillåtna) efter efter vad som är best practice i JavaScript gällande följande:
    * Indentering
    * Namngivning av variabler och funktioner
    * Deklaration av variabler och funktioner
    * Kommentering av kod
    * Hur man skriver syntax för if/while/for-loopar
    * Hur man ska använda lokala och globala variabler
2. Använd minst två olika källor för att kolla vad som gäller för best practice
3. Är källorna överens på samtliga punkter eller finns det skillnader?
4. Sammanställ en lista på vad som verkar vara best practice gällande punkterna ovan.
5. Diskutera med en annan i klassen om det finns eventuella skillnader mellan vad ni hittat.
6. Skicka resultatet till mig via ett slack-meddelande. 





