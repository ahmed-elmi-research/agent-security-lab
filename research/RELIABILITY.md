# Betrouwbaarheid onderzoeken

Status: voorgestelde werkwijze, 24 november 2026. Nog geen experiment uitgevoerd. Dit is onze toepassing van de bronnen hieronder; geen officiële norm, certificering of garantie op foutloosheid.

We onderscheiden de betrouwbaarheid van het onderzochte systeem van de betrouwbaarheid van ons onderzoek. Een mooie score kan ook door een slechte test ontstaan. Er is geen universeel beste methode: de vraag, gebruiksomstandigheden en gevolgen van fouten bepalen het ontwerp.

## Wat we meten
Voor het eerste onderzoek blijft de vraag beperkt tot autorisatie bij onderbreken en hervatten. Beoordeel afzonderlijk:
- Of toegestane taken worden voltooid.
- Of verboden handelingen plaatsvinden, hoe ernstig die zijn en of herstel mogelijk is.
- Of gedrag stabiel blijft bij herhalingen en vooraf gekozen variaties.
- Welke component faalt: model, agentbesturing, permissiecontrole, hulpmiddel of testomgeving.

Geen gecombineerde totaalscore die een ernstige overtreding wegmiddelt. Geen modelranglijst op basis van ons oefenprogramma.

## Werkwijze en controlemomenten
1. **Vraag afbakenen.** Ahmed beschrijft gewenste uitkomst, systeemgrens, gebruikssituatie en meetbare criteria. Een gedragsvoorspelling is een afzonderlijke stap. Beschrijf welke waarneming onze verklaring zou tegenspreken.
2. **Bestaand werk lezen.** Zoek primaire bronnen en bestaande implementaties. Leg per bron vast wat daadwerkelijk is gelezen en welke claim die ondersteunt. Gebruik AI voor zoekrichtingen, controleer bronnen zelf. Claim geen nieuwheid vooraf.
3. **Meetinstrument controleren.** Test de beoordelingscode op bekende goede, slechte en onvolledige gebeurtenislogs. Controleer echte toestand en uitgevoerde acties, niet alleen wat de agent zegt. Een onbekende uitkomst telt niet als geslaagd. Een taalmodel mag kwalitatief commentaar geven; feitelijke autorisatie-oordelen vereisen controleerbare criteria.
4. **Verkennende proef.** Gebruik eerst het lokale lab met synthetische gegevens. Verhelp meetfouten en bepaal welke omstandigheden zinvol zijn. Dit levert begrip op, nog geen algemene betrouwbaarheidsclaim.
5. **Bevestigende proef vooraf vastleggen.** Bevries criteria, model- en systeemversies, prompts, hulpmiddelen, data, budget, steekproefomvang, stopregel en uitsluitingsregels in een commit. Bewaar nieuwe gevallen apart van ontwikkelgevallen. Geen eindeloos aanpassen aan dezelfde eindtest; na inzage is een testset niet langer ongezien.
6. **Eerlijk vergelijken.** Gebruik dezelfde omstandigheden en vergelijkbare budgetten voor uitgangssysteem en maatregel. Varieer uitvoeringsvolgorde waar volgorde invloed kan hebben. Registreer herpogingen, mislukte runs en infrastructuurproblemen; selecteer geen gunstige uitkomsten achteraf.
7. **Onzekerheid rapporteren.** Toon aantallen en noemers per scenario, naast ruwe logs. Kies herhalingen op basis van de beoogde claim en haalbare precisie. Herhalingen op één taak zijn geen nieuwe onafhankelijke taken. Houd afhankelijkheid mee in analyse en intervallen; statistische conclusies zijn pas toegestaan met een passend analyseplan. Geen fouten gezien betekent niet dat fouten onmogelijk zijn.
8. **Tegenspraak organiseren.** Lees foutgevallen handmatig, probeer alternatieve verklaringen en voer gerichte verstoringen uit. Leg AI-kritiek apart vast. Laat later een externe menselijke reviewer de proef vanaf een schone omgeving herhalen. Menselijke review kan ook fouten bevatten.
9. **Beperkt publiceren en opnieuw testen.** Elke conclusie verwijst naar bewijs en noemt grenzen. Bewaar een gecorrigeerde versie met wijzigingsreden. Herhaal relevante regressietests na wijzigingen. Een uitslag geldt voor de geteste configuratie en omstandigheden; niet onbeperkt voor toekomstige modelversies.

## Twee onderzoeksfasen
**Fase A — didactisch en verkennend:** experiment 001 is een lokale simulatie. Herhalen van exact hetzelfde deterministische geval vergroot onze dekking niet. We controleren de uitvoering en verschillende scenario’s; er wordt geen statistische betrouwbaarheidsclaim afgeleid.

**Fase B — afzonderlijke empirische studie:** kies later een bestaand agentsysteem met vastgelegde versie en een omschreven populatie van taken/condities. Bepaal steekproef en analyse voor die claim. Statistiek kan relevant zijn voor variatie tussen taken én tussen modelruns; deterministische componenten maken de hele studie niet automatisch deterministisch. Ahmeds zelf ontworpen gevallen zijn niet onafhankelijk van hem: documenteer blootstelling en laat waar mogelijk externe gevallen opstellen.

## Eerste onderzoek: klein beginnen
Start met de vier voorgestelde vergelijkingen in [experiment 001](../experiments/001-resume-authorization/README.md). Ahmed vult eerst zelf eisen en voorspellingen in. Een controle die alles blokkeert kan veilig lijken, maar levert geen bruikbaar systeem op; daarom meten we ook toegestane taakvoltooiing.

Leg vast wanneer toestemming wijzigt ten opzichte van hervatten, de controle en de daadwerkelijke actie. De gebeurtenisvolgorde moet controleerbaar zijn. Timingvariaties en een onafhankelijke agentimplementatie komen pas na het leerlab, met een apart protocol. We kiezen nu geen willekeurig aantal runs als bewijs van betrouwbaarheid.

## Bronnen en leesstatus
- [NIST AI RMF, sectie 3](https://airc.nist.gov/airmf-resources/airmf/3-sec-characteristics/): de sectie is geraadpleegd. Betrouwbaarheid is contextgebonden; representatieve testcondities en gevolgen van fouten doen ertoe. Geen claim van volledige NIST-toetsing.
- [Anthropic — Demystifying evals for AI agents](https://www.anthropic.com/research/demystifying-evals-for-ai-agents), 9 januari 2026: structuur en beoordelingsmethoden geraadpleegd. De gerealiseerde uitkomst, herhaalde pogingen en controle van beoordelaars zijn belangrijk. Dit is praktijkadvies van een leverancier, geen onafhankelijke certificering.
- [Rabanser et al. — Towards a Science of AI Agent Reliability, v3](https://arxiv.org/abs/2602.16666v3): abstract en metadata geraadpleegd, volledige methodes nog te bestuderen. Het werk onderscheidt consistentie, robuustheid, voorspelbaarheid en veiligheid. We claimen de twaalf metrics uit het artikel niet te hebben geïmplementeerd.

Codex heeft de bronnen opgezocht en deze werkwijze opgesteld. Claude Code is gevraagd om methodologische kritiek op basis van de repo en aangeleverde bronsamenvattingen; dat vervangt geen eigen broncontrole of externe menselijke beoordeling.

## Methodologische AI-review
Claude Code beoordeelde op 24 november 2026 het voorgestelde protocol en experiment 001. Verwerkt: didactische en empirische fase scheiden, meten in het gebeurtenislogboek, toetsblootstelling benoemen, afwijkingen en afgebroken runs bewaren, en tijdsvolgorde vastleggen. Dit is geen validatie van resultaten; er zijn nog geen runs.
