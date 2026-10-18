[ 🌐 عربي ](README.ar.md) | [ 🇩🇪 Deutsch ](README.de.md) | [ 🇫🇷 Français ](README.fr.md) | [ 🇳🇱 Nederlands ](README.nl.md) | [ 🇪🇸 Español ](README.sp.md) | [ 🇬🇧 English ](README.md)

# Die Eigentümerschaft an Investmentpools fair verfolgen, wenn Kapital zu unterschiedlichen Zeitpunkten eintritt

<div align="center">

![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Microsoft%20Excel-217346)
![Domain](https://img.shields.io/badge/domain-Fund%20NAV%20Accounting-orange)

**Konzipiert für Investmentpools, Syndikate und Handelsgruppen, in denen Teilnehmer Kapital über mehrere Daten hinweg einzahlen und ein transparentes, kontinuierlich aktualisiertes Eigentumsregister benötigen.**

[Live-Demo](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/) | [Vollständige Excel-Version kaufen (kostenlos)](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

</div>

Verfolge die Eigentümerschaft jedes Teilnehmers kontinuierlich, löse Verwässerung automatisch auf Buchhaltungsebene auf und pflege einen einzigen prüffähigen Datensatz jedes Saldos—aktualisiert bei jeder Transaktion.

---

## Schnelle Vorschau
<img width="1536" height="1024" alt="ChatGPT Image May 18, 2026, 04_56_08 PM" src="https://github.com/user-attachments/assets/42e2fe30-0173-45cc-945a-0d066ac2c974" />
<img width="1672" height="941" alt="ChatGPT Image May 18, 2026, 04_56_14 PM" src="https://github.com/user-attachments/assets/1b9a5b9c-5037-4e2a-8ddb-fd1584d48a5c" />
<img width="1448" height="1086" alt="ChatGPT Image May 18, 2026, 04_56_17 PM" src="https://github.com/user-attachments/assets/71d0cb5b-76f8-4152-b13d-0b58f792e9bc" />


> Sieh dir das interaktive Buchhaltungsmodell an: [Demo des NAV- und Unitization-Simulators für Pools](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/)

---

## Warum es dieses Tool gibt

Die meisten Streitigkeiten in Investmentpools werden nicht durch schlechte Absichten verursacht.

Sie entstehen, weil feste Prozentsätze, gemischte Eintrittsdaten und manuelle GuV-Zuordnung schwer in Einklang zu bringen sind, wenn ein Teilnehmer aussteigt—insbesondere Monate oder Jahre nachdem die Positionen begründet wurden, die die Uneinigkeit verursacht haben.

Das Risiko ist strukturell:

```text
New capital contributed
-> Percentage split adjusted manually
-> Prior market gains not ring-fenced
-> Dispute surfaces at withdrawal
```

Diese Arbeitsmappe ändert den Workflow:

```text
New capital contributed
-> Units issued at current NAV
-> Prior participants' balances unaffected
-> Ownership tracked continuously from day one
```

Das wirtschaftliche Problem ist nicht nur Fairness. Es ist operative Klarheit. Pool-Betreiber, Schatzmeister und Lead-Investoren müssen genau wissen, was jedem Teilnehmer zusteht—zu jedem Zeitpunkt, nicht nur in dem Moment, in dem jemand den Ausstieg verlangt.

---

## Drei Zuordnungsfallen, in die selbst Pool-Betreiber tappen

### Falle 1 — Statische Prozentsätze, die als faire Eigentümerschaft missverstanden werden

Prozentuale Eigentümerschaft fühlt sich intuitiv an. Sie bricht in dem Moment zusammen, in dem zwei Teilnehmer zu unterschiedlichen Daten in einen steigenden Pool eintreten.

Ein Pool im Wert von $130,000 nach einem Gewinn von 30 % erhält eine Einzahlung von $65,000. Wenn der neue Teilnehmer 33 % Eigentümerschaft direkt gegen den aktuellen Poolwert erhält, wird der Gewinn von 30 % vor Eintritt des ursprünglichen Teilnehmers jetzt teilweise mit jemandem geteilt, der daran nicht beteiligt war. Die Zahl sieht intern konsistent aus. Die Ökonomie ist es nicht.

Pool-Betreiber, die pauschale Prozentsätze bei der Einzahlung zuweisen—anstatt den Eintritt zum aktuellen Marktwert zu bewerten—benachteiligen routinemäßig frühe Teilnehmer, ohne es zu merken. Der Fehler akkumuliert sich lautlos. Er tritt beim Ausstieg zutage.

### Falle 2 — XIRR auf ein Eigentumsproblem angewendet, das es nicht lösen kann

XIRR berechnet eine annualisierte Rendite auf einem einzigen Strom von Zahlungsströmen. Es beantwortet: *Welche Rendite hat dieser Investor über diesen Zeitraum erwirtschaftet?* Es beantwortet nicht: *Wie hoch ist der aktuelle Saldo dieses Investors, und wie viel erhält er, wenn er heute aussteigt?*

Das sind verschiedene Fragen. Betreiber, die XIRR als Zuordnungsmechanismus verwenden, lösen ein Rendite-Berichtsproblem mit einem Performance-Messwerkzeug.

Um es funktionieren zu lassen, muss ein separater Renditestrom pro Teilnehmer berechnet, nach jeder Transaktion neu berechnet und die resultierenden Salden manuell abgeglichen werden, wenn neues Kapital eintritt. Die Berechnung ist im Moment ihrer Ausführung gültig. Sie pflegt keinen kontinuierlichen Zustand. Jede Einzahlung, Auszahlung oder GuV-Buchung erfordert einen frischen manuellen Lauf und einen neuen Abstimmungsdurchgang.

Betreiber, die individuelle Renditen mit XIRR verfolgen und daraus aktuelle Salden ableiten, fügen zwei Probleme mit einem Werkzeug zusammen—und erzeugen bei jeder Kapitalbewegung Abstimmungslücken.

### Falle 3 — Verwässerungseffekte nach der Abwicklung berechnet

In Modellen mit festen Prozentsätzen wird die wirtschaftliche Auswirkung einer neuen Einzahlung typischerweise in der nächsten Abstimmungsperiode aufgelöst, nicht in dem Moment, in dem Kapital eintritt. Bis dahin ist der Einstiegspreis des neuen Teilnehmers im Register nicht mehr sichtbar. Es bleiben nur aktuelle Salden übrig.

Dies schafft eine strukturelle Mehrdeutigkeit, die nicht rückwirkend aufgelöst werden kann: Wenn der Pool zwischen dem Eintritt eines frühen Investors und dem Eintritt eines späteren Investors um 25 % gestiegen ist und beide die zu einem späteren Datum zugewiesene prozentuale Eigentümerschaft erhalten haben, wurde der Timing-Vorteil des frühen Investors lautlos in die statische Aufteilung absorbiert.

Der Fehler liegt in niemandes Arithmetik. Er liegt im Buchhaltungsmodell. Und er wird normalerweise im denkbar schlechtesten Moment entdeckt—wenn jemand versucht zu gehen.

---

## Für wen dieses Tool gedacht ist

| Benutzer | Praktischer Anwendungsfall |
|---|---|
| Schatzmeister von Investmentclubs | Eigentümerschaft pro Mitglied über unregelmäßige Einzahlungsdaten hinweg verfolgen, ohne manuelle Neuberechnung |
| Syndikatsbetreiber | Kapitalpartnereintritte und -austritte verwalten, ohne Prozentsatzaufteilungen jedes Mal neu zu verhandeln |
| Administratoren kleiner Fonds | Ein transparentes, prüffähiges Register ohne institutionelle Buchhaltungssoftware pflegen |
| Koordinatoren von Family Offices | Gewinne und Verluste fair auf Familienmitglieder verteilen, die zu unterschiedlichen Zeiten einzahlen |
| Leads diskretionärer Handelsgruppen | Anteile ausgeben, wenn neues Kapital hinzukommt; Auszahlungen zu einem überprüfbaren aktuellen Wert abwickeln |

Am besten geeignet für Pools mit 3–20 Teilnehmern bei gemischtem Einzahlungstiming, bei denen institutionelle Fondsverwaltungssoftware unerschwinglich ist, manuelle Tabellenkalkulationszuordnung aber keine sauberen Antworten mehr liefert.

---

## Was die Arbeitsmappe tut

### Transaktionsregister
Ein einziger Dateneingabepunkt für Einzahlungen, Auszahlungen und Markt-GuV-Ereignisse. Erfasse jede Transaktion einmal; Anteilsanzahlen, NAV und Salden pro Teilnehmer aktualisieren sich automatisch im Hintergrund.

### NAV-Berechnungs-Engine
Der Nettoinventarwert wird kontinuierlich neu berechnet, während Markt-GuV erfasst wird. Der Saldo jedes Teilnehmers leitet sich aus aktueller NAV × gehaltenen Anteilen ab—nicht aus einer Prozentsatztabelle, die manuelle Pflege erfordert.

### Ausgabe und Rücknahme von Anteilen
Einzahlungen kaufen Anteile zur aktuellen NAV. Auszahlungen lösen Anteile zur aktuellen NAV ein. Neueintretende erhalten Anteile, die zum Marktwert zum Zeitpunkt des Eintritts bewertet sind, nicht zu Nennwert. Die akkumulierten Gewinne früherer Teilnehmer werden strukturell erhalten—keine manuelle Abschottung erforderlich.

### Dashboard pro Teilnehmer
Der aktuelle Saldo, die Anteilsanzahl, der Eigentümerschaftsprozentsatz, die Einstiegs-NAV und der Einzahlungsverlauf jedes Teilnehmers sind in Echtzeit sichtbar. Keine manuelle Neuberechnung. Kein Abstimmungszyklus erforderlich, um die Frage zu beantworten: *was steht diesem Investor gerade zu?*

### Prüffertige Aufzeichnungen
Jede Transaktion wird mit Datum, NAV zur Transaktion, ausgegebenen oder eingelösten Anteilen und resultierenden Salden protokolliert. Die Aufzeichnungen sind für Prüfung, Export und Streitbeilegung ab dem ersten Eintrag strukturiert.

---

## Beispielszenario

<!-- SCREENSHOT PLACEHOLDER: Before/after comparison or ledger entry view — recommended 1200 × 700 -->

**Pool-Profil:** 8 Teilnehmer. Einzahlungen verteilt über 18 Monate. Der Poolwert stieg über diesen Zeitraum um etwa 40 %. Verwaltet vom Lead-Teilnehmer in einer gemeinsamen manuellen Tabelle.

**Das Problem:** Drei Teilnehmer traten zu verschiedenen Zeitpunkten während der Wachstumsphase bei. Der Lead-Investor passte die Eigentümerschaftsprozentsätze bei jedem Eintritt an. Die GuV wurde monatlich auf Basis der aktuellen Prozentsatztabelle verteilt.

Als zwei frühe Teilnehmer die vollständige Rücknahme beantragten, entstanden drei gleichzeitige Streitigkeiten: einer über die korrekte Behandlung eines 15%igen Rückgangs, der zwischen dem Eintrittsdatum des ersten und des zweiten Kohortenjahrgangs auftrat; einer über eine Einzahlung, die im falschen Monat erfasst worden war; und einer darüber, welcher Prozentsatz für den letzten Teilmonat vor dem Ausstieg galt.

Die Rekonstruktion erforderte die manuelle Nachverfolgung von 18 Monaten manueller Zuordnungseinträge. Der Prozess dauerte drei Wochen, erforderte einen externen Buchhalter und führte dazu, dass ein Teilnehmer eine Zahl akzeptierte, die von seinem tatsächlichen Anspruch abwich, anstatt den Streit fortzusetzen.

| | Vorher | Nachher |
|---|---|---|
| Eigentumsmodell | Feste Prozentsätze, bei jeder Einzahlung manuell angepasst | Anteilsbasierte NAV; Anteile werden bei Einzahlung zum aktuellen Marktwert ausgegeben |
| Behandlung von Neueintretenden | Bei Eintritt ausgehandelter Prozentsatz; frühere Gewinne nicht abgeschottet | Anteile zur aktuellen NAV gekauft; frühere Teilnehmer strukturell unbeeinflusst |
| GuV-Zuordnung | Manuelle Neuberechnung gegen die Prozentsatztabelle in jeder Periode | Automatisch über NAV-Bewegung; Anteilsanzahlen unverändert |
| Abwicklung von Auszahlungen | Salden aus historischen Prozentsatzeinträgen rekonstruieren | Anteile zur aktuellen NAV einlösen; Saldo direkt aus dem Registerzustand ablesen |
| Konfliktoberfläche | Jeder manuelle Abstimmungspunkt | Auf Buchhaltungsebene aufgelöst |

---

## Warum NAV-Buchhaltung so funktioniert

Die Fondsbuchhaltung hat die Anteils-/NAV-Struktur genau deshalb übernommen, weil das Timing der Investoren ein wirtschaftliches Fairnessproblem schafft, das statische Eigentümerschaft ohne manuellen Eingriff an jedem Transaktionspunkt nicht lösen kann.

Ein Teilnehmer, der am Tag 90 in einen steigenden Pool eingezahlt hat, teilte nicht die Risikoexposition eines Teilnehmers, der am Tag 1 eingetreten ist. Sie als gleichwertige Eigentümer zu behandeln erfordert, den wirtschaftlichen Unterschied ihrer Eintrittsbedingungen zu ignorieren—was feste Prozentsätze durch ihr Design tun.

Die Anteilsstruktur kodiert Timing direkt: Der pro Anteil beim Eintritt gezahlte Preis spiegelt den Wert des Pools im Moment der Einzahlung wider. Marktbewegungen nach dem Eintritt fließen durch NAV-Änderungen, nicht durch Prozentsatzanpassungen. Auszahlungen werden zum aktuellen Marktwert verrechnet. Die Buchhaltung erzeugt zu jedem Zeitpunkt einen kontinuierlichen, überprüfbaren Zustand, ohne einen manuellen Korrekturzyklus zu erfordern.

Deshalb verwendet jeder regulierte Investmentfonds—offene Investmentfonds, ETFs, Hedgefonds—NAV-Buchhaltung als sein Eigentumsregister. Die Struktur wurde nicht für Compliance entwickelt. Sie wurde entwickelt, weil sie der einzige Mechanismus ist, der alle vier Eigentumsbelange gleichzeitig handhabt:

| Belang | Handhabt durch |
|---|---|
| Timing des Kapitaleintritts | Kaufpreis des Anteils (NAV zum Einzahlungsdatum) |
| Marktperformance | NAV-Bewegung; Anteilsanzahlen unverändert |
| Höhe der Einzahlung | Ausgegebene Anteilsmenge |
| Verwässerung durch Neueintretende | Anteile zur aktuellen NAV ausgegeben; nicht zu Nennwert |

Nützliche Referenzen:
- [CFA Institute: Pooled Investment Vehicles](https://www.cfainstitute.org)
- [IOSCO: Principles for the Valuation of Collective Investment Schemes](https://www.iosco.org)
- [FASB ASC 946: Financial Services — Investment Companies](https://www.fasb.org)

---

## Wie Anteilsausgabe und NAV funktionieren

Der Nettoinventarwert des Pools entspricht dem gesamten Marktwert geteilt durch die ausstehenden Anteile. Wenn neues Kapital eintritt, kauft es Anteile zur aktuellen NAV—nicht zu Nennwert. Marktgewinne und -verluste ändern die NAV; sie ändern nicht die Anteilsanzahlen.

| Ereignis | Poolwert | Ausstehende Anteile | NAV pro Anteil |
|---|---|---|---|
| Investor A zahlt $100,000 ein | $100,000 | 100,000 | $1.00 |
| Marktgewinn: +30 % | $130,000 | 100,000 | $1.30 |
| Investor B zahlt $65,000 ein | $195,000 | 150,000 | $1.30 |
| Marktverlust: −15 % | $165,750 | 150,000 | $1.105 |
| Investor A löst 50,000 Anteile ein | $110,250 | 100,000 | $1.105 |

**Der Mechanismus in Zahlen:**
Investor B tritt zu einer NAV von $1.30 ein—nicht zu Nennwert—und erhält 50,000 Anteile für $65,000. Nach einem Verlust von 15 % hält Investor B 50,000 × $1.105 = $55,250. Investor B hat genau seinen proportionalen Anteil des Rückgangs relativ zu seinem Einstiegspunkt absorbiert. Der Gewinn von 30 % vor Eintritt von Investor A wurde nicht übertragen.

**Das Modell mit statischen Prozentsätzen im gleichen Szenario:**
Investor B werden beim Eintritt 33 % Eigentümerschaft zugewiesen (eine Einzahlung von $65K in einen Pool von $195K). Dieser Prozentsatz wird dann direkt auf alle künftige GuV angewendet. Bei der nächsten Abstimmung erhält Investor B 33 % des 15%igen Verlusts—aber der Gewinn von 30 %, den Investor A vor dem Eintritt von Investor B erwirtschaftet hat, wird jetzt ebenfalls teilweise nach derselben Prozentsatztabelle zugeordnet. Die beiden wirtschaftlich unterscheidbaren Perioden wurden zu einer einzigen Eigentumszahl verschmolzen.

Das NAV-Modell trennt sie strukturell. Die Prozentberechnung wird zur Folge der Anteilsanzahlen, nicht zu einer Managemententscheidung, die an jeder Periodengrenze getroffen wird.

Für einen Pool mit 8 Teilnehmern und zweiwöchentlicher Transaktionsaktivität sind das 8 kontinuierliche Saldoberechnungen, die sich bei jeder Einzahlung, Auszahlung und GuV-Buchung aktualisieren—ohne einen manuellen Anpassungszyklus.

---

## Logik der Arbeitsmappe

Die Arbeitsmappe ist um einen praktischen Pool-Verwaltungsworkflow herum organisiert:

1. Teilnehmerinformationen und Ersteinzahlungen eingeben.
2. Anteile zur aktuellen NAV für jede Einzahlung ausgeben.
3. Markt-GuV erfassen, wenn sie anfällt—täglich, wöchentlich oder monatlich.
4. Anteile zur aktuellen NAV für jede Auszahlungsanforderung einlösen.
5. Salden, Anteilsanzahlen und Eigentümerschaftsprozentsätze pro Teilnehmer jederzeit überprüfen.
6. Transaktionsverlauf für Abstimmung, Steuerdokumentation oder Streitprüfung exportieren.
7. Auf Eingabelücken oder Saldounstimmigkeiten prüfen, bevor eine Ausschüttung erfolgt.

Die Arbeitsmappe ist als Entscheidungsunterstützungs- und Buchhaltungstransparenzwerkzeug gedacht. Sie ersetzt keine qualifizierte Rechtsberatung zur Fondsstruktur, zur steuerlichen Behandlung von Investorenzuordnungen oder zur regulatorischen Compliance in der Rechtsordnung des Betreibers.

---

## Kauf

Verwende hier die vollständige Excel-Arbeitsmappe:

[Kaufe den vollständigen Excel-Tracker](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

---

## Einschränkungen

- **Abhängigkeit von der Datenintegrität** — NAV-Berechnungen sind nur so genau wie die Einträge; fehlende, falsch datierte oder falsch klassifizierte Transaktionen erzeugen ohne Warnung falsche Salden
- **Keine Rechts- oder Steuerberatung** — diese Arbeitsmappe spiegelt Standard-NAV-Buchhaltungsprinzipien wider; die steuerliche Behandlung von Anteilszuordnungen und Investorenausschüttungen variiert je nach Rechtsordnung und sollte mit qualifizierten Beratern validiert werden
- **Nur manuelle Dateneingabe** — Marktwerte müssen manuell eingegeben werden; die Arbeitsmappe stellt keine Verbindung zu externen Preisfeeds, Broker-APIs oder Portfoliomanagementsystemen her
- **Umfang: nur Bareinzahlungen, -auszahlungen und Markt-GuV** — Carried-Interest-Strukturen, Performance-Fee-Wasserfälle, abgegrenzte Ertragsausschüttungen und Multiwährungspools beinhalten Bedingungen, die in dieser Version nicht codiert sind
- **Größenobergrenze** — konzipiert für Pools mit 3–20 Teilnehmern bei wöchentlicher bis monatlicher Transaktionsfrequenz; höheres Volumen kann die Excel-Leistung beeinträchtigen
- **Empfindlichkeit gegenüber der Excel-Version** — erfordert Excel 2016 oder höher unter Windows; das Verhalten in Excel für Mac oder Office 365 Web kann abweichen
- **Randfälle nicht vollständig automatisiert** — Side-Pocket-Zuordnungen, Bestimmungen zu gesperrtem Kapital und gestaffelte Rücknahmetore beinhalten regulatorische oder vertragliche Bedingungen, die eine manuelle Behandlung erfordern, die in dieser Version nicht codiert ist

---

## Über dieses Projekt

Diese Arbeitsmappe ist Teil eines breiteren Bemühens, komplexe betriebliche und finanzielle Buchhaltungsanforderungen in leichtgewichtige Werkzeuge zu übersetzen, die kleine und mittlere Organisationen tatsächlich nutzen können.

Kein Abonnement für Fondsverwaltungssoftware. Kein individuelles Entwicklungsprojekt. Keine zusätzlichen Konten.

Nur klare Buchhaltungslogik, strukturierte Transaktionsdaten und wiederholbare Eigentumsberechnungen—geliefert in Software, die dein Team bereits hat.

Wenn dein Betrieb Zuordnungs-, Abstimmungs- oder Eigentumsverfolgungsprobleme betrifft, die derzeit im Kopfmodell von jemandem oder in einer getrennten Tabelle leben, [sieh dir an, was sonst verfügbar ist →](https://www.theseusworkshop.com)

---

## Lizenz

Vertrieben unter der [MIT-Lizenz](https://opensource.org/licenses/MIT).
