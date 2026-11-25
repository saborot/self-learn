# AWS: Week 8 Day 3, cost vs reliability trade-offs

- **Date:** 2026-11-25 (Wed), ledger `W01-Wed`
- **Actual minutes:** 30 (his estimate)
- **Status:** done

## Covered
Short refresher at his request: reliability spend buys down risk; compare redundancy cost with expected downtime cost; over-provisioning vs intentional headroom; each extra nine costs much more; cost optimization = value per dollar. Then the 4 pending questions, a trade-off table, and an explain-back.

## His answers (summary) and feedback
1. **Cheapest isn't best:** cheap means accepting outage risk, judged against business impact. *Feedback:* correct; make the comparison explicit (savings vs likelihood × duration × cost of downtime); hidden costs too (RTO/RPO, 2 a.m. toil, TCO).
2. **Over-provisioning vs headroom:** first answer defined headroom by size ("medium load, not worst case"). *Feedback:* the difference is intent, not size; the N+1 across 3 AZs example. Restated correctly: over-provisioning is unexamined "peace of mind" spend; headroom is a deliberate allowance for a named event so the system doesn't degrade or crash. Added: headroom also covers known load spikes and scale-up lag.
3. **Checkout vs internal tool:** user-facing, tied directly to revenue. *Feedback:* the driver is cost of downtime, not being user-facing; second-order costs (lost sales don't return, trust, SLA, support load).
4. **Cost optimization means:** "spending resources wisely; every spend justified." *Feedback:* drop the circular "optimized"; it's business value per dollar, and it can mean spending more.

## Artifact: trade-off table (checkout vs internal tool)
He needed a worked example first (I used login service vs wiki) and pushed back on exact pricing; I said rough ratios are fine. Iterations:
- Checkout 100% → corrected to **99.99%** (no system is 100%; each nine costs more).
- Internal tool 90% (≈36 days/yr) → 99.95% (inconsistent with single AZ / "staff can wait") → **99.9%**, accepted as the upper edge for single AZ.
- Final: checkout = 99.99%, multi-AZ + automatic failover + N+1, ~$1,500/mo, high and immediate downtime cost; decision: pay, because 1 h of outage costs more than 6 months of redundancy. Internal tool = 99.9%, single AZ, ~$80/mo, low and deferrable; decision: run cheap, because it is tolerable and recoverable without significant business impact.
- Key lesson: **the availability target must be paid for by the redundancy row.** Check designs for internal consistency.

## Explain-back
PM prompt: "Why not run checkout cheap and save $1,400/mo?" He answered: checkout has more risk and a wide blast radius affecting revenue and success; the internal tool is recoverable without significant business impact. Passed. Coaching: put the $1,400 against the cost of an outage hour, so a PM hears a number, not an opinion.

## Next step
Week 8 Day 4. The title isn't confirmed: the handoff doesn't list it, and he hasn't said yet. Ask him for the Day 4 name from his AWS 90-day checklist at the start of the next AWS session.
