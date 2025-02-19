---
title: "Van ondertitels naar locatie: het algoritme dat Bestemming X voorspelde in 13 minuten"
date: 2025-01-25 12:00:00 +0100
categories: [Projects]
tags: [Python, AI, Bestemming X, OCR, GPT-4o]
---


## *Bestemming X*

**VTM** stuurt op zondagavond een groep onbekende Vlamingen op pad op een geblindeerde bus, richting een mysterieuze exitlocatie. Aan het einde van de aflevering moeten de kandidaten raden waar ze zijn - een lastige opgave, zo blijkt. Het is niet ongebruikelijk dat de kandidaten hun '**x**' aan de andere kant van Europa zetten. Zo vergisten in de eerste aflevering verschillende kandidaten de **Griekse** omgeving waar de bus halt had gehouden voor de **Spaanse**.

![De Griekse bergen in Aflevering 1](/assets/bestemming1.PNG)
_De Griekse bergen in Aflevering 1_

De kijker wordt opgeroepen om vanuit de zetel gretig mee te zoeken. Zo kunnen kijkers op de website van **VTM** ook hun '**x**' plaatsen. Hier is echter één groot verschil: de kandidaten zitten op de bus zonder toegang tot het internet - de kijker, heeft wel alle **digitale tools** voorhanden, van facebookgroepen tot AI assistants. Dit maakt de opdracht duidelijk eenvoudiger: in het klassement zie je hoe duizenden kijkers vaak tot op enkele meters van de exitlocatie zitten.

Zowel de kijkers als de deelnemers krijgen af en toe de blinddoek opgelicht en mogen kort een glimp van de omgeving opvangen. Maar wat gebeurt er wanneer we die gunst niet krijgen? Dit artikel onderzoekt de vraag: kan een algoritme, permanent met de blinddoek op en enkel op basis van de ondertitels bepalen waar de exitlocatie is?

## Het algoritme

Dit weekend schreef ik een algoritme dat voor mij op zoek ging naar de exitlocaties van *Bestemming X*. Het algoritme kreeg toegang tot de ondertitels, die het omzette naar tekst. Die tekst werd vervolgens geanalyseerd door **GPT-4**, het taalmodel achter ChatGPT. Elke keer dat het algoritme 2500 tokens had verwerkt (lees: ongeveer 1900 woorden), stuurde het een verzoek naar het AI-model om de ondertitels te analyseren en een top 3 van mogelijke exitlocaties terug te geven. Concreet betekende dit dat er per **13 minuten** aflevering een verzoek werd verstuurd, wat neerkomt op **4 gokmomenten** per aflevering en dus in totaal **12 locaties**. In aflevering twee duurde het slechts **13 minuten** voordat deze aanpak de exitlocatie correct herkende als **Meteora, Griekenland**.

![Na 13 minuten gokte het algoritme op Meteora](/assets/x1.png)
_Na 13 minuten gokte het algoritme op Meteora_

## Valkuilen

*Bestemming X* is een programma vol verrassingen. Trouwe fans weten dat je **Aster Nzeyimana** niet altijd op zijn woord moet geloven. Tijdens een aflevering kregen de kandidaten bijvoorbeeld de vraag: "Zit er wit in de vlag van het land waar wij ons nu bevinden?" Het antwoord was "**Nai**". Een Griek zou meteen weten dat dit in het Grieks "ja" betekent, in de ondertiteling stond "nee" te lezen. Het algoritme liet zijn initiële gok op **Griekenland** varen (door de aanwezigheid van wit in de vlag?). De aflevering eindigde in **Athene**, wij zaten net zoals sommige kandidaten op een brug in **Spanje**.

Hieronder vind je een overzicht van de evolutie van de gokken per aflevering, inclusief momenten waarop het algoritme razendsnel juist was, maar ook wanneer het grondig de mist in ging.

## Resultaten

### Aflevering 1 - correcte locatie: **Athene, Griekenland**

| | G1 | G2 | G3 | G4 |
|:---:|:---|:---|:---|:---|
| 🥇 | Thessaloniki | Thessaloniki | Pyreneeën | Ronda |
| 🥈 | Pyreneeën | Sierra Nevada | Andorra | Andorra |
| 🥉 | Dolomieten | Tirol | Perpignan | Lissabon |

### Aflevering 2 - correcte locatie: **Meteora, Griekenland**

| | G1 | G2 | G3 | G4 |
|:---:|:---|:---|:---|:---|
| 🥇 | Meteora | Meteora | Skopje | Meteora |
| 🥈 | Balatonmeer | Sofia | Meteora | Skopje |
| 🥉 | Adrspach | Istanbul | Tirana | Kosovo |

### Aflevering 3 - correcte locatie: **Tirana, Albanië**

| | G1 | G2 | G3 | G4 |
|:---:|:---|:---|:---|:---|
| 🥇 | Plovdiv | Pyreneeën | Tirana | Tirana |
| 🥈 | Istanbul | Baskenland | Pristina | Cappadocië |
| 🥉 | Belgrado | Jura | Skopje | Kaukasus | 