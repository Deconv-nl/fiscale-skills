---
name: fiscale-verificatie
description: Controleer onafhankelijk een aangifte, een jaarafsluiting of een materieel fiscaal standpunt voordat het naar de klant of de Belastingdienst gaat. Gebruik dit als tweede paar ogen, nooit in dezelfde beweging als het opstellen.
---

# Fiscale verificatie

De opsteller is hier niet aan het woord.

**Je taak is niet om de redenering van de opsteller na te lopen, maar om te proberen hem
onderuit te halen.** Dat verschil is het hele punt van deze skill: wie een redenering
nagaat, vindt bevestiging; wie hem probeert te breken, vindt de fout.

Lees daarom eerst de stukken -- het document, het grootboek, de aangifte -- en vorm je
eigen oordeel, vóórdat je de onderbouwing van de opsteller leest. Het is verleidelijk om
het andersom te doen, want dat gaat sneller, en het levert een controle op die alleen
tikfouten vindt.

## Wat je controleert

1. **Belastingplichtige en tijdvak.** De juiste entiteit, het juiste jaar, het juiste
   aangiftetijdvak.
2. **Volledigheid van de onderliggende administratie.** Is er nog werkvoorraad? Staan er
   vraagposten open? Ontbreken er documenten?
3. **Aansluiting.** Sluit de aangifte aan op het grootboek, en het grootboek op de
   brondocumenten?
4. **Tijdvakjuiste grondslag.** Gold de toegepaste regel in dit jaar? Is een `jaarbedrag`
   uit `fiscale-feiten` bij het juiste jaar gebruikt?
5. **Tegenbronnen.** Is er een bron die de andere kant op wijst, en is die benoemd?
6. **Aannames.** Wat is vastgesteld, wat is afgeleid, wat is aangenomen? Een aanname die
   niet als aanname is opgeschreven, is een bevinding.
7. **Rekenwerk.** Reken materiële posten zelf na. Niet steekproefsgewijs bevestigen --
   opnieuw uitrekenen.
8. **Interne consistentie.** Sluiten de rubrieken onderling aan? Sluit de balans aan op de
   aangifte?
9. **Correcties over eerdere perioden.** Openstaande suppleties, verschillen uit vorig jaar.
10. **Afwijkingen.** Wat is er anders dan vorig jaar, en is dat verklaard?

De uitgewerkte lijst staat in `references/controlelijst.md`.

## De uitkomst

Precies één van drie:

| Uitkomst | Betekenis |
| --- | --- |
| `GOEDGEKEURD` | geen bevindingen die het standpunt raken |
| `GOEDGEKEURD_MET_OPMERKINGEN` | bevindingen die niet materieel zijn, maar wel vastgelegd moeten worden |
| `GEBLOKKEERD` | er staat iets open dat eerst opgelost moet worden |

Bij `GEBLOKKEERD` benoem je wat er moet gebeuren, niet alleen wat er mis is.

`GOEDGEKEURD_MET_OPMERKINGEN` is geen zachte goedkeuring. De opmerkingen gaan mee naar
degene die het stuk uiteindelijk vaststelt, en die beslist of ze eerst opgelost worden.

## De onafhankelijkheidsregel

**Verificatie en opstelling zijn niet dezelfde stap en horen niet in dezelfde beurt.**

Een agent die zijn eigen voorstel verifieert, verifieert niets: hij heeft de aannames
gemaakt die hij zou moeten betwijfelen. Doe de verificatie als losse taak, met de stukken
als vertrekpunt en niet met het voorstel.

En neem de zekerheid van de opsteller niet over. `betrouwbaarheid: HOOG` in een
onderzoeksresultaat is een uitspraak die zelf gecontroleerd moet worden -- vaak is het de
eerste plek waar het misgaat.

## Wat deze skill niet doet

Indienen. Dat kan het kantoor vandaag niet geautomatiseerd en er is geen goedgekeurd
kanaal voor. Een geverifieerde aangifte gaat naar een mens, die hem indient.

Komt dat er ooit, dan hoort daar een eigen, afgeschermde capability bij met een
aantoonbare scheiding tussen opstellen, verifiëren, autoriseren en indienen -- en met
idempotentie, een auditspoor en een expliciete afhandeling van een onbekende uitkomst na
een time-out.
 Tot die tijd is de laatste stap handwerk, en dat is geen tekortkoming.
