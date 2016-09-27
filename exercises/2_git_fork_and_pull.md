# Fork & Pull Model

Nu ska vi istället göra varsin kopia av repot som ni jobbar utifrån. Detta arbetsätt kallas __"Fork and Pull"__. Vilket betyder att vi skapar våra egna kopior, sen ber vi ägaren till ursprungliga repot att dra in (Pull) våra ändringar samt slå ihop alla ändringar (merge). Se länk nedan för hur man Forkar en repo:

[Fork A Repo](https://help.github.com/articles/fork-a-repo/)

## Forka

1. Person A och B skapar varsin fork av ägarens repo samt klonar ner detta forkade repo till sin egen dator.
2. Ändringar ska nu ske i detta forkade repo


## Push to fork!

1. Person __A__ ska nu göra en ändring på __fil 9 på sitt forkade repo__ så att sagan slutar lyckligt om den tidigare slutade sorgligt och vice versa. 
2. Person __B__ ska nu göra en ändring på fil 6 så att hjälten inte vinner utan blir besegrad.
3. Istället för att pusha till ägarens repo ska du som Person __A__ eller Person __B__ pusha din kod till ditt egna forkade repo.
4. Person A & B ska sedan skicka pull request från sina repos på GitHub till ägarens repo.
5. Ägaren ska merga branches in i huvudrepot samt lösa eventuella `merge conflicts` som har uppstått.

Se nedan för att få era repos synkade när man har forkat ett repo.


## Synca era repos

När vi vill hämta ner den senaste versionen av vårt forkade repo som ligger uppe på GitHub till vårt lokala repo använder vi:
```bash
git fetch
```
Vi kan även göra en `git pull` vilket gör en `git fetch` samt en `git merge` samtidigt.
Vårt lokala repo har ju en länk till GitHub-repot genom att vi har tidigare lagt till en `remote`. Då kan vi lägga upp och ta ner ändringar vi gör på vårt eget forkade repo. Men vi skulle också vilja att vi kan hämta de senaste repot från ägarens repo, alltså den slutgiltiga versionen. Detta kan vi göra genom att lägga till en till remote som man brukar kalla för `upstream`:

[Configuring a remote for a fork](https://help.github.com/articles/configuring-a-remote-for-a-fork/)
[Syncing a fork](https://help.github.com/articles/syncing-a-fork/)

Så när vi vill pusha ändringar samt hämta ändringar från vårt eget repo använder vi:
```bash
git push origin
git fetch origin
```

Och när vi vill hämta ändringar från ägarens original:
```bash
git fetch upstream
```

1. Sätt upp en `remote` till ägarens repo och kalla den för `upstream`
2. Kör sedan en `git fetch upstream` enligt länken ovan och se till så att ditt lokala repo är synkat med ägarens repo samt ditt eget forkade repo.
