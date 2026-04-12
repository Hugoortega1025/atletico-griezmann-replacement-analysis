# Atlético Madrid — Griezmann Replacement Analysis
### Football Recruitment Analytics | Cosine Similarity | Percentile Profiling 

---

## Executive Summary

Antoine Griezmann is leaving Atlético Madrid after a decade — confirmed heading to Orlando City at the end of the 2025/26 season. Beyond the emotional weight, his departure removes the connective tissue of Simeone's system; a player who was never a pure goalscorer or a pure creator, but operated across every dimension of the attack simultaneously. Finding a direct replacement is not straightforward.

Using cosine similarity modeling and percentile profiling across 2,854 players from Europe's top 5 leagues, this analysis identifies the players who most closely replicate Griezmann's statistical profile — and finds that the strongest answer may already be at the club.

**Data:** FBref player statistics (2024/25 & 2025/26) sourced via Kaggle across the Premier League, La Liga, Bundesliga, Serie A, and Ligue 1.

**Method:** Per90 normalization --> StandardScaler --> Cosine Similarity --> Cross-season overlap --> Percentile profiling --> Scatter analysis --> Composite & detailed radar comparison

**Key Finding:** No single player is a perfect like-for-like replacement. Griezmann's balanced profile across chance creation, goal threat, ball progression, and defensive contribution is rare. However, the analysis surfaces four candidates worth serious recruitment consideration.

**Final Recommendations:**
- **Alex Baena** — highest chance creation profile of any candidate (KP/90 at 99.8th percentile), already at Atlético, currently misused positionally. Give him the opportunity before spending in the market.
- **Lee Kang-in** — closest statistical match to Griezmann in the dataset, genuine transfer links already in place
- **Phil Foden** — highest goal threat of the final four, situation at City evolving — if the door opens, walk through it
- **Matías Soulé** — elite ball progression at 23, one to monitor

---

## Business Problem

Atlético Madrid operate a system that demands a very specific type of player to make it function. Griezmann's second phase at the club saw him evolve into a free-roaming number 10/8 — linking midfield to attack, creating chances at an elite level, pressing from the front, and giving Simeone's block its attacking structure. He was never replaceable on name alone, and he is not replaceable on profile alone either.

The departure triggers a recruitment question that goes beyond "who scores goals" — it demands identifying who can replicate the full statistical makeup of what Griezmann provided: creation, progression, goal involvement, and defensive workrate in a single profile.

The aim of this analysis is to use publicly available football data to build a data-driven shortlist that gives Atlético's recruitment department an evidence-based starting point for the 2026 summer window.

---

## Methodology

**Benchmark Construction** — Griezmann's 2025/26 season was initially used as the benchmark. The initial similarity model returned pure strikers (Sorloth, Sesko), exposing the issue: limited managed substitute appearances inflated his per90 numbers and distorted his true profile. His 2024/25 season (2,469 minutes) was adopted as the benchmark — a full starter season representative of his actual role in Simeone's system.

**Candidate Pool** — Filtered to forwards and midfielders across the top 5 leagues, minimum 900 minutes, age below 30. Per90 calculated across 20 metrics. After null removal: 768 players (24/25) and 737 players (25/26).

**Cosine Similarity** — Each player represented as a vector in multi-dimensional space, one dimension per per90 metric. StandardScaler normalizes all features to prevent high-magnitude metrics dominating. Cosine similarity measures the angle between each candidate's vector and Griezmann's — a score of 1.0 means identical profile shape, 0 means no similarity.

**Cross-Season Overlap** — Top 150 candidates from both seasons intersected. Players appearing in both lists show consistent statistical similarity across two seasons rather than a one-year spike. Average similarity score used for final ranking. **53 players** survived the overlap.

**Scatter Analysis** — In the absence of positional heatmap data, two scatter plots provide a proxy positional filter:
- Goal Threat vs Creativity (npxG/90 vs xAG/90) — identifies players in Griezmann's attacking profile zone
- Profile Similarity vs Output Level — surfaces players who are both similar in profile and operating at a high enough performance level to be a realistic replacement

**Shortlist Refinement** — Football context applied: transfer realism, positional fit, age profile. 53 overlap candidates --> 8 shortlisted --> **final 4 for deep analysis**

**Percentile Profiling & Radar Comparison** — All per90 metrics converted to percentile ranks relative to the 826-player FW/MF pool. Composite scores built across five footballing categories. Two radar formats produced per candidate — a 5-axis composite radar and a detailed 20-metric radar — overlaid against Griezmann's 2024/25 benchmark.

---

## Results & Recommendations

### Key Finding
No player sits cleanly in the high similarity and high output quadrant simultaneously — Griezmann's profile is genuinely rare. The scatter and similarity model confirm this across two seasons of data.

### Candidate Assessments

| Player | Age | Club | Similarity Avg | Standout Metric |
|---|---|---|---|---|
| Alex Baena | 24 | Atlético Madrid | 0.607 | KP/90 — 99.8th percentile |
| Lee Kang-in | 25 | Paris Saint-Germain | 0.695 | xAG/90 — 96.6th percentile |
| Phil Foden | 25 | Manchester City | 0.726 | Sh/90 — 88.5th percentile |
| Matías Soulé | 23 | Roma | 0.626 | PrgR/90 — 93.3rd percentile |

**Alex Baena — The Replacement is Already at Home**
The most statistically compelling finding of this analysis. Baena's chance creation profile is the highest of any candidate — KP/90 at 99.8th percentile, SCA/90 at 99th, xAG/90 at 99.2nd. His concern this season has been positional — deployed as a channel forward rather than the free-roaming creative role his data says he belongs in. His finishing trails Griezmann (SoT% 22.9 vs 58.5) but at 24, that is an improvable area. The recommendation is simple: before spending in the market, trust what is already in the team.

**Kang-in Lee — Primary External Target**
Statistically the closest profile match to Griezmann in the dataset. KP/90, PPA/90, SCA/90, and xAG/90 all rank in the top 1-3% of the candidate pool. Transfer links with Atlético already exist with sporting director Alemany reportedly involved in discussions. The defensive contribution gap is not a primary concern — Simeone's track record of integrating defensive discipline into attacking players makes this manageable. Age 25 gives the club a player who can grow into the role.

**Phil Foden — The Ambitious Hidden Gem**
Highest goal threat of the four finalists — Gls/90 at 82.9th percentile, npxG/90 at 77.1st, Sh/90 at 88.5th — combined with elite chance creation across KP/90, PPA/90, and SCA/90. His situation at Manchester City mirrors the conditions that made Julián Álvarez available. No transfer links exist at time of writing, but the data makes the case clearly: if the door opens, Atlético should walk through it — and don't be surprised when it does.

**Matías Soulé — One to Monitor**
Elite ball progression at 23 — PrgC/90 at 91.6th percentile, PrgR/90 at 93.3rd. However, with Baena already at the club carrying a similar finishing quality gap relative to Griezmann, the case for bringing in another player with the same limitation is difficult to make. Strong profile, high ceiling, priority behind the other three.

### Overall Recommendation
Rather than a single signing, this analysis points toward a layered approach:

1. **Give Baena the role** — already at the club, already elite in the creative dimensions that defined Griezmann
2. **Pursue Lee Kang-in** — strongest external candidate statistically and in terms of transfer realism
3. **Monitor Foden** — low probability, high reward. The data backs the ambition

---

## Tools & Libraries

`Python` · `pandas` · `numpy` · `scikit-learn` · `matplotlib` · `mplsoccer` · `scipy` · `Tableau`

---

## Next Steps & Limitations

**Limitations:**
- **No positional heatmap data** — spatial tracking data would significantly improve positional filtering. Players like Declan Rice surfaced due to statistical overlap despite playing a fundamentally different role. Scatter plots were used as a compensating proxy.
- **Unweighted composite scores** — each metric within a composite contributes equally. PCA-derived weights would better reflect the relative importance of individual metrics within each category.
- **2025/26 dataset column limitations** — missing key advanced metrics (npxG, progressive passes, SCA, PPA) constrained the cross-season comparison to a reduced feature set.
- **Benchmark season** — 2024/25 reflects an evolved, deeper-lying Griezmann. His 2022/23 and 2023/24 profiles (16 and 24 goals respectively) would produce a different benchmark vector and a different shortlist. This analysis identifies a replacement for what Atlético actually lost, not a historical peak.

**Next Steps:**
- Wyscout integration — video analysis of final candidates to validate statistical findings with qualitative scouting. 
- PCA-weighted composites — data-driven feature weights within each composite bucket
- Historical benchmark — rerun with Griezmann's 2023/24 profile as an alternative benchmark
