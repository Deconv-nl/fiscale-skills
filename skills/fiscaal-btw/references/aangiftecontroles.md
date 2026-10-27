# Controles vóór een btw-aangifte

Loop deze af voordat een aangifte de status `KLAAR_VOOR_VERIFICATIE` krijgt. De volgorde
is bewust: aansluiting eerst, inhoud daarna, vergelijking als laatste.

## Aansluiting

- omzetrekeningen sluiten aan op de belaste omzet in de aangifte;
- verschuldigde btw sluit aan op de btw-rekeningen in het grootboek;
- voorbelasting sluit aan op de inkoopboekingen;
- de totalen van de aangifte sluiten aan op de administratie;
- het saldo van de btw-rekeningen na afsluiting van het tijdvak is nul, of het verschil is
  verklaard.

Een niet-verklaard verschil op de btw-rekeningen is de meest voorkomende voorbode van een
naheffing. Zoek het uit; boek het niet weg.

## Volledigheid

- alle facturen van het tijdvak zijn verwerkt -- de werkvoorraad is leeg, gemarkeerde
  boekingen in het boekhoudpakket inbegrepen;
- geen openstaande vraagposten die btw raken;
- verlegde prestaties zijn zowel bij de verschuldigde als bij de af te trekken btw
  verwerkt;
- intracommunautaire leveringen en verwervingen zijn compleet en sluiten aan op de opgaaf
  ICP;
- invoer en uitvoer zijn juist verwerkt;
- creditnota's en correcties zijn meegenomen;
- geen dubbel geboekte facturen;
- ontbrekende documenten zijn benoemd, niet stilzwijgend overgeslagen.

De opgaaf ICP moet regel voor regel aansluiten op rubriek 3b. Doet hij dat niet, dan volgt
er vrijwel zeker een vraag van de Belastingdienst.

## Inhoud

- privégebruik is beoordeeld: auto, telefoon, gemengde kosten;
- de correctie privégebruik auto staat in het **laatste** tijdvak van het jaar;
- niet-aftrekbare btw is uitgesloten: horeca, relatiegeschenken boven de drempel,
  personeelsvoorzieningen;
- pro rata is toegepast waar er vrijgestelde prestaties zijn;
- herziening van investeringsgoederen is beoordeeld, in het laatste tijdvak van het jaar;
- ongebruikelijke tarieven of btw-codes zijn nagelopen;
- facturen op privénaam zijn gemeld -- de btw daarop is niet gedekt.

## Vergelijking

- vergelijk met het vorige tijdvak en met hetzelfde tijdvak vorig jaar;
- verklaar elke materiële afwijking;
- controleer of er een correctie over een eerder tijdvak openstaat, en of de
  suppletiegrens wordt overschreden.

Een aangifte die sterk afwijkt van het patroon en waarvoor niemand een verklaring heeft,
gaat niet weg. Dat is geen extra zorgvuldigheid maar de goedkoopste plek om de fout te
vinden.

## Uitkomst

```yaml
tijdvak:
status: KLAAR_VOOR_VERIFICATIE | GEBLOKKEERD
aansluitverschillen: []
openstaande_vraagposten: []
afwijkingen_met_verklaring: []
suppletie_nodig: true | false
opmerkingen: []
```

Een onverklaard materieel verschil geeft `GEBLOKKEERD`. Niet "klaar met een kanttekening".
