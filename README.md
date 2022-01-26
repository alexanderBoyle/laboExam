# Eindexamen Continuous Integration Basics

Aanvullend op de meerkeuzetoets die je dient in te vullen via Leho, werk je onderstaande examenopdracht uit in deze GitHub repo.

>**Belangrijk:** de meerkeuzetoets op Leho staat helemaal **los van deze opdracht** (in tegenstelling tot de labo's die je na elke les maakte met bijhorende toets). Maak **EERST** de toets en werk vervolgens onderstaande opdracht uit.

Volg de stappen van de opdracht **exact** (ook namen van bestanden, mappen, branches, ...).
Let er ook op dat je alle conventies volgt (o.a. commit messages, naamgeving branches, ...).

## Puntenverdeling

| Onderdeel | Punten |
|-----------|--------|
| Conventies (algemeen) | 5 |
| Deel 1 | 5 |
| Deel 2 | 4 | 
| Deel 3 | 4 |
| Deel 4 | 5 |
| Deel 5 | 5 |
| Deel 6 | 4 |
| Afronden opdracht | 3 |
| **TOTAAL** | **35** |

## **Examenopdracht:** *Takenlijst*
- [ ] Open de Git Bash Console op de locatie waar je deze opdracht wil gaan uitwerken.
- [ ] Zorg ervoor dat een lokale kopie van de startsituatie *(deze repository)* van de opdracht op jouw pc terechtkomt. Maak hiervoor gebruik van het passende git commando. 
- [ ] Ga vervolgens via de Console naar je hierboven verkregen lokale repository. Dit kan/mag je uiteraard ook doen door de nieuw aangemaakte folder aan te klikken en hier opnieuw een Git Bash console te openen via de **Git Bash Here** optie.
>**Tip!** Controleer voor je verder werkt of je al dan niet in de juiste git repository zit! Je kan dit snel visueel vaststellen in je console.

## Deel 1: gitignore instellen en files toevoegen (5 ptn)

Voor we aan de slag gaan binnen deze repo, willen we enkele bestanden voorgoed uitsluiten uit het versiebeheer.

- [ ] Maak een nieuwe gitignore file aan op de juiste plaats binnen je lokale repo (volg onze conventie).
- [ ] Voorzie hierin de nodige regels om het volgende te bekomen:
  - Alle tijdelijke bestanden (extensie `.tmp`) in de hele repo worden genegeerd.
  - Alle bestanden binnen de map `src` worden genegeerd, behalve deze met extensie `.html` of `.css`.
- [ ] Voorzie je gitignore van wat commentaar die beschrijft wat de regels als effect hebben.
- [ ] Voer onderstaande reeks commando's uit
  ```
  mkdir src
  touch src/index.html
  touch src/contact.html
  touch src/garbage.txt
  touch src/main.css
  touch src/notes.tmp
  touch passwords.tmp
  touch LICENSE
  ```
- [ ] Verifieer of je gitignore regels hun werk hebben gedaan: worden de juiste bestanden genegeerd in de working directory? Zo niet: pas dan **EERST** je gitignore regels aan tot ze correct zijn.
- [ ] Neem de toegevoegde bestanden op in de geschiedenis van je lokale repo (op de `master` branch).
- [ ] Synchroniseer de `master` branch naar de remote.

## Deel 2: branches aanmaken (4 ptn)

- [ ] Maak lokaal een nieuwe `dev` branch vanaf master en synchroniseer deze naar de remote.
- [ ] Maak lokaal meteen ook een feature branch `feature/home-page` vanaf `dev`. Synchroniseer ook deze branch naar de remote.
- [ ] Maak lokaal nog een tweede feature branch `feature/contact-page` vanaf `dev`. Synchroniseer ook deze branch naar de remote.
- [ ] Maak lokaal een derde feature branch `feature/css` vanaf `dev`. Synchroniseer ook deze branch naar de remote.

## Deel 3: home page (4 ptn)

- [ ] Ga lokaal naar de branch `feature/home-page`.
- [ ] Open het (nog lege) bestand `src/index.html` in een editor naar keuze (bv. Visual Studio Code).
- [ ] Voorzie onderstaande inhoud voor deze home page:
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Home</title>
  </head>
  <body>
      <h1>Welkom!</h1>
  </body>
  </html>
  ```
- [ ] Bewaar je wijziging en neem deze op in je lokale git geschiedenis (op de huidige branch `feature/home-page`).
- [ ] Synchroniseer de wijziging naar de remote.
- [ ] Merge **lokaal** de branch `feature/home-page` in `dev`.
- [ ] Synchroniseer ook `dev` vervolgens naar de remote.

## Deel 4: contact pagina (5 ptn)

- [ ] Ga lokaal naar de branch `feature/contact-page`.
- [ ] Breng deze feature branch up to date met de meest recente wijzigingen uit de `dev` branch.
- [ ] Open het bestand `src/contact.html` en voorzie het van deze inhoud:
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Contact</title>
  </head>
  <body>
      <a href="mailto:fictiefje@fopstraat.be">Mail me</a>
  </body>
  </html>
  ```
- [ ] Bewaar deze wijziging en neem ze op in je lokale git geschiedenis.
- [ ] Open het bestand `src/index.html` en pas deze aan door onder regel 10 deze lijn toe te voegen:
  ```html
  <a href="contact.html">Contact</a>
  ```
- [ ] Bewaar en neem ook deze wijziging op in je lokale git geschiedenis.
- [ ] Synchroniseer naar de remote.
- [ ] Open op GitHub een pull request van de branch `feature/contact-page` naar `dev`.
- [ ] **Laat deze pull request even open staan.** We gaan ze later pas mergen.

## Deel 5: CSS (5 ptn)

- [ ] Ga lokaal naar de branch `feature/css`.
- [ ] Breng deze up to date met de laatste wijzigingen uit de `dev` branch.
- [ ] Open het bestand `src/main.css` en voorzie het van deze inhoud:
  ```css
  html, body {
    background-color: lightblue;
  }
  ```
- [ ] Bewaar de wijziging en neem deze op in je lokale git geschiedenis.
- [ ] Open nu het bestand `src/index.html` en pas deze aan door onder regel 6 deze lijn toe te voegen:
  ```html
  <link rel="stylesheet" href="main.css">
  ```
- [ ] Bewaar deze wijziging en neem ze op in de lokale git geschiedenis.
- [ ] Voeg vervolgens (nog steeds in de file `src/index.html`) onder regel 11 deze lijn toe:
  ```html
  <p>Welkom op mijn website</p>
  ```
- Je home page zou nu deze inhoud moeten hebben:
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <link rel="stylesheet" href="main.css">
      <title>Home</title>
  </head>
  <body>
      <h1>Welkom!</h1>
      <p>Welkom op mijn website</p>
  </body>
  </html>
  ```
- [ ] Bewaar deze wijziging en neem ze op in de lokale git geschiedenis.
- [ ] Synchroniseer naar de remote.
- [ ] Open op GitHub een pull request van de branch `feature/css` naar `dev`.
- [ ] **Laat deze pull request even open staan.** We gaan ze later pas mergen.

## Deel 6: pull requests afwerken (4 ptn)

Bekijk even je twee openstaande pull requests naar de `dev` branch.
Je zal zien dat geen van beiden een conflict rapporteert.
Het ziet er dus naar uit dat we ze beiden probleemloos kunnen afwerken.

- [ ] Merge de eerste pull request van de branch `feature/contact-page` naar `dev`.
- [ ] Wanneer je vervolgens de andere pull request wil afwerken, zal je zien dat daar nu wel een conflict optreedt.
      De inhoud van de target branch `dev` is immers net veranderd door de eerste PR te mergen, en conflicteert nu
      wel met de wijzigingen uit de tweede pull request.

We zullen het conflict nu lokaal oplossen.

- [ ] Ga lokaal naar de branch `feature/css`.
- [ ] Denk erover na welke commit op deze branch het conflict zou kunnen veroorzaken.
      Achteraf bekeken, willen we deze specifieke wijziging gewoon helemaal ongedaan maken om het conflict op te lossen.
- [ ] Gebruik het gepaste git commando om deze ene specifieke commit lokaal terug te draaien **zonder te knoeien met de bestaande geschiedenis**.

>**Tip:** als je niet weet welke commit het conflict veroorzaakt heeft, of hoe je deze kan terugdraaien, is het ook toegelaten om het conflict op een andere manier (naar keuze) op te lossen. **Dit zal je maar een deel van de punten opleveren voor dit onderdeel**, maar zo kan je wel verder met de rest van de opdracht.

- [ ] Synchroniseer naar de remote.
- [ ] Verifieer in je openstaande pull request op GitHub dat het conflict verdwenen is.
- [ ] Merge de pull request.

## Afronden opdracht (3 ptn)

- [ ] Ga lokaal naar de `dev` branch en breng deze up to date met alle wijzigingen die remote gebeurden (via de pull requests).
- [ ] Merge lokaal de `dev` branch in de `master` branch.
- [ ] Synchroniseer de `master` branch met de remote.

# Afspraken

- Volg alle aangeleerde **conventies (5 ptn)**!!
- Elke vorm van **fraude (kopiëren van code/opdracht, ...)** wordt bestraft met een nulscore.
- Raadpleeg gerust de cursus, oefeningen en PE-opdrachten.
- Gebruik van internet is toegestaan, al is dit niet altijd aan te raden. Alles wat nodig is, werd gezien in de lessen en is aanwezig in de cursus.
- Controleer zeker zelf goed of alle commits, branches, pull requests, ... correct aanwezig zijn op je remote repo.
  Wij kunnen uiteraard enkel quoteren wat op de remote aanwezig is.
- Controleer ook of de pull requests allemaal volledig zijn afgewerkt en gemerged.
