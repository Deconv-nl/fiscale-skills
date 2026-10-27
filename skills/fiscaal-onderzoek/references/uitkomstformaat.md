# Uitkomstformaat

Geef het resultaat zo terug dat een mens het kan lezen én een volgende stap het kan
gebruiken. Laat velden weg die niet spelen; verzin ze niet vol.

```yaml
vraag:
belastingsoort:        # OB | IB | Vpb | LB | formeel
belastingjaar:
tijdvak:

feiten:
  vastgesteld: []
  afgeleid: []
  ontbrekend: []

conclusie:
behandeling:           # concreet: welke boeking, welk tarief, welke rubriek

grondslag:
  - bron:
    artikel:
    geldig:
    relevantie:

rechtspraak:
  - ecli:
    instantie:
    datum:
    relevantie:

beleid:
  - bron:
    datum:
    relevantie:

redenering:
  regel:
  toepassing:
  conclusie:

alternatieven: []
onzekerheden: []

betrouwbaarheid: HOOG | MIDDEL | LAAG
toelichting_betrouwbaarheid:
mens_nodig: true | false
reden_mens_nodig:
vervolgacties: []
```

## De betrouwbaarheid

**HOOG** -- de feiten zijn compleet en de regel is niet in geschil. Je hebt de bron
gelezen, of hij staat in `fiscale-feiten` met status `vastgesteld` en het juiste jaar.

**MIDDEL** -- de regel is duidelijk maar de kwalificatie van de feiten vergt een oordeel,
of je grondslag is uitleg (niveau 6) in plaats van wet.

**LAAG** -- er ontbreekt een materieel feit, bronnen spreken elkaar tegen, je kon geen
bron raadplegen, of de rechtsvraag is werkelijk open.

Bij `LAAG` staat `mens_nodig: true`. Altijd.

Een getal achter de betrouwbaarheid mag, maar vervangt de toelichting nooit: "80%" zegt
niemand iets, "de factuur noemt de prestatiedatum niet" wel.

## Als er niet genoeg is om te concluderen

Geef `AANVULLENDE_INFORMATIE_NODIG` als conclusie, en zet in `vervolgacties` **de vraag
zoals hij gesteld moet worden** -- aan de klant, aan de collega, of als vraagpost. Niet
"meer informatie nodig", maar "vraag de leverancier om een factuur op naam van de
onderneming, met vermelding van de prestatiedatum".

Een openstaande vraag die niet is opgeschreven als vraag, wordt niet gesteld.
