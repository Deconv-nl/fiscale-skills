# Fiscale skills van Deconv

Vijf skills voor Claude Code die helpen bij Nederlandse fiscale vragen in de boekhoudpraktijk:

| Skill | Waarvoor |
| --- | --- |
| `fiscaal-btw` | Btw-behandeling van een transactie bepalen en een btw-aangifte controleren |
| `fiscaal-onderzoek` | De fiscaal juiste behandeling uitzoeken, met bronnen uit het juiste tijdvak |
| `fiscale-correctie` | Melden dat een boeking, regel of aangifte fiscaal niet klopt |
| `fiscale-feiten` | Vastgelegde tarieven, drempels en termijnen, met jaartal en bron |
| `fiscale-verificatie` | Een aangifte of standpunt onafhankelijk controleren (tweede paar ogen) |

## Installeren

Zeg tegen Claude Code:

> Installeer de fiscale skills van Deconv: https://github.com/deconv-nl/fiscale-skills

Of typ zelf in Claude Code:

```
/plugin marketplace add deconv-nl/fiscale-skills
/plugin install fiscale-skills@deconv-nl
```

Bijwerken naar de nieuwste versie: `/plugin marketplace update deconv-nl`.

## Instructies voor een AI-assistent

Vraagt een gebruiker je deze skills te installeren:

1. Werk je in Claude Code met de `/plugin`-opdracht, voer dan uit:
   `/plugin marketplace add deconv-nl/fiscale-skills` en daarna
   `/plugin install fiscale-skills@deconv-nl`. Laat de gebruiker deze regels zelf typen als
   jij geen slash-opdrachten kunt uitvoeren.
2. Anders: kopieer de vijf mappen uit `skills/` van deze repository naar
   `~/.claude/skills/` (Windows: `%USERPROFILE%\.claude\skills\`), bijvoorbeeld:
   `git clone https://github.com/deconv-nl/fiscale-skills /tmp/fiscale-skills && cp -R /tmp/fiscale-skills/skills/* ~/.claude/skills/`
3. Zeg de gebruiker Claude Code opnieuw te starten.

## Let op

- De tarieven en bedragen zijn vastgelegd en geverifieerd op 06-09-2026. Controleer ze
  voor latere jaren zelf bij de Belastingdienst.
- Deze skills zijn hulpmiddelen, geen fiscaal advies. Een mens blijft verantwoordelijk
  voor wat er wordt geboekt en ingediend.
- De materialiteitsgrens in `fiscaal-onderzoek` is een eigen afspraak; pas hem aan naar
  je eigen praktijk.

Licentie: MIT.
