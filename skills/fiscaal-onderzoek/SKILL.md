---
name: fiscaal-onderzoek
description: Zoek uit wat de fiscaal juiste behandeling is van een transactie, een boeking of een aangiftepost, en onderbouw die met bronnen die voor het juiste tijdvak golden. Gebruik dit bij elke fiscale vraag, en bij elke boeking waarvan de behandeling niet vastligt in de kantoorregels of de klantregels.
---

# Fiscaal onderzoek

Deze skill bepaalt wat er fiscaal hóórt, en waarop dat rust. Hij boekt niets en dient
niets in.

De vraag die hij beantwoordt is altijd dezelfde: **wat is voor dit feitencomplex, in dit
tijdvak, de best verdedigbare behandeling, en welke bron draagt dat?**

## Waar je begint: niet hier

Voor het dagelijkse boekwerk staat het antwoord meestal al ergens. Loop deze volgorde af
voordat je gaat onderzoeken:

1. De vastgelegde afspraken met de klant.
2. De kantoorbrede regels.
3. `fiscale-feiten` -- de vastgelegde tarieven, drempels en termijnen.
4. Pas dan deze skill.

Onderzoek doen voor iets wat al is vastgelegd kost tijd en levert bovendien een tweede,
net andere formulering op van een regel die al bestond. Vind je bij 1 of 2 iets dat je
fiscaal onjuist lijkt: niet stilzwijgend afwijken en niet stilzwijgend volgen, maar
`fiscale-correctie`.

## Wat je eerst vaststelt

Zonder deze vijf is er geen vraag, alleen een onderwerp:

- **wie** -- belastingplichtige en rechtsvorm (eenmanszaak, B.V., stichting, vof);
- **welke belasting** -- OB, IB, Vpb, LB, formeel recht;
- **wanneer** -- transactiedatum, en het belastingjaar of aangiftetijdvak;
- **wat** -- de materiële feiten, uit het document, niet uit de metadata;
- **waarom het opkomt** -- boeking, aangifte, vraag van de klant, correctie.

Splits de feiten daarna in drie stapels, en houd ze uit elkaar tot het eind:

| Stapel | Betekenis |
| --- | --- |
| **Vastgesteld** | staat in een document dat je gelezen hebt |
| **Afgeleid** | volgt uit iets anders; noteer waaruit |
| **Ontbrekend** | je hebt het nodig en je hebt het niet |

**Een ontbrekend feit vul je niet in.** Dat is de kern van deze hele skill. Een aanname
die als feit meegaat, is later niet meer te herkennen van een gelezen feit -- en juist
dat verschil bepaalt of een standpunt houdbaar is. Ontbreekt er iets materieels, dan
eindigt het onderzoek met `AANVULLENDE_INFORMATIE_NODIG` en de vraag die gesteld moet
worden.

## Hoe je onderzoekt

Werk `Regel -> Feiten -> Toepassing -> Conclusie` af, in die volgorde en zichtbaar. De
regel eerst, want wie met de conclusie begint zoekt daarna alleen nog bronnen die hem
bevestigen.

De bronnen en hun rangorde staan in `references/bronnenhierarchie.md`. De tijdvakregels
-- welk recht gold toen, en wat je doet met later gewijzigde wetgeving -- in
`references/tijdvakregels.md`.

### Eerst: kún je de bron lezen?

Dat verschilt per omgeving en dat is het eerste wat je vaststelt.

**Heb je een webgereedschap** (WebFetch, WebSearch), dan gebruik je het. Haal de bron
werkelijk op, citeer wat er staat, en noteer de datum waarop je hem las. Dit is de normale
gang van zaken bij een vraag die iemand aan een agent in Claude Code stelt.

**De agent die de administraties verwerkt heeft dat gereedschap niet.** Die kan
`wetten.overheid.nl`, `rechtspraak.nl` en `kennisgroepen.belastingdienst.nl` niet
bereiken. Voor hem geldt de rest van deze paragraaf.

### Wat je doet als je de bron niet kunt lezen

Kun je de bron niet daadwerkelijk ophalen, dan heb je geen bron, hoe zeker de regel ook
voelt.

Zeg dat dan, met zoveel woorden, en kies één van deze twee:

- **Het staat in `fiscale-feiten` met status `vastgesteld`.** Dan is dát je bron, en je
  noemt hem als zodanig: het kantoor heeft die regel vastgelegd en gedateerd.
- **Het staat daar niet.** Dan is je uitkomst `AANVULLENDE_INFORMATIE_NODIG` met
  `betrouwbaarheid: LAAG` en de concrete vraag erbij: welk artikel of welke pagina een
  mens moet nakijken. Vermeld wat je vermoedt dat het antwoord is -- dat scheelt de mens
  zoekwerk -- maar **presenteer het niet als conclusie en boek er niet op.**

Een verzonnen artikelverwijzing is erger dan geen verwijzing. Hij ziet er precies zo uit
als een goede en niemand controleert hem meer.

## Wanneer een mens ernaar moet kijken

Stop en leg voor, ook als je een antwoord hebt:

- bronnen spreken elkaar materieel tegen;
- een materieel feit ontbreekt en is niet te achterhalen;
- de uitleg is werkelijk onzeker, niet alleen ongebruikelijk;
- het gaat om boete, navordering, bezwaar, beroep, controle of een vermoeden van fraude;
- herstructurering, fusie, splitsing, fiscale eenheid, grensoverschrijdende structuur,
  vaste inrichting of verrekenprijzen;
- deelnemingsvrijstelling, renteaftrekbeperking of misbruikbepaling;
- ongebruikelijke transacties tussen de B.V. en haar DGA;
- het bedrag komt boven de materialiteitsgrens hieronder uit.

## De materialiteitsgrens

Vastgesteld op 06-09-2026. Dit is een **kantoorafspraak** en geen wettelijke grens: pas
hem aan als de praktijk uitwijst dat hij te hoog of te laag ligt, en zet er dan de nieuwe
datum bij.

| Grens | Bedrag | Per |
| --- | --- | --- |
| Btw-effect van één post | € 250 | post |
| Winsteffect van één post | € 1.000 | post |
| Opgeteld effect binnen één administratie | € 2.500 | boekjaar |

Blijft een twijfelgeval onder alle drie, dan mag de agent zelf beslissen op grond van de
kantoorregels en `fiscale-feiten`, en meldt hij de keuze in het eindrapport. Komt hij
boven één ervan uit, dan gaat het naar een mens.

Die derde regel is er omdat de eerste twee anders te omzeilen zijn. Veertig bonnen van
€ 40 zijn samen geen kleinigheid, ook al is elke bon dat wel. Tel gelijksoortige twijfel
daarom op voordat je hem afwijst.

**Ongeacht het bedrag** gaat het altijd naar een mens bij: boete, navordering, bezwaar,
controle, een vermoeden van opzet of grove schuld, staking, herstructurering, een
grensoverschrijdende structuur, de rekening-courant van de DGA, en de
deelnemingsvrijstelling. Daar is geen ondergrens; een kleine fout in zo'n dossier is niet
klein.

Los daarvan staat de **wettelijke** suppletiegrens van € 1.000 voor de btw. Die is geen
materialiteitsafspraak maar een verplichting, en hij gaat voor. Zie
`references/formeel.md` bij `fiscale-feiten`.

## Wat je teruggeeft

Het formaat staat in `references/uitkomstformaat.md`. Twee dingen daaruit gelden altijd:

- **De betrouwbaarheid is een woord, geen getal.** `HOOG`, `MIDDEL` of `LAAG`, met de
  reden erbij. Een percentage suggereert een meting die er niet is.
- **Alternatieven en onzekerheden staan er ook in**, ook wanneer je een duidelijke
  conclusie hebt. Wie alleen de gekozen route opschrijft, maakt de keuze onzichtbaar.

## Valkuilen

- **Boekhoudkundig is niet fiscaal.** De commerciële winst is het startpunt van de
  fiscale winst, niet hetzelfde.
- **Nooit het huidige recht op een ouder tijdvak plakken.** Tarieven, drempels en
  vrijstellingen wijzigen jaarlijks.
- **Een grootboekrekening of een eerdere boeking is geen fiscale onderbouwing.** Dat de
  vorige boekhouder het zo deed, zegt alleen dat hij het zo deed.
- **Een faciliteit geldt niet omdat hij vorig jaar gold.** Toets de voorwaarden opnieuw
  per jaar.
- **belastingdienst.nl is uitleg, geen wet.** Prima voor tarieven, termijnen en
  invulmechaniek; hij gaat niet boven de wet als het schuurt.
- **Modelkennis is geen bron.** Ook niet als hij klopt.
