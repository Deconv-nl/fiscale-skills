---
name: fiscale-feiten
description: De vastgelegde Nederlandse fiscale regels, tarieven, drempels en termijnen die het kantoor dagelijks raakt, met jaartal en bron per regel. Raadpleeg dit bij het boeken, bij een btw-aangifte en bij elke vraag over een tarief, een drempel, een aftrekbeperking of een termijn.
---

# Fiscale feiten

Dit is de feitenlaag. `fiscaal-onderzoek` beschrijft *hoe* je iets uitzoekt; hier staat
*wat* er al is uitgezocht.

Hij bestaat omdat de agent niet altijd wetsteksten kan ophalen. Zonder vastgelegde
feiten heeft hij twee opties: gokken, of alles voorleggen. Deze skill maakt een derde
mogelijk.

De bedragen voor 2026 zijn op 06-09-2026 geverifieerd bij de Belastingdienst.

## Dit bestand is niet de waarheid

Lees dit voordat je één bedrag hieruit gebruikt.

**De officiële bron is leidend. Altijd.** Wat hier staat is een *gedateerde kopie* van wat
op 06-09-2026 bij de Belastingdienst en in de wet stond. Kopieën verouderen, originelen
niet. Wijkt dit bestand af van de bron, dan heeft de bron gelijk en is dit bestand kapot.

Waarom er dan toch een kopie is: de agent die de administraties verwerkt kan
`belastingdienst.nl` en `wetten.overheid.nl` niet bereiken. Zonder deze kopie kan hij
alleen gokken of alles voorleggen. Het is een noodvoorziening voor precies die ene
omgeving, en geen naslagwerk.

Daaruit volgen drie regels:

1. **Heb je een webgereedschap, gebruik het.** Kun je de Belastingdienst of de wet
   bereiken, kijk daar en niet hier. Wijkt het af, werk dit bestand bij en meld het.
2. **Elk bedrag draagt een jaartal, en dat is bindend.** `jaarbedrag` (2026) betekent:
   bruikbaar voor 2026 en voor niets anders. Voor een ander jaar is dit bestand géén bron.
3. **Verzin niets bij.** Staat een regel er niet in, dan is het antwoord
   `AANVULLENDE_INFORMATIE_NODIG`, niet een herinnering.

## De Vpb-rekenmodule heeft eigen cijfers

Er is nog een plek in deze repository waar fiscale bedragen staan: `vpb_preparation/`,
de Vpb-aangiftevoorbereiding. `vpb_preparation/engine.py` draagt in `RULES` een
volledige, hardgecodeerde set -- tarieven, KIA-staffel, gemengde kosten, earnings
stripping, verliesverrekening -- met de officiële bronnen en een verificatiedatum erbij.

**Voor een Vpb-berekening is die module de bron, niet dit bestand.** Dit bestand is er om
te lezen en te herkennen; de module rekent. Ze mogen niet uiteenlopen.

Twee dingen om te weten:

- **De module staat op belastingjaar 2025** (`RULESET_VERSION = "nl-vpb-2025-calculation-v1"`)
  en weigert elk ander jaar. Dat is bewust fail-closed: hij rekent liever niet dan fout.
- **De cijfers hier zijn van 2026 en die van de module van 2025.** Ze hóren dus te
  verschillen -- de KIA-staffel is tussen die jaren gewijzigd. Zie je een verschil, tel dan
  eerst de jaartallen op elkaar voordat je het een fout noemt.

Wordt de module op 2026 gezet, dan worden de cijfers hier en daar gelijkgetrokken in
diezelfde taak. Gebeurt dat niet, dan hebben we twee waarheden en dat is precies wat deze
paragraaf moet voorkomen.

## De statussen

**1. Lees de status.** Elke regel draagt er een:

| Status | Betekenis | Wat je ermee mag |
| --- | --- | --- |
| `vastgesteld` | structurele regel, verandert niet jaarlijks | gebruiken als grondslag, betrouwbaarheid `HOOG` |
| `jaarbedrag` | bedrag of percentage dat per jaar wijzigt | alleen gebruiken voor het genoemde jaar; ander jaar = opzoeken |
| `te-verifiëren` | opgeschreven maar niet tegen de bron gecontroleerd | **niet** als grondslag; als aanwijzing melden, mens laten nakijken |

**2. Lees het jaar.** Een `jaarbedrag` bij een ander belastingjaar is geen bron maar een
valstrik. Er staat niet "vermoedelijk ook 2027" en dat is opzettelijk.

**3. Staat het er niet, dan verzin je het niet.** Een ontbrekende regel is
`AANVULLENDE_INFORMATIE_NODIG`, geen uitnodiging tot herinneren. Dit bestand is bewust
klein; het groeit door wat er in het werk langskomt, niet door aanvulling uit het hoofd.

## Wat hier bewust níét in staat

De **btw-tarieven per administratie** komen uit het boekhoudpakket, per boekingsdatum.
Dat is een levende bron en die wint het van elke lijst. De 21% en 9% in
`references/btw.md` staan er om te herkennen wat je ziet, niet om mee te rekenen -- neem
het tarief dat het boekhoudpakket voor die datum en die administratie teruggeeft.

## Wat waar staat

- `references/btw.md` -- tarieven, aftrek, BUA, privégebruik, herziening, aangifte
- `references/inkomstenbelasting.md` -- winst uit onderneming, ondernemersfaciliteiten,
  auto, werkruimte
- `references/vennootschapsbelasting.md` -- tarief, DGA, gebruikelijk loon,
  aftrekbeperkingen
- `references/loonheffingen-wkr.md` -- werkkostenregeling, vrije ruimte, gerichte
  vrijstellingen, normbedragen, bijtelling; plus waar het Handboek Loonheffingen staat
- `references/formeel.md` -- termijnen, bewaarplicht, suppletie, boetes

## Hoe je hem bijwerkt

Een regel komt hier terecht wanneer hij in het werk is uitgezocht, niet wanneer iemand
hem kent. Noteer per regel: de regel zelf, de bron met artikel, het jaar, de status, en
de datum waarop hij is vastgelegd.

Verander een bestaande regel nooit stil. Is hij gewijzigd, zet het oude jaartal erbij en
het nieuwe eronder -- een boeking uit 2024 heeft de regel van 2024 nodig, ook in 2027.

**In januari is er een vaste ronde.** Loop dan alle regels met status `jaarbedrag` langs
tegen de cijfers van het nieuwe jaar. Doe je dat niet, dan draagt elk bedrag hier een
jaartal dat inmiddels klopt noch opvalt -- en dat is precies de fout die deze statussen
moesten voorkomen.

Constateert iemand dat een regel hier fout is: dat is `fiscale-correctie`, niet een
edit-en-door.
