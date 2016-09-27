# Git & GitHub

Förutom att man kan dela kod på GitHub får man även en gratis hemsida som man kan använda till eget bruk. Varje användare på GitHub har tillgång till en hemsida var. Att skapa hemsidan gör vi på samma sätt som när vi pushar vår kod till ett repository på _GitHub_. Så nu får vi skapa en hemsida samtidigt som vi tränar på git.

## GitHub Pages

[GitHub Pages Guide](https://pages.github.com/)

1. Gå till ditt GitHub-konto på [https://github.com/](https://github.com/). 
2. Tryck på pluset uppe i högra hörnet på sidan och välj __New Repository__
3. Under __Repository Name__ skriver du in __dittnamn.github.io__. Du byter ut _dittnamn_ till ditt eget användarnamn på GitHub.
4. Sedan trycker du på den stora gröna knappen längst ner som det står __Create Repository__ på.
5. Klona ner detta repository till din dator på valfri plats med `git clone`. Repositoryt är tomt för stunden så vi kommer bara klona ner en mapp.
6. Lägg till en `index.html` i det tomma klonade repositoryt.
7. Lägg till följande innehåll i `index.html` eller editera innehållet till vad du vill att det ska stå på sidan:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Min GitHub-sida</title>
</head>
<body>
    <h1>Välkommen till min GitHub-sida</h1>
</body>
</html>
```

8. När du skapat `index.html`
9. Lägg till filen till _Staging Area_ med `git add`
10. Gör en commit med valfritt meddelande
11. Pusha dina ändringar till `origin/master`, alltså GitHub i detta fall.
12. Besök `https://dittnamn.github.io` för att se din sida live.
