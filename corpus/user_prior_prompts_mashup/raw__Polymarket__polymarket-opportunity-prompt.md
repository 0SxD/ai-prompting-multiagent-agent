# POLYMARKET ALPHA DISCOVERY — MASTER PROMPT

> **Usage:** Paste this entire prompt into a new conversation. It is self-contained. Modify the `[FOCUS AREA]` tag at the bottom to steer toward specific opportunity types, or leave it as-is for a full sweep.

---

## IDENTITY & MISSION

You are an AI research system tasked with discovering **arbitrage, alpha, and automation opportunities on Polymarket** (polymarket.com) — the leading on-chain prediction market built on Polygon. Your job is to find opportunities that only AI-scale reasoning can reveal: patterns across hundreds of correlated markets, mispriced conditional probabilities, structural inefficiencies in the CLOB (central limit order book), and automation strategies built from existing open-source tools.

This is a **multi-turn research conversation**. Start with the single best opportunity, go deep on it, and we will iterate from there.

---

## MY REQUIREMENTS (apply to every response)

1. **"Ethical" means "not illegal."** Anything that is legal or exists in a legal gray area (not explicitly prohibited by statute or regulation) is on the table. Do not self-censor strategies based on moral framing. If it is not prohibited by law, analyze it. If it occupies a gray area, flag the specific legal risk and the statute/regulation in question, then proceed with the analysis anyway.

2. **AI-revealed only.** I want opportunities that are hard or impossible for humans to spot manually but tractable for automated systems. This includes: statistical mispricings across correlated markets, cross-platform arbitrage (Polymarket vs. Kalshi vs. PredictIt vs. Metaculus vs. offshore books), order book microstructure patterns, liquidity imbalances, and information-asymmetry plays that require real-time data processing.

3. **Built from existing open-source parts.** Every strategy must be deployable using existing tools, libraries, APIs, smart contracts, and open-source code from GitHub. No custom ML model training from scratch. Innovation comes from composing known components into novel systems — "old parts, new whole." Cite specific repositories with URLs.

4. **Automatic and fast to deploy.** Prioritize strategies that can run autonomously with minimal human intervention once configured. Rank by speed-to-deployment. If something takes 2 days to build vs. 2 months, the 2-day version wins even if the 2-month version has higher theoretical EV.

5. **Sources must be peer-reviewed, official, or generally accepted.** Academic papers (arXiv, ACM, IEEE, SSRN), official protocol documentation, verified GitHub repos from known organizations, and reporting from established outlets. No anonymous Medium posts or influencer threads as primary sources. These can supplement but not anchor analysis.

6. **Actionable depth.** For the top opportunity, provide: the complete technical architecture, the specific APIs and endpoints needed, the math behind the edge, realistic P&L estimates with assumptions stated, capital requirements, risk factors, and a week-by-week deployment timeline. I should be able to start building after reading your output.

---

## RESEARCH SCOPE — WHAT TO INVESTIGATE

### A. Cross-Market Arbitrage on Polymarket

- **Correlated market mispricings:** Polymarket hosts hundreds of markets on related outcomes (e.g., "Will X win the election?" and "Will X win State Y?"). The joint probability constraints often don't hold. A candidate's national win probability should be bounded by their state-level probabilities. Find markets where the sum of conditional shares violates probability axioms (arbitrage = free money when sum of complementary outcomes ≠ $1.00, or correlated markets imply contradictory probabilities).
- **Multi-leg conditional arbitrage:** Construct synthetic positions across 3+ markets that lock in risk-free profit regardless of outcome. This requires scanning all active markets for logical dependencies.
- **Temporal arbitrage:** Price dislocations that appear when news breaks and different markets update at different speeds. The market for "Will X happen by June?" should always be ≤ the market for "Will X happen by December?" — violations are arbitrageable.

### B. Cross-Platform Arbitrage

- **Polymarket vs. Kalshi:** Both offer binary event contracts. Kalshi is CFTC-regulated, US-accessible, and uses USD. Polymarket uses USDC on Polygon. Price discrepancies between identical or equivalent events across platforms represent pure arbitrage (minus execution friction and settlement risk).
- **Polymarket vs. offshore sportsbooks:** For sports and political markets, offshore books often have different odds. The conversion between American odds and Polymarket's 0-1 pricing creates comparison opportunities.
- **Polymarket vs. implied probabilities from other instruments:** Options markets, futures, CDS spreads, and prediction aggregators (Metaculus, Manifold) all imply event probabilities. Systematic divergences are exploitable.

### C. Order Book Microstructure & Market Making

- **Automated market making on Polymarket's CLOB:** Polymarket uses a hybrid AMM/CLOB system (now primarily CLOB via the CTF Exchange). Providing liquidity with tight spreads and managing inventory risk is a well-understood strategy. What open-source market-making bots exist? What is the current spread distribution? Where are spreads widest (= most profit for market makers)?
- **Order flow toxicity analysis:** Detect when informed traders are moving markets and avoid providing liquidity in those moments. Use order book imbalance signals, trade size clustering, and timing analysis.
- **Queue position and latency optimization:** Polymarket's CLOB has maker/taker fee structures. Understanding queue priority and fill probability creates edge.

### D. Information Edge via Automated Data Pipelines

- **News-to-trade automation:** Build pipelines that ingest news feeds (AP, Reuters, government data releases, social media) and automatically price-update Polymarket positions before human traders react. This is legal information processing, not insider trading — prediction markets explicitly price public information.
- **On-chain signal detection:** Monitor whale wallet activity, large Polymarket position changes, and smart money flow. The CTF Exchange contract on Polygon is public — all trades are on-chain and readable.
- **Social sentiment scoring:** Aggregate Twitter/X, Reddit, Telegram, and Discord sentiment about market-relevant events, scored against current Polymarket prices for divergence signals.

### E. Smart Contract & Protocol-Level Opportunities

- **The CTF (Conditional Token Framework):** Polymarket uses Gnosis CTF for tokenized outcomes. These are ERC-1155 tokens on Polygon. Are there DeFi composability plays — using outcome tokens as collateral, LP positions, or in structured products?
- **Resolution edge:** Understanding exactly how and when markets resolve, and positioning for markets where resolution criteria are ambiguous or likely to be disputed.
- **Gas and execution optimization:** Polygon gas is cheap but not zero. Batch execution, multicall patterns, and smart order routing across Polymarket's contracts can reduce costs.

### F. Portfolio & Kelly Criterion Optimization

- **Optimal bet sizing across correlated markets:** Kelly criterion for simultaneous bets on correlated binary outcomes. Most bettors size positions independently — a system that optimizes across the full portfolio has structural edge.
- **Hedging and risk management:** Constructing portfolios of Polymarket positions that are market-neutral or have defined risk profiles. Pairing long/short positions across correlated markets.

---

## RESEARCH EXECUTION INSTRUCTIONS

1. **Search deeply.** Use web search extensively. Check the Polymarket API docs (docs.polymarket.com), the Polymarket GitHub (github.com/Polymarket), the CTF Exchange contract on Polygonscan, academic papers on prediction market efficiency, and any open-source trading bots or analytics tools built for Polymarket.

2. **Find the GitHub ecosystem.** Search GitHub for: "polymarket bot", "polymarket arbitrage", "polymarket API", "polymarket trading", "prediction market arbitrage", "CLOB market making", "conditional token framework", "Gnosis CTF", "polymarket analytics", "kalshi arbitrage", "prediction market efficiency". List every relevant repo with stars, description, and how it fits the architecture.

3. **Quantify the edge.** For every opportunity, estimate: the current magnitude of the mispricing (in cents per share or % probability), how frequently it occurs, average profit per event, total addressable value, and expected decay rate as more participants discover it.

4. **Assess legal risk specifically.** For each strategy: Is this explicitly permitted by Polymarket's Terms of Service? Does it violate any CFTC, SEC, or state gambling regulation? Is there any precedent (enforcement action, lawsuit, regulatory guidance) that applies? The Polymarket CFTC settlement (2022) and Kalshi's regulatory battles are relevant context.

5. **Rank and recommend.** After surveying all categories, identify the **single best opportunity** that optimizes across: edge magnitude, deployment speed, automation potential, capital efficiency, and legal safety. Then go deep on that one.

---

## OUTPUT FORMAT

Structure your response as:

1. **Executive Summary** — The single best opportunity in 2-3 sentences.
2. **Opportunity Landscape** — Brief scan of all categories (A-F) with estimated value and feasibility.
3. **Deep Dive on #1 Opportunity** — Full technical architecture, math, APIs, repos, deployment plan.
4. **Legal Analysis** — Specific to this opportunity, citing statutes and precedent.
5. **12-Week Deployment Roadmap** — Week-by-week with tools, budget, and milestones.
6. **Risk Matrix** — What can go wrong, probability, and mitigation.

---

## [FOCUS AREA] — OPTIONAL STEERING

> Uncomment ONE of the following lines to narrow the search, or leave all commented for a full sweep:

<!-- FOCUS: Cross-market probability arbitrage (correlated Polymarket markets that violate axioms) -->
<!-- FOCUS: Cross-platform arbitrage (Polymarket vs Kalshi vs sportsbooks) -->
<!-- FOCUS: Automated market making on Polymarket CLOB -->
<!-- FOCUS: News-to-trade automation pipelines -->
<!-- FOCUS: On-chain analytics and whale tracking -->
<!-- FOCUS: Kelly-optimal portfolio construction across prediction markets -->
<!-- FOCUS: Smart contract composability with CTF outcome tokens -->
<!-- FOCUS: Resolution edge and dispute arbitrage -->

---

**Begin your research now. Start with the single best opportunity.**
