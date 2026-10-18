[ 🌐 عربي ](README.ar.md) | [ 🇩🇪 Deutsch ](README.de.md) | [ 🇫🇷 Français ](README.fr.md) | [ 🇳🇱 Nederlands ](README.nl.md) | [ 🇪🇸 Español ](README.sp.md) | [ 🇬🇧 English ](README.md)

# Répartir equitablement la détention des parts d’un fonds d’investissement lorsque les apports arrivent à des dates différentes

<div align="center">

![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Microsoft%20Excel-217346)
![Domain](https://img.shields.io/badge/domain-Fund%20NAV%20Accounting-orange)

**Conçu pour les fonds d'investissement, les consortiums et les groupes de négociation où les participants apportent des capitaux à des dates multiples et ont besoin d'un registre de détention transparent, mis à jour en permanence.**

[Démo en ligne](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/) | [Acheter l'Excel complet (gratuit)](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

</div>

Suivez la détention de chaque participant en continu, résolvez automatiquement la dilution au niveau comptable et conservez un seul enregistrement auditable de chaque solde — mis à jour à chaque transaction.

---

## Aperçu rapide
<img width="1536" height="1024" alt="ChatGPT Image May 18, 2026, 04_56_08 PM" src="https://github.com/user-attachments/assets/42e2fe30-0173-45cc-945a-0d066ac2c974" />
<img width="1672" height="941" alt="ChatGPT Image May 18, 2026, 04_56_14 PM" src="https://github.com/user-attachments/assets/1b9a5b9c-5037-4e2a-8ddb-fd1584d48a5c" />
<img width="1448" height="1086" alt="ChatGPT Image May 18, 2026, 04_56_17 PM" src="https://github.com/user-attachments/assets/71d0cb5b-76f8-4152-b13d-0b58f792e9bc" />


> Consultez le modèle comptable interactif : [démo du simulateur d'unitisation du fonds (NAV)](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/)

---

## Pourquoi cet outil existe

La plupart des litiges entre pools d'investissement ne sont pas dus à de mauvaises intentions.

Ils surviennent parce que les pourcentages fixes, les dates d'entrée hétérogènes et l'imputation manuelle du P&L sont difficiles à rapprocher lorsqu'un participant se retire — surtout des mois ou des années après l'établissement des positions ayant provoqué le désaccord.

Le risque est structurel :

```text
New capital contributed
-> Percentage split adjusted manually
-> Prior market gains not ring-fenced
-> Dispute surfaces at withdrawal
```

Ce classeur change le mode de fonctionnement :

```text
New capital contributed
-> Units issued at current NAV
-> Prior participants' balances unaffected
-> Ownership tracked continuously from day one
```

Le problème commercial ne porte pas uniquement sur l'équité. Il porte sur la clarté opérationnelle. Les gérants de pool, les trésoriers et les investisseurs référents doivent savoir exactement ce qui revient à chaque participant — à tout moment, et pas uniquement au moment où quelqu'un demande à sortir.

---

## Trois pièges de répartition qui piègent les gérants de pool

### Piège 1 — Des pourcentages fixes pris pour une détention équitable

La détention en pourcentage paraît intuitive. Elle s'effondre dès que deux participants entrent dans un pool en hausse à des dates différentes.

Un pool valent $130,000 après une hausse de 30 % reçoit un apport de $65,000. Si le nouveau participant reçoit 33 % de détention directement calculés sur la valeur actuelle du pool, la hausse de 30 % réalisée par le participant initial avant son entrée se trouve alors partagée en partie avec quelqu'un qui n'était pas présent pour la réaliser. Le chiffre paraît cohérent sur le papier. L'économie ne l'est pas.

Les gérants de pool qui attribuent des pourcentages plats au moment de l'apport — plutôt que de valoriser l'entrée à la valeur de marché actuelle — sous-compensent régulièrement les premiers participants sans s'en rendre compte. L'erreur s'accumule en silence. Elle ressurgit au moment de la sortie.

### Piège 2 — Le XIRR appliqué à un problème de détention qu'il ne peut pas résoudre

Le XIRR calcule un rendement annualisé sur un flux unique de trésorerie. Il répond à : *Quel rendement cet investisseur a-t-il obtenu sur cette période ?* Il ne répond pas à : *Quel est le solde actuel de cet investisseur, et combien reçoit-il s'il sort aujourd'hui ?*

Ce sont deux questions différentes. Les gérants qui utilisent le XIRR comme mécanisme de répartition résolvent un problème de reporting de rendement avec un outil de mesure de performance.

Pour le faire fonctionner, il faut calculer un flux de rendement distinct par participant, recalculer après chaque transaction et rapprocher manuellement les soldes obtenus lorsque de nouveaux capitaux entrent. Le calcul est valide au moment où il s'exécute. Il ne maintient aucun état continu. Chaque dépôt, chaque retrait ou chaque saisie de P&L exige une nouvelle exécution manuelle et une nouvelle passe de rapprochement.

Les gérants qui suivent les rendements individuels avec le XIRR puis en déduisent les soldes actuels associent deux problèmes avec un seul outil — et créent des écarts de rapprochement à chaque mouvement de capitaux.

### Piège 3 — Les effets de dilution calculés après le règlement

Dans les modèles à pourcentages fixes, l'impact économique d'un nouvel apport est généralement résolu à la période de rapprochement suivante, et non au moment où les capitaux entrent. À ce stade, le prix d'entrée du nouveau participant n'apparaît plus dans le registre. Seuls les soldes actuels subsistent.

Cela crée une ambiguïté structurelle qui ne peut pas être résolue rétroactivement : si le pool a progressé de 25 % entre l'entrée d'un investisseur précoce et celle d'un investisseur ultérieur, et que les deux ont reçu une détention en pourcentage attribuée à la date la plus tardive, l'avantage de temporalité de l'investisseur précoce a été silencieusement absorbé dans la répartition statique.

L'erreur ne réside dans aucun calcul. Elle réside dans le modèle comptable. Et elle est généralement découverte au pire moment — quand quelqu'un essaie de partir.

---

## À qui s'adresse cet outil

| Utilisateur | Cas d'usage pratique |
|---|---|
| Trésoriers de clubs d'investissement | Suivre la détention de chaque membre entre des dates d'apport irrégulières sans recalcul manuel |
| Gérants de consortium | Gérer les entrées et les sorties des apporteurs de capitaux sans renégocier la répartition en pourcentage à chaque fois |
| Administrateurs de petits fonds | Tenir un registre transparent et auditable sans logiciel de comptabilité institutionnel |
| Coordinateurs de family office | Répartir équitablement les gains et les pertes entre les membres d'une famille qui apportent à des périodes différentes |
| Responsables de groupes de négociation discrétionnaires | Émettre des parts lorsque de nouveaux capitaux arrivent ; régler les retraits à une valeur actuelle vérifiable |

Idéal pour les pools de 3 à 20 participants avec des apports échelonnés, où les logiciels institutionnels d'administration de fonds sont hors de portée financière mais où la répartition manuelle sous tableur ne fournit plus de réponses propres.

---

## Ce que fait le classeur

### Registre des transactions
Un point de saisie unique pour les dépôts, les retraits et les événements de P&L de marché. Enregistrez chaque transaction une seule fois ; les quantités de parts, la NAV et les soldes par participant se mettent à jour automatiquement en arrière-plan.

### Moteur de calcul de la NAV
La valeur nette d'actifs se recalcule en continu au fur et à mesure que le P&L de marché est saisi. Le solde de chaque participant découle de la NAV courante × les parts détenues — et non d'un tableau de pourcentages exigeant une mise à jour manuelle.

### Émission et rachat de parts
Les dépôts achètent des parts à la NAV courante. Les retraits rachètent des parts à la NAV courante. Les nouveaux entrants reçoivent des parts valorisées à la valeur de marché au moment de l'entrée, et non à la valeur nominale. Les gains accumulés des participants antérieurs sont préservés structurellement — aucun ring-fencing manuel n'est requis.

### Tableau de bord par participant
Le solde actuel, le nombre de parts, le pourcentage de détention, la NAV d'entrée et l'historique des apports de chaque participant sont visibles en temps réel. Aucun recalcul manuel. Aucun cycle de rapprochement n'est nécessaire pour répondre à la question : *que doit cet investisseur maintenant ?*

### Enregistrements prêts pour l'audit
Chaque transaction est enregistrée avec sa date, la NAV au moment de l'opération, les parts émises ou rachetées et les soldes qui en résultent. Les enregistrements sont structurés pour la revue, l'export et la résolution des litiges dès la première saisie.

---

## Exemple de scénario

<!-- SCREENSHOT PLACEHOLDER: Before/after comparison or ledger entry view — recommended 1200 × 700 -->

**Profil du pool :** 8 participants. Apports répartis sur 18 mois. La valeur du pool a progressé d'environ 40 % sur cette période. Géré par le participant principal dans un tableur manuel partagé.

**Le problème :** trois participants ont rejoint le pool à différents moments de la période de croissance. L'investisseur référent ajustait les pourcentages de détention à chaque entrée. Le P&L était réparti mensuellement sur la base du tableau de pourcentages en vigueur.

Lorsque deux participants précoces ont demandé le rachat total de leurs parts, trois litiges simultanés ont éclaté : l'un sur le traitement correct d'un repli de 15 % survenu entre les dates d'entrée de la première et de la seconde cohorte ; l'un sur un apport qui avait été enregistré dans le mauvais mois ; et l'un sur le pourcentage applicable au dernier mois partiel avant la sortie.

La reconstitution a exigé le suivi manuel de 18 mois d'écritures de répartition. Le processus a pris trois semaines, a nécessité un comptable externe et s'est conclu par l'acceptation, par un participant, d'un montant différent de son droit réel, plutôt que de poursuivre le litige.

| | Avant | Après |
|---|---|---|
| Modèle de détention | Pourcentages fixes, ajustés manuellement à chaque apport | NAV par parts ; parts émises à la valeur de marché courante lors du dépôt |
| Traitement du nouvel entrant | Pourcentage négocié à l'entrée ; gains antérieurs non ring-fencés | Parts achetées à la NAV courante ; participants antérieurs structurellement affectés |
| Imputation du P&L | Recalcul manuel sur le tableau des pourcentages à chaque période | Automatique via l'évolution de la NAV ; nombre de parts inchangé |
| Règlement des retraits | Reconstitution des soldes à partir des pourcentages historiques | Rachat de parts à la NAV courante ; solde lu directement dans l'état du registre |
| Surface de litige | Chaque point de rapprochement manuel | Résolu au niveau comptable |

---

## Pourquoi la comptabilité en NAV fonctionne ainsi

La comptabilité des fonds d'investissement a adopté la structure parts/NAV précisément parce que le calendrier d'entrée des investisseurs crée un problème d'équité économique que la détention statique ne peut pas résoudre sans intervention manuelle à chaque point de transaction.

Un participant qui a apporté des capitaux dans un pool en hausse au 90e jour n'a pas partagé l'exposition au risque d'un participant entré au 1er jour. Les traiter comme des détenteurs équivalents suppose d'ignorer la différence économique entre leurs conditions d'entrée — ce que les pourcentages statiques font par conception.

La structure en parts encode le calendrier directement : le prix payé par part à l'entrée reflète la valeur du pool au moment de l'apport. Les mouvements de marché après l'entrée passent par les variations de la NAV, et non par des ajustements de pourcentages. Les retraits se règlement à la valeur de marché courante. La comptabilité produit un état continu et vérifiable à tout moment, sans exiger de cycle de correction manuelle.

C'est pourquoi chaque fonds d'investissement réglementé — fonds de placement collectif, ETF, fonds spéculatifs — utilise la comptabilité en NAV comme registre de détention. Cette structure n'a pas été développée pour des raisons de conformité. Elle a été développée parce qu'il s'agit du seul mécanisme qui traite simultanément les quatre préoccupations liées à la détention :

| Préoccupation | Traité par |
|---|---|
| Calendrier d'entrée des capitaux | Prix d'achat de la part (NAV à la date du dépôt) |
| Performance de marché | Évolution de la NAV ; nombre de parts inchangé |
| Taille de l'apport | Quantité de parts émise |
| Dilution due aux nouveaux entrants | Parts émises à la NAV courante ; pas à la valeur nominale |

Références utiles :
- [CFA Institute : véhicules d'investissement collectifs](https://www.cfainstitute.org)
- [IOSCO : principes pour l'évaluation des fonds d'investissement collectifs](https://www.iosco.org)
- [FASB ASC 946 : services financiers — sociétés d'investissement](https://www.fasb.org)

---

## Comment fonctionnent l'émission de parts et la NAV

La valeur nette d'actifs du pool est égale à la valeur de marché totale divisée par le nombre de parts en circulation. Lorsque de nouveaux capitaux entrent, ils achètent des parts à la NAV courante — et non à la valeur nominale. Les gains et pertes de marché modifient la NAV ; ils ne modifient pas le nombre de parts.

| Événement | Valeur du pool | Parts en circulation | NAV par part |
|---|---|---|---|
| L'investisseur A dépose $100,000 | $100,000 | 100,000 | $1.00 |
| Gain de marché : +30 % | $130,000 | 100,000 | $1.30 |
| L'investisseur B dépose $65,000 | $195,000 | 150,000 | $1.30 |
| Perte de marché : −15 % | $165,750 | 150,000 | $1.105 |
| L'investisseur A rachète 50,000 parts | $110,250 | 100,000 | $1.105 |

**Le mécanisme en chiffres :**
L'investisseur B entre à la NAV de $1.30 — et non à la valeur nominale — et reçoit 50,000 parts pour $65,000. Après une perte de 15 %, l'investisseur B détient 50,000 × $1.105 = $55,250. L'investisseur B a absorbé exactement sa quote-part proportionnelle du repli par rapport à son point d'entrée. La hausse de 30 % réalisée par l'investisseur A avant l'entrée de l'investisseur B n'a pas été transférée.

**Le modèle en pourcentages fixes dans le même scénario :**
33 % de détention sont attribués à l'investisseur B à son entrée (un apport de $65K dans un pool de $195K). Ce pourcentage est ensuite appliqué directement à tous les P&L futurs. Lors du rapprochement suivant, l'investisseur B reçoit 33 % de la perte de 15 % — mais la hausse de 30 % que l'investisseur A avait réalisée avant l'entrée de l'investisseur B est désormais elle aussi répartie en partie selon le même tableau de pourcentages. Les deux périodes économiquement distinctes ont été fusionnées en un seul chiffre de détention.

Le modèle en NAV les sépare structurellement. Le calcul en pourcentage devient une conséquence du nombre de parts, et non une décision de gestion prise à chaque clôture de période.

Pour un pool de 8 participants avec une activité transactionnelle bimensuelle, cela représente 8 calculs de soldes continus mis à jour à chaque dépôt, retrait et saisie de P&L — sans cycle d'ajustement manuel.

---

## Logique du classeur

Le classeur est structuré autour d'un flux pratique d'administration de pool :

1. Saisir les informations des participants et les apports initiaux.
2. Émettre des parts à la NAV courante pour chaque dépôt.
3. Enregistrer le P&L de marché au fur et à mesure qu'il survient — quotidien, hebdomadaire ou mensuel.
4. Racheter des parts à la NAV courante pour chaque demande de retrait.
5. Consulter à tout moment les soldes, les quantités de parts et les pourcentages de détention de chaque participant.
6. Exporter l'historique des transactions pour rapprochement, documentation fiscale ou examen des litiges.
7. Vérifier l'absence de lacunes de saisie ou d'incohérences de soldes avant toute distribution.

Le classeur est conçu comme un outil d'aide à la décision et de transparence comptable. Il ne remplace pas un conseil juridique qualifié sur la structuration d'un fonds, le traitement fiscal des répartions entre investisseurs ou la conformité réglementaire dans la juridiction de l'opérateur.

---

## Achat

Utilisez le classeur Excel complet ici :

[Acheter le suivi Excel complet](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

---

## Limites

- **Dépendance à l'intégrité des données** — les calculs de NAV ne sont aussi exacts que les saisies ; les transactions manquantes, mal datées ou mal classées produisent des soldes erronés sans aucun avertissement
- **Ce n'est pas un conseil juridique ou fiscal** — ce classeur reflète les principes standard de la comptabilité en NAV ; le traitement fiscal des répartitions de parts et des distributions aux investisseurs varie selon la juridiction et doit être validé avec des conseillers qualifiés
- **Saisie manuelle uniquement** — les valeurs de marché doivent être saisies manuellement ; le classeur ne se connecte à aucun flux de prix externe, API de courtage ni système de gestion de portefeuille
- **Périmètre : dépôts, retraits et P&L de marché uniquement** — les structures de carried interest, les cascades de commissions de performance, les distributions de revenus accumulés et les pools multi-devises impliquent des conditions qui ne sont pas encodées dans cette version
- **Plafond d'échelle** — conçu pour des pools de 3 à 20 participants avec une fréquence de transaction hebdomadaire à mensuelle ; un volume supérieur peut dégrader les performances d'Excel
- **Sensibilité à la version d'Excel** — nécessite Excel 2016 ou une version ultérieure sous Windows ; le comportement dans Excel pour Mac ou dans Office 365 web peut différer
- **Cas particuliers non entièrement automatisés** — les allocations en side pocket, les dispositions de capital verrouillé et les seuils de rachat échelonnés impliquent des conditions réglementaires ou contractuelles qui nécessitent un traitement manuel non encodé dans cette version

---

## À propos de ce projet

Ce classeur fait partie d'une démarche plus large visant à traduire des exigences complexes de comptabilité opérationnelle et financière en outils légers que les organisations de petite et moyenne taille peuvent réellement utiliser.

Aucun abonnement à un logiciel d'administration de fonds. Aucun projet de développement sur mesure. Aucun compte supplémentaire.

Simplement une logique comptable claire, des données de transaction structurées et des calculs de détention reproductibles — fournis dans un logiciel que votre équipe possède déjà.

Si votre activité implique des problèmes de répartition, de rapprochement ou de suivi de la détention qui résident aujourd'hui dans la tête de quelqu'un ou dans un tableur déconnecté, [dDécouvrez ce qui est disponible par ailleurs →](https://www.theseusworkshop.com)

---

## Licence

Distribué sous la [licence MIT](https://opensource.org/licenses/MIT).
