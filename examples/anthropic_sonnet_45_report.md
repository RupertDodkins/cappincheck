# CappinCheck Report: Introducing Claude Sonnet 4.5 \ Anthropic

Source: `https://www.anthropic.com/news/claude-sonnet-4-5`

## Provenance

- Mode: `live_gemini`
- Runtime: `local`
- Pipeline wall: `149.26s`
- Load / Extract / Audit / Contrast: `1.67s` / `13.05s` / `134.54s` / `37.74s`
- Claims extracted / audited: `8` / `1`
- Specialist passes / unique sources: `3` / `7`

- Model: `gemini-3.5-flash`
- Evidence Contrast: `enabled`
- Provided reference URLs: `https://www.anthropic.com/claude-sonnet-4-5-system-card`, `https://www.anthropic.com/news/announcing-our-updated-responsible-scaling-policy`

## Scorecard

- Claims audited: `1`
- Verdict counts: `supported=0` · `overstated=1` · `missing_context=0` · `contradicted=0` · `not_checkable=0`
- Average stretch score: `80/100`
- Provided reference URL count: `2`

| Claim | Formal Verdict | Confidence | Stretch Score |
| --- | --- | --- | ---: |
| Claude Sonnet 4.5 is the best coding model in the world. | overstated | high | 80 |

## claim_01: overstated

**Confidence:** high

**Original:** Claude Sonnet 4.5 is the best coding model in the world.

**Stretch Score:** 80/100

**Why:** While the blog's introductory text claims that Claude Sonnet 4.5 is the best coding model in the world in an absolute sense, the actual technical documentation and the blog's own footnotes narrow this claim. They reveal that its record scores are benchmark-specific (e.g., SWE-bench Verified) and are highly contingent on specialized agentic scaffolding (including a 200K thinking budget, specific bash/file tools, and a minor prompt addendum) or advanced parallel test-time compute. Additionally, this representation is a snapshot of capabilities at its release in September 2025, as subsequent models (such as Claude Sonnet 4.6 and Claude Opus 4.6) have since surpassed its performance.

**Defensible rewrite:** At its release in September 2025, Claude Sonnet 4.5 achieved a state-of-the-art score of 77.2% on the SWE-bench Verified benchmark (82.0% with parallel test-time compute), outperforming contemporary competitors like GPT-5 and Gemini 2.5 Pro when utilizing structured agentic scaffolding.

**Claim timing:**
- Total / Verifier / Contradiction / Numeric / Aggregator / Contrast: 134.53s / 47.05s / 39.68s / 31.19s / 49.74s / 37.74s

### Agent Steps

<details><summary>Grounded Verifier: At the time of its release on September 29, 2025, Claude Sonnet 4.5 was the highest-performing model on major agentic coding and computer use benchmarks, outperforming then-competitors like GPT-5 (and its specialized variant GPT-5 Codex) and Gemini 2.5 Pro. It scored 77.2% on SWE-bench Verified (82.0% with parallel test-time compute) and 50.0% on Terminal-Bench. However, subsequent model updates released in late 2025 and 2026 (such as Claude Sonnet 4.6, Claude Opus 4.6/4.7, GPT-5.5, and Gemini 3.1 Pro) have since surpassed Sonnet 4.5's performance.</summary>

**Duration:** 47.05s

**Supporting evidence:**
- Claude Sonnet 4.5 is state-of-the-art on the SWE-bench Verified evaluation, which measures real-world software coding abilities... We report 77.2%, which was averaged over 10 trials, no test-time compute, and 200K thinking budget... For our 'high compute' numbers we adopt additional complexity and parallel test-time compute... This results in a score of 82.0% for Sonnet 4.5. ([Introducing Claude Sonnet 4.5 - Anthropic](https://www.anthropic.com/news/claude-sonnet-4-5)). Relevance: Directly establishes the self-reported scores for Claude Sonnet 4.5 on the premier software coding benchmark, SWE-bench Verified, both with and without parallel compute.
- Sonnet 4.5 leads Anthropic's own chart on SWE-bench Verified (n=500), posting 77.2% accuracy in standard runs and 82.0% with parallel test-time compute (the asterisked figure). That edges its prior state-of-the-art model Opus 4.1 (74.5% / 79.4%), Sonnet 4 (72.7% / 80.2%), and tops the single-run scores shown for OpenAI's specialized coding model GPT-5 Codex (74.5%), GPT-5 (72.8%) and Google's Gemini 2.5 Pro (67.2%). ([Claude Sonnet 4.5: Best coding model or just more marketing?](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHzsrgokvQDmTyG8y1esT5CkUQcKEmWtoj-7F4RUJmRHzB9cFlK85rGCrvAW7zkEK0uTvLBTiaDOen6q29xtOVxwUg8GsqRbS3AOTXvKPLNZ_LwSFY28zfSWmdQP8xqxP9q9jOYydJ5Ds8-mYL1QbPx65M2mNMgFMJa45hTd-XKZN79ntpCmOnsUPPp4_re5-CrF2BgXS5lRlvOGeFCfn4Sm1TtuZl_cRKybi1ajPzo)). Relevance: Compares Claude Sonnet 4.5's SWE-bench Verified performance directly with competing open and closed-source models (GPT-5 Codex, GPT-5, and Gemini 2.5 Pro) available at the time of launch.
- Terminal-Bench evaluates command-line interactions—navigating environments, executing commands... The Rankings: Claude Sonnet 4.5: 50.0% (leads the category); GPT-5: 43.8%; Claude Haiku 4.5: 41.0%; Claude Sonnet 4: 36.4%; Gemini 2.5 Pro: 25.3%. ([What is Claude Haiku 4.5? Full Overview, Specs & Benchmarks](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFZarZlfhdGE_oBR28ZMvX2ZCw4f9t0ORe2N2MYenYqa4ASR4Ich4YMRebyCAgzCuQnByHHlh7eFUxI2wxzSD21YRLVL2ZarOHcd7A1dYdH-cJn9xIEZSKcmeXw_3IxzzxPOuuAdurKcA==)). Relevance: Provides exact command-line tool-use rankings on Terminal-Bench, showing Sonnet 4.5 outperformed GPT-5 and Gemini 2.5 Pro upon release.

**Contradictions / narrowing evidence:**
- Model, SWE-bench Verified. Claude Opus 4.6, 80.8%. Claude Opus 4.5, 80.9%. Gemini 3.1 Pro, 80.6%. Claude Sonnet 4.6, 79.6%. Claude Sonnet 4.5, 77.2%. GPT-5.1, 76.3%. ([Best AI Model for Coding Agents in 2026: A Routing Guide](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE6QnfTAl_7BhOaqg4aInXLNaOnaqDRKLW_nTh2okILmHw5LK9tdmw7v_hNd6oO_dcBcNCTarCrRdojztZzcemZQKpOHMWf4uQOtlRXdnquDp0Swm7-hTGyx0-ttxOPtY9qmW0DrWPLAZhhpeZyxgs=)). Relevance: Shows that by early 2026, several newer models—including Google's Gemini 3.1 Pro and Anthropic's own updated Claude Sonnet 4.6, Opus 4.5, and Opus 4.6—all achieved higher scores on SWE-bench Verified than Claude Sonnet 4.5.
- GPT 5.5 leads with a performance of 82.60%, achieving the best accuracy on SWE-bench Verified. Claude Opus 4.7 follows closely at 82.00%... Claude Sonnet 4.5 (Thinking) scores 71.4%... ([SWE-bench Verified - Vals AI](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQGaChqwNt9z6Fus-ygeq3ykbgdd9FSrolAaZX1qU90EtjxkqFdwSqYwqJKZx9zPo4w4qiz68OCFzlEBCS0nIbXoYECzuF9fTB6gHnyJ-Qj2v6_CQFdWPKpjGyK_3iw=)). Relevance: Shows that newer generation models like GPT 5.5 and Claude Opus 4.7 score significantly higher than Claude Sonnet 4.5 on SWE-bench Verified, indicating that Sonnet 4.5's leadership was temporary.

**Missing context:**
- The absolute claim of being the 'best coding model in the world' was temporally bounded. While true in late September 2025, subsequent hardware, scaffolding, and model optimizations in early 2026 yielded superior performances from Google (Gemini 3.1 Pro), OpenAI (GPT 5.5), and Anthropic's own subsequent iterations (Sonnet 4.6, Opus 4.6, Opus 4.7).
- Third-party independent leaderboards (such as Vals AI) evaluated Claude Sonnet 4.5 with different setups, leading to lower absolute performance metrics (e.g., ~69.8% on SWE-bench Verified) compared to the self-reported 77.2%.

**Computed checks:**
- SWE-bench Verified (Standard): Claude Sonnet 4.5 achieved 77.2% vs. GPT-5 Codex (74.5%), GPT-5 (72.8%), and Gemini 2.5 Pro (67.2%).
- SWE-bench Verified (High Compute): Claude Sonnet 4.5 achieved 82.0% vs. Claude Sonnet 4 (80.2%) and Claude Opus 4.1 (79.4%).
- Terminal-Bench: Claude Sonnet 4.5 scored 50.0% vs. GPT-5 (43.8%) and Gemini 2.5 Pro (25.3%).
- OSWorld: Claude Sonnet 4.5 achieved 61.4% vs. Claude Sonnet 4 (42.2%).
- SWE-bench Verified (Subsequent 2026 Models): Claude Sonnet 4.5 (77.2%) was outpaced by Claude Sonnet 4.6 (79.6%), Gemini 3.1 Pro (80.6%), Claude Opus 4.6 (80.8%), Claude Opus 4.5 (80.9%), and GPT 5.5 (82.60%).

</details>

<details><summary>Contradiction Finder Skill: While Anthropic claims Claude Sonnet 4.5 is 'the best coding model in the world,' this is primarily justified by a 77.2% score on the SWE-bench Verified dataset. However, independent leaderboards show that under a standardized 'mini-SWE-agent' harness (which minimizes agent scaffold optimization), Claude Sonnet 4.5 scores 70.6%, which is comparable to or behind competing models. Furthermore, newer models (such as GPT-5.5 at 82.60%, Claude Opus 4.7 at 82.00%, and Gemini 3.5 Flash at 78.80%) have since surpassed these scores. Additionally, on more difficult benchmarks like SWE-Bench Pro, leading models experience a massive drop in performance (~23%), highlighting that SWE-bench Verified scores are highly inflated compared to production-level coding tasks.</summary>

**Duration:** 39.68s

**Supporting evidence:**
- Claude Sonnet 4.5 is the best coding model in the world... Claude Sonnet 4.5 is state-of-the-art on the SWE-bench Verified evaluation, which measures real-world software coding abilities... We report 77.2%, which was averaged over 10 trials, no test-time compute, and 200K thinking budget on the full 500-problem SWE-bench Verified dataset. ([Introducing Claude Sonnet 4.5 \\ Anthropic](https://www.anthropic.com/news/claude-sonnet-4-5)). Relevance: Provides the primary claim and self-reported state-of-the-art benchmark results on SWE-bench Verified.

**Contradictions / narrowing evidence:**
- 1. OpenAI. GPT 5.5. 82.60%± 1.70... 2. Anthropic. Claude Opus 4.7. 82.00%± 1.72... 3. Google. Gemini 3.5 Flash. 78.80%± 1.83... 5. OpenAI. GPT 5.4. 78.20%± 1.85... ([SWE-bench Verified - Vals AI](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQG_oFuJjTX4pMEv-sZmnOfRdCfi65zfvMZQkGxQ5YLWwAzgp5piSgvNoyqyem8AhfPcMrBDRAjk-FE3IQPDymRxMnVjDf_e4gWg5-SMXxxP-rkcTbM_YYRYDZo6g_c=)). Relevance: Shows that subsequent models like GPT 5.5, Claude Opus 4.7, Gemini 3.5 Flash, and GPT 5.4 have surpassed the performance scores initially cited for Claude Sonnet 4.5.
- Claude Sonnet 4.5, 70.6 ... Organization: Anthropic ... Agent: mini-SWE-agent ([SWE-bench + - OpenLM.ai](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE5inW-Yj2m7G09oS3a-HwKhM4112lAB5faSqUvqxcG5hHjjlDV1h4YFl4Ok2k2kYTeEw5iKeZkVLzH4nCNaYx5b8zrJRK0igC3KaS7r5tmPBRZ)). Relevance: Demonstrates that under a standardized agent harness, Claude Sonnet 4.5's performance falls to 70.6%, which is on par with GPT-5 (70.1%) and below other contemporary models, demonstrating that the claimed 77.2% score relied heavily on proprietary scaffolding.
- While most top models score over 70% on the verified version, the best-performing models, OpenAI GPT-5 and Claude Opus 4.1, score only 23.3% and 23.1% respectively on SWE-Bench Pro. This highlights the increased difficulty and realism of the new benchmark. ([SWE-Bench Pro Leaderboard AI Coding Benchmark (Public Dataset) - Scale Labs](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFJq7OO6zRtNHuK3Kls3srzeCfjXyIec717ffNmmdS04PYVOnK32S4--o8vfoBZ1tRxnFgFf_BqRNYS9dck4NDi7v-LkMb_JbNFgAgwVy_GFwRWnEcSify4uLG-3UjJzbhSS6396bw3IqD-0i5J)). Relevance: Exposes the inherent limitation of the SWE-bench Verified benchmark; even the highest-rated models fail significantly on harder, more realistic production-level codebases (SWE-bench Pro).

**Missing context:**
- Proprietary Scaffolding & Prompt Engineering: The model's 77.2% SWE-bench score was achieved using a custom prompt addendum instructing the model to use tools over 100 times and write its own tests first.
- Benchmark Optimization: In the τ2-bench evaluation, Anthropic utilized specialized prompt addendums tailored specifically to instruct Claude to avoid its 'known failure modes' on the benchmark, and added user-prompt modifications to prevent failure modes related to ending interactions incorrectly.
- Excluded Configurations: A 1M context configuration of Sonnet 4.5 originally achieved a higher score of 78.2% on SWE-bench Verified, but this configuration was omitted from primary reporting due to 'recent inference issues' at Anthropic.
- High-Compute Discrepancies: The 82.0% 'high compute' score cited by Anthropic relies on rejection sampling (filtering patches that break visible tests) and selecting candidates via an internal scoring model, rather than single-attempt generation.
- Agent Harness Dependency: Standardized independent leaderboards (like OpenLM.ai) show that model-only performance is highly dependent on the agentic scaffold; using a standard mini-SWE-agent harness drop's Sonnet 4.5's score from 77.2% to 70.6%.

**Computed checks:**
- 77.2%: Self-reported baseline score for Claude Sonnet 4.5 on SWE-bench Verified.
- 82.0%: Self-reported high-compute score for Claude Sonnet 4.5 on SWE-bench Verified.
- 70.6%: Independent benchmark score of Claude Sonnet 4.5 under a standardized 'mini-SWE-agent' harness.
- 82.60%: Score of the top-performing model (OpenAI GPT 5.5) on the SWE-bench Verified leaderboard as of mid-2026.
- 23.3%: Best-performing model score on the more challenging SWE-bench Pro benchmark.

</details>

<details><summary>Numeric Calibrator Skill: The claim that Claude Sonnet 4.5 is 'the best coding model in the world' is presented as an absolute benchmark ranking, but the text lacks the specific numerical scores of competing open and closed-source models (such as OpenAI's GPT-5 or Google's Gemini models) to back it up. Although the footnotes state that competitor scores were retrieved from external sources, none of those numbers are shown or compared directly within the document. In addition, several customer testimonies describe relative improvements (e.g., Devin's 18% planning and 12% evaluation gains; Hai's 44% intake time reduction and 25% accuracy increase) without specifying the absolute values or baseline denominators.</summary>

**Duration:** 31.19s

**Supporting evidence:**
- Claude Sonnet 4.5 is state-of-the-art on the SWE-bench Verified evaluation, which measures real-world software coding abilities. ([Introducing Claude Sonnet 4.5 \ Anthropic](https://www.anthropic.com/news/claude-sonnet-4-5)). Relevance: Directly supports the claim by stating the model achieved state-of-the-art results on a prominent software engineering benchmark.
- We report 77.2%, which was averaged over 10 trials, no test-time compute, and 200K thinking budget on the full 500-problem SWE-bench Verified dataset. A 1M context configuration achieves 78.2%... high compute... results in a score of 82.0% for Sonnet 4.5. ([Introducing Claude Sonnet 4.5 \ Anthropic](https://www.anthropic.com/news/claude-sonnet-4-5)). Relevance: Provides the explicit performance scores of Sonnet 4.5 across different testing configurations for the SWE-bench Verified coding benchmark.
- Claude Sonnet 4.5's edit capabilities are exceptional — we went from 9% error rate on Sonnet 4 to 0% on our internal code editing benchmark. ([Introducing Claude Sonnet 4.5 \ Anthropic](https://www.anthropic.com/news/claude-sonnet-4-5)). Relevance: Provides internal coding benchmark numbers comparing Sonnet 4.5 to Sonnet 4.

**Missing context:**
- The document lacks the specific benchmark scores of competing open and closed-source models (such as GPT-5 or Gemini models) on SWE-bench Verified and Terminal-Bench to substantiate the absolute claim of being the 'best in the world'.
- The document lacks the specific score achieved by Claude Sonnet 4.5 on Terminal-Bench.
- The document lacks the absolute baseline values and denominators for Devin's planning performance and end-to-end evaluation scores (only relative increases of 18% and 12% are listed).
- The document lacks the absolute baseline values and denominators for the Hai security agents' vulnerability intake time and accuracy (only relative changes of -44% and +25% are listed).

**Computed checks:**
- Internal code editing benchmark: error rate fell from 9% (Sonnet 4) to 0% (Sonnet 4.5). Absolute delta = -9 percentage points. Relative improvement = (9% - 0%) / 9% = 100% reduction in error rate.
- SWE-bench Verified (primary 200K config vs 1M context config): 77.2% vs 78.2%. Absolute delta = +1.0 percentage point. Relative improvement = (1.0 / 77.2) * 100% ≈ 1.30%.
- SWE-bench Verified (primary 200K config vs high compute config): 77.2% vs 82.0%. Absolute delta = +4.8 percentage points. Relative improvement = (4.8 / 77.2) * 100% ≈ 6.22%.
- OSWorld benchmark (computer use, related to coding agents): score increased from 42.2% (Sonnet 4) to 61.4% (Sonnet 4.5). Absolute delta = +19.2 percentage points. Relative improvement = (19.2 / 42.2) * 100% ≈ 45.50%.
- Devin planning performance: relative increase of 18%. Absolute delta and baseline denominator are missing.
- Devin end-to-end evaluation scores: relative increase of 12%. Absolute delta and baseline denominator are missing.
- Hai security agents average vulnerability intake time: relative decrease of 44%. Absolute delta and baseline denominator are missing.
- Hai security agents accuracy: relative increase of 25%. Absolute delta and baseline denominator are missing.

</details>

<details><summary>claim-aggregator: Combined specialist outputs into final verdict `overstated` with `high` confidence.</summary>

**Duration:** 49.74s

**Supporting evidence:**
- Claude Sonnet 4.5 is state-of-the-art on the SWE-bench Verified evaluation, which measures real-world software coding abilities... We report 77.2%, which was averaged over 10 trials, no test-time compute, and 200K thinking budget... For our 'high compute' numbers we adopt additional complexity and parallel test-time compute... This results in a score of 82.0% for Sonnet 4.5. ([Introducing Claude Sonnet 4.5 - Anthropic](https://www.anthropic.com/news/claude-sonnet-4-5)). Relevance: Directly establishes the self-reported scores for Claude Sonnet 4.5 on the premier software coding benchmark, SWE-bench Verified, both with and without parallel compute.
- Sonnet 4.5 leads Anthropic's own chart on SWE-bench Verified (n=500), posting 77.2% accuracy in standard runs and 82.0% with parallel test-time compute (the asterisked figure). That edges its prior state-of-the-art model Opus 4.1 (74.5% / 79.4%), Sonnet 4 (72.7% / 80.2%), and tops the single-run scores shown for OpenAI's specialized coding model GPT-5 Codex (74.5%), GPT-5 (72.8%) and Google's Gemini 2.5 Pro (67.2%). ([Claude Sonnet 4.5: Best coding model or just more marketing?](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHzsrgokvQDmTyG8y1esT5CkUQcKEmWtoj-7F4RUJmRHzB9cFlK85rGCrvAW7zkEK0uTvLBTiaDOen6q29xtOVxwUg8GsqRbS3AOTXvKPLNZ_LwSFY28zfSWmdQP8xqxP9q9jOYydJ5Ds8-mYL1QbPx65M2mNMgFMJa45hTd-XKZN79ntpCmOnsUPPp4_re5-CrF2BgXS5lRlvOGeFCfn4Sm1TtuZl_cRKybi1ajPzo)). Relevance: Compares Claude Sonnet 4.5's SWE-bench Verified performance directly with competing open and closed-source models (GPT-5 Codex, GPT-5, and Gemini 2.5 Pro) available at the time of launch.

**Contradictions / narrowing evidence:**
- Model, SWE-bench Verified. Claude Opus 4.6, 80.8%. Claude Opus 4.5, 80.9%. Gemini 3.1 Pro, 80.6%. Claude Sonnet 4.6, 79.6%. Claude Sonnet 4.5, 77.2%. GPT-5.1, 76.3%. ([Best AI Model for Coding Agents in 2026: A Routing Guide](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE6QnfTAl_7BhOaqg4aInXLNaOnaqDRKLW_nTh2okILmHw5LK9tdmw7v_hNd6oO_dcBcNCTarCrRdojztZzcemZQKpOHMWf4uQOtlRXdnquDp0Swm7-hTGyx0-ttxOPtY9qmW0DrWPLAZhhpeZyxgs=)). Relevance: Shows that by early 2026, several newer models—including Google's Gemini 3.1 Pro and Anthropic's own updated Claude Sonnet 4.6, Opus 4.5, and Opus 4.6—all achieved higher scores on SWE-bench Verified than Claude Sonnet 4.5.
- 1. OpenAI. GPT 5.5. 82.60% plus minus 1.70... 2. Anthropic. Claude Opus 4.7. 82.00% plus minus 1.72... 3. Google. Gemini 3.5 Flash. 78.80% plus minus 1.83... 5. OpenAI. GPT 5.4. 78.20% plus minus 1.85... ([SWE-bench Verified - Vals AI](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQG_oFuJjTX4pMEv-sZmnOfRdCfi65zfvMZQkGxQ5YLWwAzgp5piSgvNoyqyem8AhfPcMrBDRAjk-FE3IQPDymRxMnVjDf_e4gWg5-SMXxxP-rkcTbM_YYRYDZo6g_c=)). Relevance: Shows that subsequent models like GPT 5.5, Claude Opus 4.7, Gemini 3.5 Flash, and GPT 5.4 have surpassed the performance scores initially cited for Claude Sonnet 4.5.
- Claude Sonnet 4.5, 70.6 ... Organization: Anthropic ... Agent: mini-SWE-agent ([SWE-bench + - OpenLM.ai](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE5inW-Yj2m7G09oS3a-HwKhM4112lAB5faSqUvqxcG5hHjjlDV1h4YFl4Ok2k2kYTeEw5iKeZkVLzH4nCNaYx5b8zrJRK0igC3KaS7r5tmPBRZ)). Relevance: Demonstrates that under a standardized agent harness, Claude Sonnet 4.5's performance falls to 70.6%, which is on par with GPT-5 (70.1%) and below other contemporary models, demonstrating that the claimed 77.2% score relied heavily on proprietary scaffolding.

**Missing context:**
- The absolute claim of being the 'best coding model in the world' is temporally bounded; newer models released in 2026 like GPT 5.5, Gemini 3.1 Pro, and Claude Opus 4.7 have since achieved superior performance. [1, 2]
- The 77.2% score relied on proprietary scaffolding and custom prompt engineering; when evaluated on standardized harnesses (e.g., mini-SWE-agent), the performance of Sonnet 4.5 drops to 70.6%. [2]

**Computed checks:**
- SWE-bench Verified (Standard): Claude Sonnet 4.5 achieved 77.2% vs. GPT-5 Codex (74.5%), GPT-5 (72.8%), and Gemini 2.5 Pro (67.2%). [1]
- SWE-bench Verified (High Compute): Claude Sonnet 4.5 achieved 82.0% vs. Claude Sonnet 4 (80.2%) and Claude Opus 4.1 (79.4%). [1]
- Standardized Agent Harness: Claude Sonnet 4.5's score dropped to 70.6% on the mini-SWE-agent harness. [2]
- 2026 Competitors: Claude Sonnet 4.5 (77.2%) was outpaced by models like Gemini 3.1 Pro (80.6%), Claude Opus 4.6 (80.8%), and GPT 5.5 (82.60%). [1, 2]

</details>

### Evidence Contrast

**Claim says:** Claude Sonnet 4.5 is the best coding model in the world.

**Best reference says:** The main text states the model is the best coding model in the world based on leading SWE-bench Verified and OSWorld results [1.1.3]. However, the methodology footnotes qualify this by explaining that these scores (77.2% baseline and 82.0% high compute) were achieved using a simple scaffold with specific tools, a 200K thinking budget, a prompt addendum, and parallel test-time compute.

**Key qualification:** The footnote explains that the state-of-the-art performance relies on structured scaffolding, custom prompts, and parallel sampling configurations.

**Delta:** narrower_than_claim — While the blog's introductory text claims that Claude Sonnet 4.5 is the best coding model in the world in an absolute sense, the actual technical documentation and the blog's own footnotes narrow this claim. They reveal that its record scores are benchmark-specific (e.g., SWE-bench Verified) and are highly contingent on specialized agentic scaffolding (including a 200K thinking budget, specific bash/file tools, and a minor prompt addendum) or advanced parallel test-time compute. Additionally, this representation is a snapshot of capabilities at its release in September 2025, as subsequent models (such as Claude Sonnet 4.6 and Claude Opus 4.6) have since surpassed its performance.

**Final verdict:** overstated

**Defensible rewrite:** At its release in September 2025, Claude Sonnet 4.5 achieved a state-of-the-art score of 77.2% on the SWE-bench Verified benchmark (82.0% with parallel test-time compute), outperforming contemporary competitors like GPT-5 and Gemini 2.5 Pro when utilizing structured agentic scaffolding.

### Claim-Level Contrast References

- Introducing Claude Sonnet 4.5 (blog, authority 100/100): https://www.anthropic.com/news/claude-sonnet-4-5. This is the source document containing the exact promotional claim and initial context.
- Claude Sonnet 4.5 System Card (official_doc, authority 100/100): https://www.anthropic.com/claude-sonnet-4-5-system-card. Contains official technical documentation, evaluations, and qualifications regarding the model's actual coding capabilities and benchmark setups.
- Announcing our updated Responsible Scaling Policy (blog, authority 90/100): https://www.anthropic.com/news/announcing-our-updated-responsible-scaling-policy. Provides context on the responsible scaling framework and the safety levels (ASL-3) under which the model was deployed, though not directly measuring coding capability.

**Reference snippets / mismatches:**
- The main text states the model is the best coding model in the world based on leading SWE-bench Verified and OSWorld results [1.1.3]. However, the methodology footnotes qualify this by explaining that these scores (77.2% baseline and 82.0% high compute) were achieved using a simple scaffold with specific tools, a 200K thinking budget, a prompt addendum, and parallel test-time compute. (Introducing Claude Sonnet 4.5, narrows, https://www.anthropic.com/news/claude-sonnet-4-5). The footnote explains that the state-of-the-art performance relies on structured scaffolding, custom prompts, and parallel sampling configurations.
- The system card describes the model's 'particular strengths in software coding' and documents its capability improvements. Rather than asserting absolute global superiority, it reports controlled evaluations on benchmarks like SWE-bench Verified. (Claude Sonnet 4.5 System Card, narrows, https://www.anthropic.com/claude-sonnet-4-5-system-card). It frames capability gains in the context of specific evaluations, safety mitigations, and relative improvement over prior internal models.
- This document outlines Anthropic's general risk management framework, safety levels (ASLs), and commitments for mitigating catastrophic risks, without containing any details or evaluations of the model's coding performance. (Announcing our updated Responsible Scaling Policy, irrelevant, https://www.anthropic.com/news/announcing-our-updated-responsible-scaling-policy). It focuses strictly on safety commitments and governance policies, separate from technical benchmark achievements.

**Computed checks:**
- SWE-bench Verified (Standard): Claude Sonnet 4.5 achieved 77.2% vs. GPT-5 Codex (74.5%), GPT-5 (72.8%), and Gemini 2.5 Pro (67.2%). [1]
- SWE-bench Verified (High Compute): Claude Sonnet 4.5 achieved 82.0% vs. Claude Sonnet 4 (80.2%) and Claude Opus 4.1 (79.4%). [1]
- Standardized Agent Harness: Claude Sonnet 4.5's score dropped to 70.6% on the mini-SWE-agent harness. [2]
- 2026 Competitors: Claude Sonnet 4.5 (77.2%) was outpaced by models like Gemini 3.1 Pro (80.6%), Claude Opus 4.6 (80.8%), and GPT 5.5 (82.60%). [1, 2]

**Gemini-discovered supporting sources:**
- Claude Sonnet 4.5 is state-of-the-art on the SWE-bench Verified evaluation, which measures real-world software coding abilities... We report 77.2%, which was averaged over 10 trials, no test-time compute, and 200K thinking budget... For our 'high compute' numbers we adopt additional complexity and parallel test-time compute... This results in a score of 82.0% for Sonnet 4.5. ([Introducing Claude Sonnet 4.5 - Anthropic](https://www.anthropic.com/news/claude-sonnet-4-5)). Relevance: Directly establishes the self-reported scores for Claude Sonnet 4.5 on the premier software coding benchmark, SWE-bench Verified, both with and without parallel compute.
- Sonnet 4.5 leads Anthropic's own chart on SWE-bench Verified (n=500), posting 77.2% accuracy in standard runs and 82.0% with parallel test-time compute (the asterisked figure). That edges its prior state-of-the-art model Opus 4.1 (74.5% / 79.4%), Sonnet 4 (72.7% / 80.2%), and tops the single-run scores shown for OpenAI's specialized coding model GPT-5 Codex (74.5%), GPT-5 (72.8%) and Google's Gemini 2.5 Pro (67.2%). ([Claude Sonnet 4.5: Best coding model or just more marketing?](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHzsrgokvQDmTyG8y1esT5CkUQcKEmWtoj-7F4RUJmRHzB9cFlK85rGCrvAW7zkEK0uTvLBTiaDOen6q29xtOVxwUg8GsqRbS3AOTXvKPLNZ_LwSFY28zfSWmdQP8xqxP9q9jOYydJ5Ds8-mYL1QbPx65M2mNMgFMJa45hTd-XKZN79ntpCmOnsUPPp4_re5-CrF2BgXS5lRlvOGeFCfn4Sm1TtuZl_cRKybi1ajPzo)). Relevance: Compares Claude Sonnet 4.5's SWE-bench Verified performance directly with competing open and closed-source models (GPT-5 Codex, GPT-5, and Gemini 2.5 Pro) available at the time of launch.

**Gemini-discovered caveat / counter sources:**
- Model, SWE-bench Verified. Claude Opus 4.6, 80.8%. Claude Opus 4.5, 80.9%. Gemini 3.1 Pro, 80.6%. Claude Sonnet 4.6, 79.6%. Claude Sonnet 4.5, 77.2%. GPT-5.1, 76.3%. ([Best AI Model for Coding Agents in 2026: A Routing Guide](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE6QnfTAl_7BhOaqg4aInXLNaOnaqDRKLW_nTh2okILmHw5LK9tdmw7v_hNd6oO_dcBcNCTarCrRdojztZzcemZQKpOHMWf4uQOtlRXdnquDp0Swm7-hTGyx0-ttxOPtY9qmW0DrWPLAZhhpeZyxgs=)). Relevance: Shows that by early 2026, several newer models—including Google's Gemini 3.1 Pro and Anthropic's own updated Claude Sonnet 4.6, Opus 4.5, and Opus 4.6—all achieved higher scores on SWE-bench Verified than Claude Sonnet 4.5.
- 1. OpenAI. GPT 5.5. 82.60% plus minus 1.70... 2. Anthropic. Claude Opus 4.7. 82.00% plus minus 1.72... 3. Google. Gemini 3.5 Flash. 78.80% plus minus 1.83... 5. OpenAI. GPT 5.4. 78.20% plus minus 1.85... ([SWE-bench Verified - Vals AI](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQG_oFuJjTX4pMEv-sZmnOfRdCfi65zfvMZQkGxQ5YLWwAzgp5piSgvNoyqyem8AhfPcMrBDRAjk-FE3IQPDymRxMnVjDf_e4gWg5-SMXxxP-rkcTbM_YYRYDZo6g_c=)). Relevance: Shows that subsequent models like GPT 5.5, Claude Opus 4.7, Gemini 3.5 Flash, and GPT 5.4 have surpassed the performance scores initially cited for Claude Sonnet 4.5.
- Claude Sonnet 4.5, 70.6 ... Organization: Anthropic ... Agent: mini-SWE-agent ([SWE-bench + - OpenLM.ai](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE5inW-Yj2m7G09oS3a-HwKhM4112lAB5faSqUvqxcG5hHjjlDV1h4YFl4Ok2k2kYTeEw5iKeZkVLzH4nCNaYx5b8zrJRK0igC3KaS7r5tmPBRZ)). Relevance: Demonstrates that under a standardized agent harness, Claude Sonnet 4.5's performance falls to 70.6%, which is on par with GPT-5 (70.1%) and below other contemporary models, demonstrating that the claimed 77.2% score relied heavily on proprietary scaffolding.

**Missing context:**
- The absolute claim of being the 'best coding model in the world' is temporally bounded; newer models released in 2026 like GPT 5.5, Gemini 3.1 Pro, and Claude Opus 4.7 have since achieved superior performance. [1, 2]
- The 77.2% score relied on proprietary scaffolding and custom prompt engineering; when evaluated on standardized harnesses (e.g., mini-SWE-agent), the performance of Sonnet 4.5 drops to 70.6%. [2]

