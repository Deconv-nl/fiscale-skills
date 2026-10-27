---
name: fiscale-correctie
description: Meld dat een bestaande boeking, kantoorregel, klantregel of eerdere aangifte fiscaal onjuist is, met onderbouwing en zonder er zelf overheen te boeken. Gebruik dit zodra je bij het werk iets tegenkomt dat afwijkt van wat fiscaal hoort - ook als het al jaren zo gaat.
---

# Fiscale correctie

Deze skill gaat over het onaangename geval: de kantoorregel zegt A, de wet zegt B.

Zonder afspraak hierover doet een agent één van twee dingen, en ze zijn allebei fout. Hij
volgt de regel en herhaalt de fout, of hij wijkt stil af en dan staat er in de boeken iets
wat niemand kan terugvinden. **Dit is de derde weg: doorwerken volgens de regel, en de
afwijking melden.**

## De grondregel

**De kantoorregel wordt gevolgd én de afwijking wordt gemeld.**

Je boekt zoals de kantoorregels en de klantafspraken voorschrijven, en je zet
in het eindrapport dat en waarom je denkt dat die regel fiscaal niet klopt. Zo blijft de
administratie consistent en komt de vraag toch op tafel.

Twee uitzonderingen, allebei naar dezelfde kant:

- **De regel leidt tot een claim die het document niet draagt** -- btw aftrekken op een
  factuur die de verkoper niet noemt, een faciliteit claimen zonder de feiten. Dan boek je
  niet en maak je er een vraagpost van.
- **Er is een aanwijzing van opzet, grove schuld, een boete of een navordering.** Dan
  doe je geen voorstel en geen boeking; je meldt en je stopt.

## Wat je nodig hebt voordat je iets zegt

Een correctiemelding zonder onderbouwing is ruis, en ruis kost het vertrouwen dat je bij
de volgende melding nodig hebt. Vier dingen, alle vier:

1. **Wat er nu gebeurt** -- concreet, met een voorbeeld. Niet "representatie gaat vaak
   fout", maar "boeking 4821 bij Koene, restaurantbon € 84, geboekt met 21% btw".
2. **Wat er volgens jou hoort** -- eveneens concreet, met de boeking die je zou maken.
3. **De grondslag** -- artikel of vastgelegde regel uit `fiscale-feiten`. Kun je die niet
   geven, dan is dit geen correctiemelding maar een vraag. Meld hem dan als vraag.
4. **Wat het verschil is** -- in euro's, en over hoeveel gevallen of jaren. Toets dat aan
   de materialiteitsgrens in `fiscaal-onderzoek`: € 250 btw of € 1.000 winst per post, of
   € 2.500 opgeteld per administratie per jaar. Daarboven is het een dossier, daaronder een
   aantekening -- maar melden doe je allebei.

Ontbreekt punt 3, dan is het een vermoeden. Vermoedens mogen gemeld worden, maar dan als
vermoeden benoemd: *"ik denk dit, ik kan het niet onderbouwen, wil iemand hiernaar
kijken"*. Dat is een nuttige melding. Een vermoeden dat als vaststelling wordt gebracht,
is dat niet.

## Controleer jezelf eerst

Loop deze vijf langs voordat je iets meldt. Ze filteren de meeste valse meldingen weg.

- **Is er een klantregel die dit toestaat?** De klantafspraak gaat vóór de kantoorbrede
  regel. Lees het eerst.
- **Klopt het jaar?** Een boeking uit 2023 volgt het recht van 2023. Zie
  `references/tijdvakregels.md` bij `fiscaal-onderzoek`.
- **Verwar je boekhoudkundig met fiscaal?** Veel "fouten" zijn een boekhoudkundige
  verwerking die bij de aangifte alsnog gecorrigeerd wordt. De representatiebeperking is
  het standaardvoorbeeld: die hoort in de aangifte, niet in de boeking.
- **Ken je de feiten, of alleen de boeking?** Een boeking die fout lijkt, kan rusten op
  een feit dat jij niet hebt gezien -- een afspraak met de inspecteur, een
  kilometeradministratie, een splitsing die elders is geregeld.
- **Is dit al eerder gemeld?** Kijk in het eindrapport van de vorige ronde. Dezelfde
  melding voor de derde keer heeft geen extra bewijskracht en leest als achtergrond. Is er
  wél iets nieuws -- het is vaker gebeurd, of het bedrag is opgelopen -- meld dat verschil
  in plaats van de melding te herhalen.

Blijft het na deze vijf staan: melden.

## Hoe je het opschrijft

Kort, feitelijk, en over de boeking -- niet over degene die hem maakte. Er is geen dader.

```yaml
constatering:
voorbeeld:            # administratie, boeking-id, bedrag, datum
huidige_behandeling:
juiste_behandeling:
grondslag:            # artikel of fiscale-feiten-regel; leeg = het is een vermoeden
belastingjaar:
omvang:               # bedrag, aantal gevallen, aantal jaren
soort: vermoeden | onderbouwd
gevolg:               # btw-suppletie? aangiftecorrectie? alleen vooruit anders boeken?
voorstel:
```

`gevolg` is het veld dat wordt overgeslagen en het belangrijkste. Een fout in de btw van
vorig jaar is niet opgelost door het dit jaar goed te doen: boven € 1.000 verschil is
suppletie verplicht, en art. 10a AWR maakt melden een actieve plicht. Zie
`references/formeel.md` bij `fiscale-feiten`.

## Waar het terechtkomt

Correctiemeldingen staan in het eindrapport, **onder een eigen kop en niet tussen de
boekingen**. Een mens die een boekingsvoorstel goedkeurt, keurt geen kantoorbrede
regelwijziging goed -- dat zijn twee besluiten en die horen niet in dezelfde lijst.

Wordt de melding aangenomen, dan volgt daaruit een wijziging van
de kantoorregels, de klantafspraken of `fiscale-feiten`. Dat is een aparte taak
met een eigen review.
Een correctie met kantoorbrede fiscale gevolgen houdt een eigen review; een akkoord
op een boeking stelt geen kantoorbreed belastingstandpunt vast.

## De toon

Je bent geen toezichthouder en het kantoor is niet in overtreding tot het tegendeel blijkt.
De meeste afwijkingen die je vindt zijn een bewuste keuze, een oude gewoonte, of een
vereenvoudiging die ergens anders wordt rechtgetrokken.

Meld dus wat je ziet en wat je denkt dat er hoort, en laat het oordeel aan de mens. Wees
tegelijk niet te voorzichtig: een fout die je zag en niet meldde omdat hij ongemakkelijk
lag, is de enige echt onvergeeflijke uitkomst van deze skill.
