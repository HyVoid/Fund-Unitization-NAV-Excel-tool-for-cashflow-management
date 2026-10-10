[ 🇫🇷 Français ](README.fr.md) | [ 🇬🇧 English ](README.md)

# Track Investment Pool Ownership Fairly When Capital Enters at Different Times

<div align="center">

![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Microsoft%20Excel-217346)
![Domain](https://img.shields.io/badge/domain-Fund%20NAV%20Accounting-orange)

**Designed for investment pools, syndicates, and trading groups where participants contribute capital across multiple dates and need a transparent, continuously updated ownership ledger.**

[Live Demo](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/) | [Purchase Complete Excel (free)](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

</div>

Track individual participant ownership continuously, resolve dilution automatically at the accounting layer, and maintain a single auditable record of every balance — updated at every transaction.

---

## Quick Preview
<img width="1536" height="1024" alt="ChatGPT Image May 18, 2026, 04_56_08 PM" src="https://github.com/user-attachments/assets/42e2fe30-0173-45cc-945a-0d066ac2c974" />
<img width="1672" height="941" alt="ChatGPT Image May 18, 2026, 04_56_14 PM" src="https://github.com/user-attachments/assets/1b9a5b9c-5037-4e2a-8ddb-fd1584d48a5c" />
<img width="1448" height="1086" alt="ChatGPT Image May 18, 2026, 04_56_17 PM" src="https://github.com/user-attachments/assets/71d0cb5b-76f8-4152-b13d-0b58f792e9bc" />


> View the interactive accounting model: [fund unitization NAV simulator demo](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/)

---

## Why This Exists

Most investment pool disputes are not caused by bad intentions.

They happen because fixed percentages, mixed entry dates, and manual P&L allocation are difficult to reconcile when a participant withdraws — especially months or years after the positions that caused the disagreement were established.

The risk is structural:

```text
New capital contributed
-> Percentage split adjusted manually
-> Prior market gains not ring-fenced
-> Dispute surfaces at withdrawal
```

This workbook changes the workflow:

```text
New capital contributed
-> Units issued at current NAV
-> Prior participants' balances unaffected
-> Ownership tracked continuously from day one
```

The commercial problem is not only fairness. It is operational clarity. Pool operators, treasurers, and lead investors need to know exactly what each participant is owed — at any point in time, not only at the moment someone asks to exit.

---

## Three Allocation Traps That Catch Pool Operators

### Trap 1 — Static percentages misread as fair ownership

Percentage ownership feels intuitive. It breaks down the moment two participants enter a rising pool at different dates.

A pool worth $130,000 after a 30% gain issues a $65,000 contribution. If the new participant receives 33% ownership directly against the current pool value, the original participant's 30% pre-entry gain is now partially shared with someone who was not present for it. The number looks internally consistent. The economics are not.

Pool operators who assign flat percentages at contribution — rather than pricing entry at the current market value — routinely undercompensate early participants without realising it. The error accumulates silently. It surfaces at exit.

### Trap 2 — XIRR applied to an ownership problem it cannot solve

XIRR computes an annualized return on a single stream of cash flows. It answers: *What return did this investor earn over this period?* It does not answer: *What is this investor's current balance, and how much do they receive if they exit today?*

These are different questions. Operators who use XIRR as an allocation mechanism are solving a return-reporting problem with a performance-measurement tool.

Making it work requires computing a separate return stream per participant, recalculating after every transaction, and manually reconciling resulting balances when new capital enters. The calculation is valid at the moment it runs. It maintains no continuous state. Every deposit, withdrawal, or P&L entry requires a fresh manual run and a new reconciliation pass.

Operators who track individual returns with XIRR and then derive current balances from those returns are stitching together two problems with one tool — and generating reconciliation gaps each time capital moves.

### Trap 3 — Dilution effects calculated after settlement

In fixed-percentage models, the economic impact of a new contribution is typically resolved at the next reconciliation period, not at the moment capital enters. By then, the entry price of the new participant is no longer visible in the ledger. Only current balances remain.

This creates a structural ambiguity that cannot be resolved retroactively: if the pool rose 25% between an early investor's entry and a later investor's entry, and both received percentage ownership assigned at the later date, the early investor's timing advantage has been silently absorbed into the static split.

The error is not in anyone's arithmetic. It is in the accounting model. And it is usually discovered at the worst possible moment — when someone is trying to leave.

---

## Who This Tool Is For

| User | Practical Use Case |
|---|---|
| Investment club treasurers | Track per-member ownership across irregular contribution dates without manual recalculation |
| Syndicate operators | Manage capital partner entries and exits without renegotiating percentage splits each time |
| Small fund administrators | Maintain a transparent, auditable ledger without institutional accounting software |
| Family office coordinators | Allocate gains and losses fairly across family members contributing at different times |
| Discretionary trading group leads | Issue units when new capital joins; settle withdrawals at a verifiable current value |

Best suited for pools with 3–20 participants running mixed contribution timing, where institutional fund administration software is cost-prohibitive but manual spreadsheet allocation no longer produces clean answers.

---

## What The Workbook Does

### Transaction Ledger
A single data entry point for deposits, withdrawals, and market P&L events. Log each transaction once; unit counts, NAV, and per-participant balances update automatically in the background.

### NAV Calculation Engine
Net Asset Value recalculates continuously as market P&L is recorded. Every participant's balance derives from current NAV × units held — not from a percentage table that requires manual maintenance.

### Unit Issuance and Redemption
Deposits purchase units at the current NAV. Withdrawals redeem units at the current NAV. New entrants receive units priced at market value at the time of entry, not at par. Earlier participants' accumulated gains are preserved structurally — no manual ring-fencing required.

### Per-Participant Dashboard
Each participant's current balance, unit count, ownership percentage, entry NAV, and contribution history is visible in real time. No manual recalculation. No reconciliation cycle required to answer the question: *what is this investor owed right now?*

### Audit-Ready Records
Every transaction is logged with date, NAV at transaction, units issued or redeemed, and resulting balances. Records are structured for review, export, and dispute resolution from the first entry.

---

## Example Scenario

<!-- SCREENSHOT PLACEHOLDER: Before/after comparison or ledger entry view — recommended 1200 × 700 -->

**Pool profile:** 8 participants. Contributions spread across 18 months. Pool value grew approximately 40% over that period. Managed by the lead participant in a shared manual spreadsheet.

**The problem:** Three participants joined at different points during the growth period. The lead investor adjusted ownership percentages at each entry. P&L was distributed monthly based on the current percentage table.

When two early participants requested full redemptions, three simultaneous disputes arose: one over the correct treatment of a 15% drawdown that occurred between the first and second cohort's entry dates; one over a contribution that had been recorded in the wrong month; and one over which percentage applied to the final partial month before exit.

Reconstruction required tracing 18 months of manual allocation entries by hand. The process took three weeks, required an external accountant, and resulted in one participant accepting a figure different from their actual entitlement rather than continue the dispute.

| | Before | After |
|---|---|---|
| Ownership model | Fixed percentages, manually adjusted at each contribution | Unit-based NAV; units issued at current market value on deposit |
| New entrant treatment | Percentage negotiated at entry; prior gains not ring-fenced | Units purchased at current NAV; prior participants unaffected structurally |
| P&L allocation | Manual recalculation against percentage table each period | Automatic via NAV movement; unit counts unchanged |
| Withdrawal settlement | Reconstruct balances from historical percentage entries | Redeem units at current NAV; balance read directly from ledger state |
| Dispute surface | Any manual reconciliation point | Resolved at the accounting layer |

---

## Why NAV Accounting Works This Way

Mutual fund accounting adopted the unit/NAV structure specifically because investor timing creates an economic fairness problem that static ownership cannot resolve without manual intervention at every transaction point.

A participant who contributed into a rising pool on day 90 did not share the risk exposure of a participant who entered on day 1. Treating them as equivalent ownership holders requires ignoring the economic difference in their entry conditions — which static percentages do by design.

The unit structure encodes timing directly: the price paid per unit at entry reflects the pool's value at the moment of contribution. Market movement after entry flows through NAV changes, not through percentage adjustments. Withdrawals clear at current market value. The accounting produces a continuous, verifiable state at every point in time without requiring a manual correction cycle.

This is why every regulated investment fund — mutual funds, ETFs, hedge funds — uses NAV accounting as its ownership ledger. The structure was not developed for compliance. It was developed because it is the only mechanism that handles all four ownership concerns simultaneously:

| Concern | Handled by |
|---|---|
| Timing of capital entry | Unit purchase price (NAV at deposit date) |
| Market performance | NAV movement; unit counts unchanged |
| Contribution size | Unit quantity issued |
| Dilution from new entrants | Units issued at current NAV; not at par |

Useful references:
- [CFA Institute: Pooled Investment Vehicles](https://www.cfainstitute.org)
- [IOSCO: Principles for the Valuation of Collective Investment Schemes](https://www.iosco.org)
- [FASB ASC 946: Financial Services — Investment Companies](https://www.fasb.org)

---

## How Unit Issuance and NAV Work

The pool's Net Asset Value equals total market value divided by outstanding units. When new capital enters, it purchases units at the current NAV — not at par. Market gains and losses change the NAV; they do not change unit counts.

| Event | Pool Value | Units Outstanding | NAV per Unit |
|---|---|---|---|
| Investor A deposits $100,000 | $100,000 | 100,000 | $1.00 |
| Market gain: +30% | $130,000 | 100,000 | $1.30 |
| Investor B deposits $65,000 | $195,000 | 150,000 | $1.30 |
| Market loss: −15% | $165,750 | 150,000 | $1.105 |
| Investor A redeems 50,000 units | $110,250 | 100,000 | $1.105 |

**The mechanism in numbers:**
Investor B enters at NAV $1.30 — not at par — and receives 50,000 units for $65,000. After a 15% loss, Investor B holds 50,000 × $1.105 = $55,250. Investor B absorbed exactly their proportional share of the drawdown relative to their entry point. Investor A's 30% pre-entry gain was not transferred.

**The static percentage model in the same scenario:**
Investor B is assigned 33% ownership at entry (a $65K contribution into a $195K pool). That percentage is then applied against all future P&L directly. At the next reconciliation, Investor B receives 33% of the 15% loss — but the 30% gain that Investor A earned before Investor B's entry is now also partially allocated according to the same percentage table. The two economically distinct periods have been merged into one ownership number.

The NAV model separates them structurally. The percentage calculation becomes a consequence of unit counts, not a management decision made at each period boundary.

For a pool with 8 participants and bi-weekly transaction activity, that is 8 continuous balance calculations updating on every deposit, withdrawal, and P&L record — without a manual adjustment cycle.

---

## Workbook Logic

The workbook is organized around a practical pool administration workflow:

1. Enter participant information and opening contributions.
2. Issue units at the current NAV for each deposit.
3. Record market P&L as it occurs — daily, weekly, or monthly.
4. Redeem units at the current NAV for each withdrawal request.
5. Review per-participant balances, unit counts, and ownership percentages at any point.
6. Export transaction history for reconciliation, tax documentation, or dispute review.
7. Check for input gaps or balance inconsistencies before any distribution is made.

The workbook is intended as a decision-support and accounting transparency tool. It does not replace qualified legal advice on fund structure, tax treatment of investor allocations, or regulatory compliance in the operator's jurisdiction.

---

## Purchase

Use the complete Excel workbook here:

[Purchase the complete Excel tracker](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

---

## Limitations

- **Data integrity dependency** — NAV calculations are only as accurate as the entries; missing, incorrectly dated, or misclassified transactions produce incorrect balances without warning
- **Not legal or tax advice** — this workbook reflects standard NAV accounting principles; tax treatment of unit allocations and investor distributions varies by jurisdiction and should be validated with qualified advisors
- **Manual data entry only** — market values must be entered manually; the workbook does not connect to external price feeds, brokerage APIs, or portfolio management systems
- **Scope: cash deposits, withdrawals, and market P&L only** — carried interest structures, performance fee waterfalls, accrued income distributions, and multi-currency pools involve conditions not encoded in this version
- **Scale ceiling** — designed for pools with 3–20 participants at weekly-to-monthly transaction frequency; higher volume may degrade Excel performance
- **Excel version sensitivity** — requires Excel 2016 or later on Windows; behaviour in Excel for Mac or Office 365 web may differ
- **Edge cases not fully automated** — side pocket allocations, locked-up capital provisions, and staged redemption gates involve regulatory or contractual conditions that require manual handling not encoded in this version

---

## About This Project

This workbook is part of a broader effort to translate complex operational and financial accounting requirements into lightweight tools that small and medium-sized organizations can actually use.

No fund administration software subscription. No custom development project. No additional accounts.

Just clear accounting logic, structured transaction data, and repeatable ownership calculations — delivered in software your team already has.

If your operation involves allocation, reconciliation, or ownership tracking problems that currently live in someone's mental model or a disconnected spreadsheet, [see what else is available →](https://www.theseusworkshop.com)

---

## License

Distributed under the [MIT License](https://opensource.org/licenses/MIT).
