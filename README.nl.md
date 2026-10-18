[ 🌐 عربي ](README.ar.md) | [ 🇩🇪 Deutsch ](README.de.md) | [ 🇫🇷 Français ](README.fr.md) | [ 🇳🇱 Nederlands ](README.nl.md) | [ 🇪🇸 Español ](README.sp.md) | [ 🇬🇧 English ](README.md)

# Eigendom van investeringspools eerlijk volgen wanneer kapitaal op verschillende tijdstippen binnenkomt

<div align="center">

![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Microsoft%20Excel-217346)
![Domain](https://img.shields.io/badge/domain-Fund%20NAV%20Accounting-orange)

**Ontworpen voor investeringspools, syndicaten en handelsgroepen waarin deelnemers kapitaal aanbieden over meerdere data heen en een transparante, continu bijgewerkte eigendomsregistratie nodig hebben.**

[Live demo](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/) | [Koop de volledige Excel-versie (gratis)](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

</div>

Volg het eigendom van elke deelnemer continu, los dilutie automatisch op op boekhoudkundig niveau en onderhoud één controleerbare registratie van elk saldo—bijgewerkt bij elke transactie.

---

## Snelle preview
<img width="1536" height="1024" alt="ChatGPT Image May 18, 2026, 04_56_08 PM" src="https://github.com/user-attachments/assets/42e2fe30-0173-45cc-945a-0d066ac2c974" />
<img width="1672" height="941" alt="ChatGPT Image May 18, 2026, 04_56_14 PM" src="https://github.com/user-attachments/assets/1b9a5b9c-5037-4e2a-8ddb-fd1584d48a5c" />
<img width="1448" height="1086" alt="ChatGPT Image May 18, 2026, 04_56_17 PM" src="https://github.com/user-attachments/assets/71d0cb5b-76f8-4152-b13d-0b58f792e9bc" />


> Bekijk het interactieve boekhoudkundige model: [demo van de NAV- en unitization-simulator voor pools](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/)

---

## Waarom dit bestaat

De meeste geschillen over investeringspools worden niet veroorzaakt door slechte bedoelingen.

Ze ontstaan omdat vaste percentages, gemengde instapdata en handmatige toerekening van winst en verlies moeilijk te verzoenen zijn wanneer een deelnemer uitstapt—met name maanden of jaren nadat de posities werden vastgelegd die de onenigheid veroorzaakten.

Het risico is structureel:

```text
New capital contributed
-> Percentage split adjusted manually
-> Prior market gains not ring-fenced
-> Dispute surfaces at withdrawal
```

Deze werkmap verandert de workflow:

```text
New capital contributed
-> Units issued at current NAV
-> Prior participants' balances unaffected
-> Ownership tracked continuously from day one
```

Het commerciële probleem is niet alleen eerlijkheid. Het is operationele helderheid. Poolbeheerders, thesauriers en hoofdinvesteerders moeten precies weten wat elke deelnemer toekomt—op elk moment, niet alleen op het moment dat iemand vraagt om uit te stappen.

---

## Drie toerekeningsvalkuilen die zelfs poolbeheerders vangen

### Valkuil 1 — Statische percentages verkeerd begrepen als eerlijk eigendom

Procentueel eigendom voelt intuïtief aan. Het valt uiteen op het moment dat twee deelnemers op verschillende data instappen in een stijgende pool.

Een pool ter waarde van $130,000 na een winst van 30 % ontvangt een bijdrage van $65,000. Als de nieuwe deelnemer 33 % eigendom direct tegen de huidige poolwaarde ontvangt, wordt de winst van 30 % vóór instap van de oorspronkelijke deelnemer nu gedeeltelijk gedeeld met iemand die daar niet bij betrokken was. Het cijfer lijkt intern consistent. De economie is dat niet.

Poolbeheerders die vaste percentages toewijzen bij de bijdrage—in plaats van instap te waarderen tegen de huidige marktwaarde—ondercompenseren vroegere deelnemers routinematig zonder het te merken. De fout accumuleert in stilte. Hij komt naar buiten bij afslag.

### Valkuil 2 — XIRR toegepast op een eigendomsprobleem dat het niet kan oplossen

XIRR berekent een geannualiseerd rendement over één stroom van cashflows. Het beantwoordt: *Welk rendement behaalde deze investeerder over deze periode?* Het beantwoordt niet: *Wat is het huidige saldo van deze investeerder, en hoeveel ontvangt hij vandaag bij uitstap?*

Dat zijn verschillende vragen. Beheerders die XIRR als toerekeningsmechanisme gebruiken, lossen een rapportageprobleem over rendement op met een tool voor prestatiemeting.

Om het te laten werken moet per deelnemer een aparte rendementsstroom worden berekend, na elke transactie opnieuw worden gerekend en de resulterende saldi handmatig worden verzoend wanneer nieuw kapitaal binnenkomt. De berekening is geldig op het moment van uitvoering. Hij handhaaft geen voortdurende staat. Elke storting, opname of boekhoudkundige winst-en-verliespost vereist een nieuwe handmatige run en een nieuwe verzoenronde.

Beheerders die individuele rendements met XIRR volgen en daaruit huidige saldi afleiden, koppelen twee problemen aan één tool—en genereren bij elke kapitaalverplaatsing verzoeningsgaten.

### Valkuil 3 — Dilutie-effecten berekend na afwikkeling

In modellen met vaste percentages wordt het economische effect van een nieuwe bijdrage doorgaans opgelost in de volgende verzoenperiode, niet op het moment dat kapitaal binnenkomt. Tegen die tijd is de instapprijs van de nieuwe deelnemer niet meer zichtbaar in het grootboek. Alleen huidige saldi blijven over.

Dit creëert een structurele dubbelzinnigheid die niet achteraf kan worden opgelost: als de pool 25 % steeg tussen de instap van een vroege investeerder en de instap van een latere investeerder, en beiden procentueel eigendom ontvingen toegekend op het latere tijdstip, dan is het timingvoordeel van de vroege investeerder stilzwijgend geabsorbeerd in de statische verdeling.

De fout zit niet in andermans rekenwerk. Hij zit in het boekhoudkundige model. En hij wordt meestal ontdekt op het slechtst mogelijke moment—wanneer iemand probeert te vertrekken.

---

## Voor wie dit tool is

| Gebruiker | Praktische use case |
|---|---|
| Thesauriers van investeringsclubs | Eigendom per lid volgen over onregelmatige bijdragedata zonder handmatige herberekening |
| Syndicaatbeheerders | Instappen en uitstappen van kapitaalpartners beheren zonder procentuele verdelingen elke keer opnieuw te onderhandelen |
| Beheerders van kleine fondsen | Een transparante, controleerbare registratie onderhouden zonder institutionele boekhoudsoftware |
| Coördinatoren van family offices | Winsten en verliezen eerlijk verdelen over familieleden die op verschillende tijdstippen bijdragen |
| Leiders van discretionaire handelsgroepen | Units uitgeven wanneer nieuw kapitaal bijkomt; opnamen afwikkelen tegen een verifieerbare huidige waarde.

Het meest geschikt voor pools met 3–20 deelnemers met gemengde bijdragetiming, waar institutionele software voor fondsbeheer onbetaalbaar is maar handmatige spreadsheet-toerekening geen schone antwoorden meer oplevert.

---

## Wat de werkmap doet

### Transactiegrootboek
Één invoerpunt voor gegevens voor stortingen, opnamen en winst-en-verliesgebeurtenissen van de markt. Leg elke transactie één keer vast; unitaantallen, NAV en saldi per deelnemer werken automatisch bij op de achtergrond.

### NAV-berekeningsengine
De netto actieve waarde wordt continu herberekend naarmate winst en verlies van de markt wordt vastgelegd. Het saldo van elke deelnemer is afgeleid van huidige NAV × gehouden units—niet van een procentagetabel die handmatig onderhoud vereist.

### Uitgifte en terugkoop van units
Stortingen kopen units tegen de huidige NAV. Opnames lossen units in tegen de huidige NAV. Nieuwe binnenkomers ontvangen units gewaardeerd tegen de marktwaarde op het moment van instap, niet tegen pari. De geaccumuleerde winsten van eerdere deelnemers worden structureel behouden—geen handmatige ring-fencing vereist.

### Dashboard per deelnemer
Het huidige saldo, het unitaantal, het eigendomspercentage, de instap-NAV en de bijdragehistorie van elke deelnemer zijn in real time zichtbaar. Geen handmatige herberekening. Geen verzoeningscyclus vereist om de vraag te beantwoorden: *wat komt deze investeerder nu toe?*

### Controleerbare registraties
Elke transactie wordt vastgelegd met datum, NAV bij transactie, uitgegeven of ingeloste units en resulterende saldi. De registraties zijn gestructureerd voor review, export en geschillenbeslechting vanaf de eerste boeking.

---

## Voorbeeldscenario

<!-- SCREENSHOT PLACEHOLDER: Before/after comparison or ledger entry view — recommended 1200 × 700 -->

**Poolprofiel:** 8 deelnemers. Bijdragen verspreid over 18 maanden. De poolwaarde groeide ongeveer 40 % in die periode. Beheerd door de leidende deelnemer in een gedeelde handmatige spreadsheet.

**Het probleem:** Drie deelnemers stapten toe op verschillende momenten tijdens de groeiperiode. De hoofdinvesteerder paste de eigendomspercentages aan bij elke instap. Winst en verlies werd maandelijks verdeeld op basis van de huidige percentagetabel.

Toen twee vroege deelnemers volledige terugname aanvroegen, ontstonden drie gelijktijdige geschillen: één over de juiste behandeling van een daling van 15 % die plaatsvond tussen de instapdata van de eerste en tweede cohort; één over een bijdrage die in de verkeerde maand was vastgelegd; en één over welk percentage gold voor de laatste deelmaand voor uitstap.

De reconstructie vereiste het met de hand traceren van 18 maanden aan handmatige toerekeningsboekingen. Het proces duurde drie weken, vereiste een externe accountant en leidde ertoe dat een deelnemer een bedrag accepteerde dat afweek van zijn werkelijke aanspraak in plaats van het geschil voort te zetten.

| | Voor | Na |
|---|---|---|
| Eigendomsmodel | Vaste percentages, handmatig aangepast bij elke bijdrage | Unitgebaseerde NAV; units uitgegeven tegen de huidige marktwaarde bij storting |
| Behandeling van nieuwe binnenkomers | Percentage onderhandeld bij instap; eerdere winsten niet afgeschermd | Units gekocht tegen de huidige NAV; eerdere deelnemers structureel onaangetast |
| Toerekening van winst en verlies | Handmatige herberekening tegen de percentagetabel elke periode | Automatisch via NAV-beweging; unitaantallen onveranderd |
| Afwikkeling van opnamen | Saldi reconstrueren uit historische percentageboekingen | Units inlossen tegen de huidige NAV; saldo direct uit de status van het grootboek aflezen |
| Geschiloppervlak | Elk handmatig verzoenpunt | Opgelost op boekhoudkundig niveau |

---

## Waarom NAV-boekhouding zo werkt

De boekhouding van beleggingsfondsen heeft de unit-/NAV-structuur specifiek overgenomen omdat de timing van investeerders een economisch eerlijkheidsprobleem creëert dat statisch eigendom niet kan oplossen zonder handmatige interventie op elk transactiepunt.

Een deelnemer die op dag 90 in een stijgende pool heeft bijgedragen, deelde niet de risico-exposure van een deelnemer die op dag 1 instapte. Hen te behandelen als equivalente eigenaars vereist het negeren van het economische verschil in hun instapvoorwaarden—wat vaste percentages per opzet doen.

De unit-structuur codeert timing direct: de prijs per unit bij instap weerspiegelt de waarde van de pool op het moment van bijdrage. Marktbewegingen na instap stromen door NAV-veranderingen, niet door percentageaanpassingen. Opnamen worden verrekend tegen de huidige marktwaarde. De boekhouding produceert op elk moment een continue, verifieerbare staat zonder een handmatige correctiecyclus.

Daarom gebruikt elk gereguleerd beleggingsfonds—beleggingsfondsen, ETF's, hedge funds—NAV-boekhouding als eigendomsregistratie. De structuur is niet ontwikkeld voor compliance. Hij is ontwikkeld omdat het het enige mechanisme is dat alle vier de eigendomszorgen gelijktijdig aanpakt:

| Zorg | Aangepakt door |
|---|---|
| Timing van kapitaalinstap | Aankoopprijs van de unit (NAV op stortingsdatum) |
| Marktperformance | NAV-beweging; unitaantallen onveranderd |
| Omvang van de bijdrage | Uitgegeven hoeveelheid units |
| Dilutie door nieuwe binnenkomers | Uitgegeven tegen de huidige NAV; niet tegen pari |

Nuttige referenties:
- [CFA Institute: Pooled Investment Vehicles](https://www.cfainstitute.org)
- [IOSCO: Principles for the Valuation of Collective Investment Schemes](https://www.iosco.org)
- [FASB ASC 946: Financial Services — Investment Companies](https://www.fasb.org)

---

## Hoe unit-uitgifte en NAV werken

De netto actieve waarde van de pool is gelijk aan de totale marktwaarde gedeeld door de uitstaande units. Wanneer nieuw kapitaal binnenkomt, koopt het units tegen de huidige NAV—niet tegen pari. Markt winsten en verliezen veranderen de NAV; zij veranderen de unitaantallen niet.

| Gebeurtenis | Poolwaarde | Uitstaande units | NAV per unit |
|---|---|---|---|
| Investeerder A stort $100,000 | $100,000 | 100,000 | $1.00 |
| Marktwinst: +30 % | $130,000 | 100,000 | $1.30 |
| Investeerder B stort $65,000 | $195,000 | 150,000 | $1.30 |
| Marktverlies: −15 % | $165,750 | 150,000 | $1.105 |
| Investeerder A lost 50,000 units in | $110,250 | 100,000 | $1.105 |

**Het mechanisme in cijfers:**
Investeerder B stapt in tegen een NAV van $1.30—niet tegen pari—en ontvangt 50,000 units voor $65,000. Na een verlies van 15 % houdt investeerder B 50,000 × $1.105 = $55,250 vast. Investeerder B absorbeerde precies zijn proportionele aandeel van de daling ten opzichte van zijn instappunt. De winst van 30 % vóór instap van investeerder A werd niet overgedragen.

**Het model met vaste percentages in hetzelfde scenario:**
Investeerder B krijgt bij instap 33 % eigendom toegekend (een bijdrage van $65K in een pool van $195K). Dat percentage wordt dan direct toegepast op alle toekomstige winst en verlies. Bij de volgende verzoening ontvangt investeerder B 33 % van het verlies van 15 %—maar de winst van 30 % die investeerder A verdiende vóór de instap van investeerder B wordt nu ook gedeeltelijk toegerekend volgens dezelfde percentagetabel. De twee economisch verschillende perioden zijn samengesmolten tot één eigendomscijfer.

Het NAV-model scheidt ze structureel. De percentageberekening wordt een gevolg van unitaantallen, geen managementbeslissing die bij elke periodegrens wordt genomen.

Voor een pool met 8 deelnemers en tweewekelijkse transactieactiviteit zijn dat 8 continue saldoberekeningen die bij elke storting, opname en winst-en-verliesboeking worden bijgewerkt—zonder een handmatige aanpassingscyclus.

---

## Logica van de werkmap

De werkmap is georganiseerd rond een praktische workflow voor poolbeheer:

1. Voer deelnemersinformatie en openingsbijdragen in.
2. Geef units uit tegen de huidige NAV voor elke storting.
3. Leg winst en verlies van de markt vast wanneer het zich voordoet—dagelijks, wekelijks of maandelijks.
4. Los units in tegen de huidige NAV voor elk opnameverzoek.
5. Bekijk saldi, unitaantallen en eigendomspercentages per deelnemer op elk moment.
6. Exporteer de transactiehistorie voor verzoening, belastingdocumentatie of geschilsreview.
7. Controleer op invoerhiaten of saldo-inconsistenties voordat een distributie wordt uitgevoerd.

De werkmap is bedoeld als tool voor besluitondersteuning en boekhoudkundige transparantie. Hij vervangt geen gekwalificeerd juridisch advies over de structuur van het fonds, de belastingbehandeling van toerekeningen aan investeerders of de naleving van regelgeving in de jurisdictie van de beheerder.

---

## Aankoop

Gebruik hier de volledige Excel-werkmap:

[Koop de volledige Excel-tracker](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

---

## Beperkingen

- **Afhankelijkheid van gegevensintegriteit** — NAV-berekeningen zijn niet nauwkeuriger dan de boekingen; ontbrekende, verkeerd gedateerde of verkeerd geclassificeerde transacties produceren zonder waarschuwing onjuiste saldi
- **Geen juridisch of fiscaal advies** — deze werkmap weerspiegelt standaard NAV-boekhoudprincipes; de belastingbehandeling van unittoekenningen en uitkeringen aan investeerders varieert per jurisdictie en moet worden gevalideerd met gekwalificeerde adviseurs
- **Alleen handmatige gegevensinvoer** — marktwaarden moeten handmatig worden ingevoerd; de werkmap maakt geen verbinding met externe prijsfeeds, broker-API's of portfoliomanagementsystemen
- **Reikwijdte: alleen contante stortingen, opnamen en winst-en-verlies van de markt — carried interest-structuren, performance fee-watervallen, opgelopen inkomensuitkeringen en pools met meerdere valuta omvatten voorwaarden die in deze versie niet zijn gecodeerd
- **Plafond voor schaal** — ontworpen voor pools met 3–20 deelnemers bij wekelijkse tot maandelijkse transactiefrequentie; hogere volumes kunnen de prestaties van Excel verslechteren
- **Gevoeligheid voor Excel-versie** — vereist Excel 2016 of later op Windows; het gedrag in Excel voor Mac of Office 365 web kan afwijken
- **Randgevallen niet volledig geautomatiseerd** — side pocket-toekenningen, bepalingen over opgesloten kapitaal en gefaseerde inlossingspoorten omvatten regulatorische of contractuele voorwaarden die handmatige behandeling vereisen die in deze versie niet zijn gecodeerd

---

## Over dit project

Deze werkmap maakt deel uit van een bredere inspanning om complexe operationele en financiële boekhoudvereisten om te zetten in lichte tools die kleine en middelgrote organisaties daadwerkelijk kunnen gebruiken.

Geen abonnement op software voor fondsbeheer. Geen maatwerkontwikkelingsproject. Geen extra accounts.

Alleen heldere boekhoudlogica, gestructureerde transactiegegevens en reproduceerbare eigendomsberekeningen—geleverd in software die uw team al heeft.

Als uw operatie toerekenings-, verzoenings- of eigendomstrackingproblemen kent Als uw operatie toerekenings-, verzoenings- of eigendomstrackingproblemen kent die nu in het mentale model van iemand of in een losgekoppelde spreadsheet leven, [bekijk wat er verder beschikbaar is →](https://www.theseusworkshop.com)

---

## Licentie

Gedistribueerd onder de [MIT-licentie](https://opensource.org/licenses/MIT).
