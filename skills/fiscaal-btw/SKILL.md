---
name: fiscaal-btw
description: Bepaal de btw-behandeling van een inkoop- of verkooptransactie en controleer een btw-aangifte voordat hij de deur uit gaat. Gebruik dit bij twijfel over een tarief, aftrek, verlegging, vrijstelling, privégebruik of een grensoverschrijdende factuur.
---

# Btw

De tarieven, drempels en termijnen staan in `fiscale-feiten`, in `references/btw.md`.
Deze skill gaat over de volgorde waarin je denkt. Loopt de vraag daarna nog steeds vast,
dan is het `fiscaal-onderzoek`.

## De volgorde per transactie

Elke btw-vraag valt uiteen in dezelfde negen. Sla er geen over, ook niet als het antwoord
voor de hand ligt -- juist bij een gewone factuur zit de fout meestal in stap 3.

1. **Wie zijn de partijen?** Leverancier en afnemer, met land en btw-nummer. Is de afnemer
   werkelijk de administratie, of staat er een privépersoon op?
2. **Is er een prestatie?** Levering van een goed of een dienst -- of is het een
   schadevergoeding, een subsidie, een doorbelasting of een borg? Die zijn vaak onbelast.
3. **Waar is de prestatie belastbaar?** Nederland, een andere lidstaat, of buiten de EU.
   Bij diensten scheidt B2B van B2C hier de wegen.
4. **Wie is de btw verschuldigd?** De leverancier, of is er verlegd naar de afnemer?
5. **Welk tarief of welke vrijstelling?** 21%, 9%, 0% of vrijgesteld -- en houd nultarief
   en vrijstelling uit elkaar.
6. **Draagt de factuur de behandeling?** Staan de wettelijke vermeldingen erop? Zonder
   geldige factuur is er geen aftrek, hoeveel btw er ook op staat.
7. **Is de btw aftrekbaar?** Wordt de inkoop gebruikt voor belaste prestaties? Valt hij
   onder het BUA (horeca, relatiegeschenken, personeelsvoorzieningen)?
8. **Is er privé- of gemengd gebruik?** Auto, telefoon, werkruimte, en bij een stichting of
   vrijgestelde ondernemer: pro rata.
9. **Speelt herziening of correctie?** Een investeringsgoed dat van gebruik wisselt, een
   creditnota, een eerdere fout.

Het uitwerkformaat staat in `references/transactieanalyse.md`.

## Wat je nooit doet

- **Btw afleiden uit het grootboek of uit een eerdere boeking.** Dat de vorige factuur van
  deze leverancier op 21% stond, zegt niets over deze prestatie.
- **Aannemen dat btw op de factuur aftrekbare btw is.** Ten onrechte gefactureerde btw is
  wel verschuldigd door de leverancier, maar niet aftrekbaar bij ons.
- **Nederlandse regels toepassen op een buitenlandse factuur.** Bepaal eerst de plaats van
  de prestatie.
- **Privégebruik stil laten lopen.** Geen correctie is een keuze en die moet je kunnen
  uitleggen.
- **Een 0%-factuur voor bewijs van verlegging aanzien.** Geen btw op de factuur kan ook
  een fout van de leverancier zijn.

## Kantoorspecifiek

Heeft je kantoor eigen btw-boekingsregels (bijvoorbeeld voor stichtingen of
bankkosten), dan gaan die vóór. Twee regels gelden altijd:

- **Privé heeft nooit btw**, ook niet in het privédeel van een gesplitste boeking.
- **Restaurant zonder btw** -- dat is geen kantoorgewoonte maar
  art. 15 lid 5 Wet OB jo. art. 4 BUA. Zie `fiscale-feiten`.

## Voor de aangifte

De controles die je afloopt vóórdat een aangifte naar verificatie gaat, staan in
`references/aangiftecontroles.md`. Een niet-verklaard materieel verschil blokkeert; het is
geen aantekening.
