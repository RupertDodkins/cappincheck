# HonestLaunch Report: Introducing Claude Opus 4.8 \ Anthropic

Source: `https://www.anthropic.com/news/claude-opus-4-8`

## Provenance

- Mode: `live_gemini`
- Model: `gemini-3.5-flash`
- Pipeline wall: `1030.07s`
- Load / Extract / Audit / Contrast: `0ms` / `0ms` / `0ms` / `0ms`
- Claims extracted / audited: `5` / `5`
- Specialist passes / unique sources: `15` / `12`

- Evidence Contrast: `disabled`
- Provided reference URLs: `https://www.anthropic.com/claude-opus-4-8-system-card`, `https://platform.claude.com/docs/en/about-claude/models/overview`, `https://claude.com/pricing#api`, `https://www.anthropic.com/news/announcing-our-updated-responsible-scaling-policy`

## Scorecard

- Claims audited: `5`
- Verdict counts: `supported=1` · `overstated=1` · `missing_context=3` · `contradicted=0` · `not_checkable=0`
- Average stretch score: `33/100`
- Provided reference URL count: `4`

| Claim | Formal Verdict | Confidence | Stretch Score |
| --- | --- | --- | ---: |
| fast mode for Opus 4.8—where the model can work at 2.5× the speed—is now three times cheaper than it was for previous models. | missing_context | high | 25 |
| On our Super-Agent benchmark, Claude Opus 4.8 is the only model to complete every case end-to-end, beating prior Opus models and GPT-5.5 at parity on cost. | missing_context | high | 45 |
| This is borne out in our evaluations, which show that Opus 4.8 is around four times less likely than its predecessor to allow flaws in code it has written to pass unremarked. | supported | high | 15 |
| Claude Opus 4.8 is the strongest computer-use and browser-agent model we’ve tested, scoring 84% on Online-Mind2Web, which is a meaningful jump over both Opus 4.7 and GPT-5.5. | missing_context | high | 35 |
| Claude Code with Opus 4.8 can now carry out codebase-scale migrations across hundreds of thousands of lines of code from kickoff to merge, with the existing test suite as its bar. | overstated | high | 45 |

## claim_1: missing_context

**Confidence:** high

**Original:** fast mode for Opus 4.8—where the model can work at 2.5× the speed—is now three times cheaper than it was for previous models.

**Stretch Score:** 25/100

**Why:** The 3x cost reduction is mathematically accurate based on previous fast mode prices ($30/$150 per million tokens) compared to the new pricing ($10/$50 per million tokens) [2, 3]. However, the speedup is officially qualified as 'up to 2.5x' and applies strictly to output tokens per second (OTPS), leaving time to first token (TTFT) unchanged [3]. Furthermore, access to fast mode is highly restricted: it is in a gated research preview on the native Claude API, unavailable on third-party cloud platforms (Vertex AI, Bedrock), and excluded from standard Claude Code subscriptions.

**Defensible rewrite:** fast mode for Opus 4.8—which can deliver up to 2.5× higher output tokens per second—is three times cheaper on the native Claude API than it was for previous models.

**Claim timing:**
- Total / Verifier / Contradiction / Numeric / Aggregator / Contrast: 314.91s / 15.87s / 27.70s / 41.81s / 223.49s / 0ms

### Agent Steps

<details><summary>grounded_verifier: The claim that fast mode for Claude Opus 4.8 is roughly 2.5x faster and three times cheaper than previous models is fully supported by official documentation and industry reporting. Pricing for Opus 4.8 fast mode is $10 per million input tokens and $50 per million output tokens, representing a 3x reduction from the $30 per million input and $150 per million output fast-mode pricing of prior models (Opus 4.7 and Opus 4.6). Official documentation confirms the model delivers up to 2.5x higher output speed in this mode.</summary>

**Duration:** 15.87s

**Supporting evidence:**
- And fast mode for Opus 4.8—where the model can work at 2.5× the speed—is now three times cheaper than it was for previous models. ... Pricing for regular usage is unchanged from Opus 4.7: $5 per million input tokens and $25 per million output tokens. Pricing for fast mode is $10 per million input tokens and $50 per million output tokens. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Direct primary source documentation explaining the 2.5x speed improvement, the 3x cost reduction, and providing the exact fast mode price points ($10/$50 per million tokens).
- Anthropic has slashed the price of running Opus 4.8 in fast mode — where the model produces tokens at roughly 2.5x normal speed — to $10 per million input tokens and $50 per million output tokens, down from $30/$150 for Opus 4.7. ([Anthropic's Claude Opus 4.8 is here with 3X cheaper fast mode and near-Mythos level alignment | VentureBeat](https://venturebeat.com/ai/anthropics-claude-opus-4-8-is-here-with-3x-cheaper-fast-mode-and-near-mythos-level-alignment/)). Relevance: Provides the explicit previous model fast-mode pricing ($30/$150) and current pricing ($10/$50), mathematically confirming the exact 3x price reduction.
- Claude Opus 4.8, Claude Opus 4.7, and Claude Opus 4.6 support fast mode (research preview), which delivers up to 2.5x higher output speed at premium pricing. ([Choosing the right model - Claude API Docs](https://docs.anthropic.com/en/docs/about-claude/models)). Relevance: Confirms the official speed metric of up to 2.5x higher output speed under the fast mode across supporting models.
- The new fast mode is $30/million input and $150/million output! ... Our teams have been building with a 2.5x-faster version of Claude Opus 4.6. ([Claude: Speed up responses with fast mode - Simon Willison's Weblog](https://simonwillison.net/2026/Feb/7/fast-mode/)). Relevance: Historical primary verification of the original fast mode pricing ($30/$150) and the 2.5x speed factor during its early rollout.

**Computed checks:**
- Opus 4.8 Fast Mode input price: $10 per million tokens.
- Opus 4.8 Fast Mode output price: $50 per million tokens.
- Previous models (Opus 4.7/4.6) Fast Mode input price: $30 per million tokens.
- Previous models (Opus 4.7/4.6) Fast Mode output price: $150 per million tokens.
- Fast mode speed increase: 2.5x (or up to 2.5x) standard output speed.
- Cost reduction ratio: exactly 3x ($30 / $10 = 3 for input, $150 / $50 = 3 for output).

</details>

<details><summary>Contradiction Finder: While the 3x cost reduction is mathematically accurate compared to the prior fast mode pricing for Opus 4.7 and 4.6 ($10/$50 MTok down from $30/$150 MTok), the claim that the model 'can work at 2.5x the speed' contains significant qualifiers and omissions. According to official documentation, the speedup is 'up to 2.5x' and is strictly limited to 'output tokens per second (OTPS),' with no improvement in 'time to first token (TTFT).' Additionally, fast mode is currently restricted to a gated research preview on the native Claude API (requiring waitlist approval or account manager setup) and is completely unavailable on third-party platforms like Amazon Bedrock, Vertex AI, and Microsoft Foundry. Furthermore, subscription plans on Claude Code do not cover fast mode under standard rate limits, requiring users to pay extra via usage credits.</summary>

**Duration:** 27.70s

**Supporting evidence:**
- Anthropic has slashed the price of running Opus 4.8 in fast mode — where the model produces tokens at roughly 2.5x normal speed — to $10 per million input tokens and $50 per million output tokens, down from $30/$150 for Opus 4.7. ... That's a 3X reduction from the fast-mode pricing of previous models ([Anthropic's Claude Opus 4.8 is here with 3X cheaper fast mode and near-Mythos level alignment | VentureBeat](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFnDBGto6PSL2FWnDuG9bBoAhNfh9vY4SM3ZcRzDFvHmRepsPbkAi7YMwefDYHIRQB_0n-kJU5QUxCIIvgRMyBGSPm73DL5CGKnCnYRtZeBdilXATKOe5AyTDlRhcRSgi_aog6EhtIYDtZlgcLlcpQquC9ybrdLl2GhixZ2Na6J9EjRAaSkGSZXWIPIbrHtNs8BDSd-UN5TEUh1BDzowh2jK9HOyXPGMBnBT001BEZNcPV_VDNp)). Relevance: Confirms the mathematical accuracy of the 3x price reduction claim, showcasing that previous models' fast mode cost $30 per million input tokens and $150 per million output tokens, which has dropped to $10/$50.

**Contradictions / narrowing evidence:**
- Fast mode delivers up to 2.5x higher output tokens per second from the same model. ... Speed benefits are focused on output tokens per second (OTPS), not time to first token (TTFT) ([Fast mode (research preview) - Claude API Docs](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHElzDuchVi3yX6HgCmlplm6e2O8YfsB_Q5VXlQBShcPYFTgIEoQNaME0eQ6ri6NPx_npLYV9MQ6J8LokpR_e1QnslNVnxU0AgSOf8J1rRmHspSpfcx9qZhlSoGeiNC_9dJS13t98A7VR4b5_IfvBMMbxcP_Us=)). Relevance: Directly qualifies and counters the claim of a flat '2.5x speed' increase, showing it is an 'up to 2.5x' improvement focused strictly on output tokens, while leaving time to first token (TTFT) unchanged.

**Missing context:**
- Gated Access: Fast mode is in a limited 'research preview' on the Claude API, meaning developers must request access through an account manager or join a waitlist.
- Platform Exclusions: Fast mode is not supported on third-party cloud hosting providers, including Vertex AI (Google Cloud), Amazon Bedrock, and Microsoft Foundry.
- Subscription Exclusions: For Claude Code subscribers on Pro, Max, Team, or Enterprise plans, fast mode usage is not included in subscription rate limits and requires purchasing extra usage credits.
- Model Deprecation: Fast mode for Claude Opus 4.6 is being deprecated and will be removed roughly 30 days post-launch, forcing transitions to maintain higher speeds.

**Computed checks:**
- Fast mode pricing is set at $10 per million input tokens and $50 per million output tokens, compared to $30/$150 on prior models (Opus 4.7 and 4.6).
- The maximum speedup is capped at 'up to 2.5x output tokens per second' (OTPS).

</details>

<details><summary>numeric_calibrator: The claim states that Claude Opus 4.8's fast mode is three times cheaper and operates at 2.5x the speed compared to prior models. While external sources confirm that fast mode pricing was indeed reduced by exactly 3x (down from $30/$150 per million tokens for Opus 4.7 to $10/$50 for Opus 4.8), the provided document lacks the prior pricing numbers needed to verify this calculation. Additionally, the speedup is officially specified as 'up to 2.5x' in API documentation and applies specifically to output tokens per second, rather than representing a consistent 2.5x speed increase across all workloads and metrics (such as time to first token).</summary>

**Duration:** 41.81s

**Supporting evidence:**
- And fast mode for Opus 4.8—where the model can work at 2.5× the speed—is now three times cheaper than it was for previous models. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Presents the original claim regarding the 2.5x speed increase and 3x cost reduction.
- Pricing for fast mode is $10 per million input tokens and $50 per million output tokens. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Provides the new pricing of the fast mode for Claude Opus 4.8, which is necessary to calculate the reduction relative to previous models.
- Anthropic has slashed the price of running Opus 4.8 in fast mode — where the model produces tokens at roughly 2.5x normal speed — to $10 per million input tokens and $50 per million output tokens, down from $30/$150 for Opus 4.7. ([Anthropic's Claude Opus 4.8 is here with 3X cheaper fast mode and near-Mythos level alignment | VentureBeat](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFeIicln7esuhcPjBZjWphnS7ALa8LPOXRKApULQVzAFhVdkkT0ge4lNK89urlKIx20Vg3SjUawltusBmbzP7klqp6dDD3oQusvWmpMg2ZxOqhQYpjbnke-bdIFaP9HUuIgYhsbmn8w-8ZV-c5OaROG0I1K9dXkAjgNdAVwp0NWrqYQY1f_sK-AnBsLF6vsnF2TyGjVtCHgu4go0KnImmcn7pVhjKjxiWWtRkMt1kdZR-1xLVM1)). Relevance: Provides the missing pricing details for previous models (Opus 4.7 fast mode was $30 per million input tokens and $150 per million output tokens) to calculate and verify the 3x reduction.

**Contradictions / narrowing evidence:**
- Up to 2.5x higher output tokens per second compared to standard speed; Speed benefits are focused on output tokens per second (OTPS), not time to first token (TTFT) ([Fast mode (research preview) - Claude API Docs](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQEZx2Zmk7ApnB-UVAUxK7p_1EAVoOb7IWb0C6xm71ZBl-q-q0vamy18WQb4c6IA42mm9HgtX6T9PNy115FUZpuEgWAqsf5EceVuGnNSav9mi49xaJcW08xwHujmhS6Zxdn2FQOinRFzfh7vlOpJMQJFoWeC89g=)). Relevance: Qualifies the '2.5x speed' claim, revealing it is an 'up to' maximum and does not apply consistently to all metrics like time to first token.

**Missing context:**
- The fast mode pricing of previous models (such as Claude Opus 4.7) is missing from the provided document, which is required to calculate and verify the 'three times cheaper' claim.
- Standardized benchmark speed measurements or statistics to verify if the model consistently runs at 2.5x the speed across different standard evaluation conditions.

**Computed checks:**
- New fast mode pricing (Opus 4.8): $10 per million input tokens, $50 per million output tokens.
- Previous fast mode pricing (Opus 4.7): $30 per million input tokens, $150 per million output tokens.
- Input tokens price reduction arithmetic: $30 / $10 = 3.0 (exactly 3 times cheaper).
- Output tokens price reduction arithmetic: $150 / $50 = 3.0 (exactly 3 times cheaper).
- The price reduction is mathematically verified to be exactly 3x, though the calculation requires external baseline pricing because the original document lacks previous fast mode prices.
- Speed increase factor claimed: 2.5x speed. External developer documentation reveals this is 'up to 2.5x' higher output tokens per second (OTPS) and does not benefit time to first token (TTFT), indicating the speedup is not uniform or consistent across all operations.

</details>

<details><summary>claim-aggregator: Combined specialist outputs into final verdict `missing_context` with `high` confidence.</summary>

**Duration:** 223.49s

**Supporting evidence:**
- And fast mode for Opus 4.8—where the model can work at 2.5× the speed—is now three times cheaper than it was for previous models. ... Pricing for regular usage is unchanged from Opus 4.7: $5 per million input tokens and $25 per million output tokens. Pricing for fast mode is $10 per million input tokens and $50 per million output tokens. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Primary announcement confirming the pricing for Opus 4.8 fast mode ($10/$50) and the claimed speedup.
- Anthropic has slashed the price of running Opus 4.8 in fast mode — where the model produces tokens at roughly 2.5x normal speed — to $10 per million input tokens and $50 per million output tokens, down from $30/$150 for Opus 4.7. ([Anthropic's Claude Opus 4.8 is here with 3X cheaper fast mode and near-Mythos level alignment | VentureBeat](https://venturebeat.com/ai/anthropics-claude-opus-4-8-is-here-with-3x-cheaper-fast-mode-and-near-mythos-level-alignment/)). Relevance: Independent reporting confirming prior fast mode pricing ($30/$150) to verify the 3x cost reduction.

**Contradictions / narrowing evidence:**
- Fast mode delivers up to 2.5x higher output tokens per second from the same model. ... Speed benefits are focused on output tokens per second (OTPS), not time to first token (TTFT) ([Fast mode (research preview) - Claude API Docs](https://docs.anthropic.com/en/docs/about-claude/models)). Relevance: API documentation qualifying the speedup as 'up to 2.5x' and clarifying it only applies to output tokens per second.

**Missing context:**
- The speed increase is 'up to 2.5x' and applies only to output tokens per second (OTPS), with no change to time to first token (TTFT).
- Fast mode is in a limited research preview requiring waitlist approval or direct account manager access.
- Fast mode is unavailable on third-party providers like Google Cloud Vertex AI or Amazon Bedrock.
- Fast mode is excluded from standard Claude Code subscription plans and requires usage credits.

**Computed checks:**
- New fast-mode pricing: $10/M input, $50/M output tokens.
- Previous fast-mode pricing: $30/M input, $150/M output tokens.
- Mathematical cost reduction: exactly 3x.
- Maximum speed increase: up to 2.5x output tokens per second.

</details>

### Evidence Contrast

**Claim says:** fast mode for Opus 4.8—where the model can work at 2.5× the speed—is now three times cheaper than it was for previous models.

**Best reference says:** API documentation indicates that fast mode offers 'up to 2.5x' higher output tokens per second (OTPS), focusing benefits on output generation rather than time to first token (TTFT). Furthermore, it notes that the feature is in a gated research preview.

**Key qualification:** Speed benefits only apply to OTPS, not TTFT, and access is gated.

**Delta:** missing_context — While the 3x pricing reduction is mathematically supported relative to previous fast-mode rates ($30/$150 reduced to $10/$50), the claim omits important scope limits: the 2.5x speed benefit is an upper bound ('up to 2.5x') restricted specifically to output tokens per second, with no impact on time to first token (TTFT). Additionally, the feature is limited to a gated research preview on the native Claude API and is unavailable on third-party cloud platforms.

**Final verdict:** missing_context

**Defensible rewrite:** fast mode for Opus 4.8—which can deliver up to 2.5× higher output tokens per second—is three times cheaper on the native Claude API than previous models' fast mode.

### Claim-Level Contrast References

- Introducing Claude Opus 4.8 - Anthropic (official_doc, authority 100/100): https://www.anthropic.com/news/claude-opus-4-8. Official announcement introducing Claude Opus 4.8 and detailing fast mode pricing and speed capabilities.

**Reference snippets / mismatches:**
- API documentation indicates that fast mode offers 'up to 2.5x' higher output tokens per second (OTPS), focusing benefits on output generation rather than time to first token (TTFT). Furthermore, it notes that the feature is in a gated research preview. (Fast mode (research preview) - Claude API Docs, narrows, https://docs.anthropic.com/en/docs/about-claude/models). Speed benefits only apply to OTPS, not TTFT, and access is gated.

**Computed checks:**
- New fast-mode pricing: $10/M input, $50/M output tokens.
- Previous fast-mode pricing: $30/M input, $150/M output tokens.
- Mathematical cost reduction: exactly 3x.
- Maximum speed increase: up to 2.5x output tokens per second.

**Gemini-discovered supporting sources:**
- And fast mode for Opus 4.8—where the model can work at 2.5× the speed—is now three times cheaper than it was for previous models. ... Pricing for regular usage is unchanged from Opus 4.7: $5 per million input tokens and $25 per million output tokens. Pricing for fast mode is $10 per million input tokens and $50 per million output tokens. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Primary announcement confirming the pricing for Opus 4.8 fast mode ($10/$50) and the claimed speedup.
- Anthropic has slashed the price of running Opus 4.8 in fast mode — where the model produces tokens at roughly 2.5x normal speed — to $10 per million input tokens and $50 per million output tokens, down from $30/$150 for Opus 4.7. ([Anthropic's Claude Opus 4.8 is here with 3X cheaper fast mode and near-Mythos level alignment | VentureBeat](https://venturebeat.com/ai/anthropics-claude-opus-4-8-is-here-with-3x-cheaper-fast-mode-and-near-mythos-level-alignment/)). Relevance: Independent reporting confirming prior fast mode pricing ($30/$150) to verify the 3x cost reduction.

**Gemini-discovered caveat / counter sources:**
- Fast mode delivers up to 2.5x higher output tokens per second from the same model. ... Speed benefits are focused on output tokens per second (OTPS), not time to first token (TTFT) ([Fast mode (research preview) - Claude API Docs](https://docs.anthropic.com/en/docs/about-claude/models)). Relevance: API documentation qualifying the speedup as 'up to 2.5x' and clarifying it only applies to output tokens per second.

**Missing context:**
- The speed increase is 'up to 2.5x' and applies only to output tokens per second (OTPS), with no change to time to first token (TTFT).
- Fast mode is in a limited research preview requiring waitlist approval or direct account manager access.
- Fast mode is unavailable on third-party providers like Google Cloud Vertex AI or Amazon Bedrock.
- Fast mode is excluded from standard Claude Code subscription plans and requires usage credits.


## claim_2: missing_context

**Confidence:** high

**Original:** On our Super-Agent benchmark, Claude Opus 4.8 is the only model to complete every case end-to-end, beating prior Opus models and GPT-5.5 at parity on cost.

**Stretch Score:** 45/100

**Why:** The claim is presented as a benchmark milestone in Anthropic's announcement, but it is based on a testimonial quote by Kay Zhu (Co-Founder and CTO of Genspark) referencing 'our Super-Agent benchmark'. This benchmark is proprietary, internal to Genspark, and completely non-public. There are no published datasets, methodologies, or peer-reviewed papers to verify the 100% completion rate or the exact cost-parity conditions compared to GPT-5.5.

**Defensible rewrite:** According to partner feedback from Genspark using their proprietary, non-public 'Super-Agent' benchmark, Claude Opus 4.8 completed every test case end-to-end, reportedly outperforming prior Opus models and GPT-5.5 under Genspark's internal cost-parity metrics.

**Claim timing:**
- Total / Verifier / Contradiction / Numeric / Aggregator / Contrast: 127.07s / 23.70s / 37.24s / 30.77s / 29.34s / 0ms

### Agent Steps

<details><summary>Grounded Verifier: The claim is based on an official quote by Kay Zhu (Co-Founder and CTO of Genspark) in Anthropic's launch announcement for Claude Opus 4.8. However, the Super-Agent benchmark is a proprietary, internal benchmark developed by Genspark rather than a public, standardized test. Consequently, while the assertion of a 100% end-to-end completion rate ('complete every case') and outperforming GPT-5.5 at cost parity is supported by the partner's testimonial, it is not publicly verifiable or reproducible because the benchmark dataset and evaluation methodology are private.</summary>

**Duration:** 23.70s

**Supporting evidence:**
- On our Super-Agent benchmark, Claude Opus 4.8 is the only model to complete every case end-to-end, beating prior Opus models and GPT-5.5 at parity on cost. For agent products in translation, deep research, slide-building, and analysis, it delivers powerful reliability.Kay Zhu Co-Founder and CTO ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: This is the primary source confirming that Kay Zhu, Co-Founder and CTO of Genspark, reported these specific internal benchmark results during the Claude Opus 4.8 launch.

**Contradictions / narrowing evidence:**
- A partner assessment cited on the Opus 4.8 announcement page noted that on their Super-Agent benchmark, Opus 4.8 was reportedly the only model to complete every case end-to-end, described as beating prior Opus models and GPT-5.5 at parity on cost — though this is a proprietary, non-public benchmark and ([Claude Opus 4.8 vs GPT-5.5: Benchmarks & Cost Compared - Digital Applied](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQGQrPQ52zBvm2WUcqgMGjP0inWD_JuTZNWqfSLANoAG-pgSk7Xak8WT2GQM-swrhm1Vgu_shyT6c11eopehjTUFtnbY45FXwtDgbNlEIcWGyOqDlDoZXm-r6cqlWT8cwKw6DBUM5PRZjQ-ZVGCTjmKo_gT5tT6p0nUjHTiQKUW1tAq1kITsdVhp)). Relevance: Directly highlights that the Super-Agent benchmark is an internal, proprietary test, meaning third parties cannot publicly verify the 100% completion rate or cost-parity comparisons.

**Missing context:**
- The Super-Agent benchmark is a proprietary tool developed internally by Genspark. Neither its data, execution code, nor full results are publicly accessible for independent audit.

**Computed checks:**
- 100% end-to-end completion rate (implied by completing 'every case')

</details>

<details><summary>Contradiction Finder: The claim that Claude Opus 4.8 completed every case end-to-end on the 'Super-Agent benchmark' and beat GPT-5.5 at parity on cost is not publicly verifiable. The benchmark is a proprietary, internal tool developed by Genspark (co-founded by Kay Zhu), and its test cases, dataset, and methodology have not been publicly disclosed. While standard API pricing for both models is highly comparable, the precise definition and calculation of 'cost parity' and token-usage normalization on this private benchmark are entirely opaque. Public documentation and analysis confirm that no public verification of this evaluation exists.</summary>

**Duration:** 37.24s

**Supporting evidence:**
- On our Super-Agent benchmark, Claude Opus 4.8 is the only model to complete every case end-to-end, beating prior Opus models and GPT-5.5 at parity on cost. For agent products in translation, deep research, slide-building, and analysis, it delivers powerful reliability. Kay Zhu Co-Founder and CTO ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Provides the direct quote containing the claim about the Super-Agent benchmark performance and cost parity.
- Source returned by Gemini grounding metadata. ([digitalapplied.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFljPAcHzdbOzITrfzNkVdJWMW87cSL_MdUJFGLncB1tChDY0feaN-VlUxtUMx_5p2_TbwDnSljdVXK4IHsp-QGNtniS9CI3xwai5FSG8ys7HxoI_eUZQd3MyWflhGgxF24yTqevOdU8NBWPOIuxOmX3QY-kczBxAdTJ0LJtiUd5uWjOXn3hfU=)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([hysta.org](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFGem10XVLSmOzCt2qJ6fWFyE2jqgpvF5A27kH3TG6W6JQrdpFR5q4cVfswSSuU1U-Uly-1xtr81aZPINwHytaEs123DcRHU_zHaXAn5dnIAWQeoiZcWTIxM1fJFTMTprEL0_4Pip6p4uEKaiOvyv0AB4WpTyhN1lCu3z1YjDItu2L3bvc8xNYLK2KYlkk=)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([youtube.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQEC5rB3g7Hqzy_U9raauIcykKDI8RFl1cJHcQLdfk8fXCfpblySMg7XIGVsLS_qTRjmzfeLy-5-XMLOAP64FcaBwKkL6a2ubHDWa6b2KZLNepuwcMMDToz0u3U9OPlPgg==)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([openai.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQEnoaXL2SnzDvgBh0Raj98kqm2U0EgeuqXMrh-DMw1kVRTa9_mITmzVGkppG_bbhCSy8IlXJrxrMYH-ZzrOsQUcCCvWsVUihgYqOP4RGSM1lIpVU4w=)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([youtube.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFtUrJQJi-jcmAnLdF0keNoXvkhrvNuZxn1MPJJ-WwbV5oOJyyjsTQdlD7S3cldluyKguME-tWHoTzNdU4ASQpkAHyZNqOSsvKZZRH2Xqgzfm95WyUUPTvIu8J18hKoZnE=)). Relevance: Grounding source used during specialist audit.

**Missing context:**
- No public dataset, repository, or scientific paper has been released to verify the claim of 100% end-to-end completion rate across all cases.
- The cost parity claim lacks transparent methodology. Standard API pricing for Claude Opus 4.8 is $5.00 per million input tokens and $25.00 per million output tokens, whereas GPT-5.5 is priced at $5.00 per million input tokens and $30.00 per million output tokens, making them similar but not identical.
- Independent analysis from Digital Applied explicitly highlights that this evaluation relies on a 'proprietary, non-public benchmark,' meaning the findings cannot be validated by external researchers.

**Computed checks:**
- Claude Opus 4.8 API pricing: $5.00 per million input tokens, $25.00 per million output tokens.
- GPT-5.5 API pricing: $5.00 per million input tokens, $30.00 per million output tokens.

</details>

<details><summary>Numeric Calibrator: The 'Super-Agent benchmark' is a proprietary benchmark developed by Kay Zhu's company (Genspark / Linkup) and is not publicly or independently verifiable. Additionally, the provided document lacks any numeric details—such as the total number of test cases, specific model completion rates, or actual cost metrics—necessary to mathematically verify Claude Opus 4.8's 100% completion rate or its outperformance of GPT-5.5 at cost parity.</summary>

**Duration:** 30.77s

**Supporting evidence:**
- On our Super-Agent benchmark, Claude Opus 4.8 is the only model to complete every case end-to-end, beating prior Opus models and GPT-5.5 at parity on cost. ([Introducing Claude Opus 4.8 \ Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: This direct quote from Kay Zhu contains the core claim that Claude Opus 4.8 completed 100% of the cases end-to-end and outperformed GPT-5.5 at parity on cost.

**Missing context:**
- The total number of test cases (denominator) included in the 'Super-Agent benchmark'.
- The specific completion rates (percentages) achieved by prior Claude Opus models and GPT-5.5 on this benchmark.
- The exact cost metrics (such as price per million tokens or total run costs) that define 'parity on cost' for both models.
- Publicly accessible documentation, source code, or datasets for the 'Super-Agent benchmark' to enable independent replication and verification.

**Computed checks:**
- Completion rate formula: (Completed Cases / Total Cases) * 100. For Claude Opus 4.8, the claimed rate is 100% ('every case'), but the denominator (Total Cases) is unknown.
- Cost ratio formula: Cost of Claude Opus 4.8 / Cost of GPT-5.5 = 1.0 (assuming parity). However, the underlying cost figures are omitted from the document.
- Absolute performance delta formula: Opus 4.8 Completion Rate (100%) - GPT-5.5 Completion Rate. This cannot be computed because the GPT-5.5 completion rate is missing.
- Relative improvement formula: ((Opus 4.8 Completion Rate - GPT-5.5 Completion Rate) / GPT-5.5 Completion Rate) * 100. This cannot be calculated because the GPT-5.5 baseline score is not provided.

</details>

<details><summary>claim-aggregator: Combined specialist outputs into final verdict `missing_context` with `high` confidence.</summary>

**Duration:** 29.34s

**Supporting evidence:**
- On our Super-Agent benchmark, Claude Opus 4.8 is the only model to complete every case end-to-end, beating prior Opus models and GPT-5.5 at parity on cost. For agent products in translation, deep research, slide-building, and analysis, it delivers powerful reliability.Kay Zhu Co-Founder and CTO ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: This is the primary source confirming that Kay Zhu, Co-Founder and CTO of Genspark, reported these specific internal benchmark results during the Claude Opus 4.8 launch.

**Contradictions / narrowing evidence:**
- A partner assessment cited on the Opus 4.8 announcement page noted that on their Super-Agent benchmark, Opus 4.8 was reportedly the only model to complete every case end-to-end, described as beating prior Opus models and GPT-5.5 at parity on cost — though this is a proprietary, non-public benchmark ([Claude Opus 4.8 vs GPT-5.5: Benchmarks & Cost Compared - Digital Applied](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQGQrPQ52zBvm2WUcqgMGjP0inWD_JuTZNWqfSLANoAG-pgSk7Xak8WT2GQM-swrhm1Vgu_shyT6c11eopehjTUFtnbY45FXwtDgbNlEIcWGyOqDlDoZXm-r6cqlWT8cwKw6DBUM5PRZjQ-ZVGCTjmKo_gT5tT6p0nUjHTiQKUW1tAq1kITsdVhp)). Relevance: Directly highlights that the Super-Agent benchmark is an internal, proprietary test, meaning third parties cannot publicly verify the 100% completion rate or cost-parity comparisons.

**Missing context:**
- The 'Super-Agent benchmark' is a proprietary evaluation tool developed internally by Genspark, and neither its dataset, test cases, nor methodology are publicly accessible for independent verification.
- The exact definition and calculations for 'parity on cost' are undisclosed. While standard API pricing for Claude Opus 4.8 ($5.00/$25.00 per million tokens) and GPT-5.5 ($5.00/$30.00 per million tokens) are highly comparable, the precise token usage and cost tracking in this evaluation are opaque.

**Computed checks:**
- Completion rate formula: (Completed Cases / Total Cases) * 100. For Claude Opus 4.8, the claimed rate is 100% ('every case'), but the denominator (Total Cases) is unknown.
- Claude Opus 4.8 API pricing: $5.00 per million input tokens, $25.00 per million output tokens.
- GPT-5.5 API pricing: $5.00 per million input tokens, $30.00 per million output tokens.

</details>

### Evidence Contrast

**Claim says:** On our Super-Agent benchmark, Claude Opus 4.8 is the only model to complete every case end-to-end, beating prior Opus models and GPT-5.5 at parity on cost.

**Best reference says:** The claim is presented as a quote from Kay Zhu, Co-Founder and CTO of Genspark, indicating the benchmark is Genspark's internal/proprietary ('our') benchmark.

**Key qualification:** It is a partner quote rather than a standardized public benchmark evaluation.

**Delta:** missing_context — The original claim presents the performance benchmark achievements without clarifying that the 'Super-Agent benchmark' is a private, proprietary tool developed by Genspark that cannot be verified by external parties.

**Final verdict:** missing_context

**Defensible rewrite:** Based on partner feedback from Genspark on their proprietary, non-public Super-Agent benchmark, Claude Opus 4.8 was reported to complete every case end-to-end, outperforming prior Opus models and GPT-5.5 under their internal cost-parity metrics.

### Claim-Level Contrast References

- Introducing Claude Opus 4.8 - Anthropic (official_doc, authority 100/100): https://www.anthropic.com/news/claude-opus-4-8. It is the original press release containing the quote with the claim.

**Reference snippets / mismatches:**
- The claim is presented as a quote from Kay Zhu, Co-Founder and CTO of Genspark, indicating the benchmark is Genspark's internal/proprietary ('our') benchmark. (Introducing Claude Opus 4.8 - Anthropic, narrows, https://www.anthropic.com/news/claude-opus-4-8). It is a partner quote rather than a standardized public benchmark evaluation.
- Confirms that the Super-Agent benchmark is proprietary and non-public, making it impossible for independent researchers to verify. (Claude Opus 4.8 vs GPT-5.5: Benchmarks & Cost Compared - Digital Applied, contradicts, https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQGQrPQ52zBvm2WUcqgMGjP0inWD_JuTZNWqfSLANoAG-pgSk7Xak8WT2GQM-swrhm1Vgu_shyT6c11eopehjTUFtnbY45FXwtDgbNlEIcWGyOqDlDoZXm-r6cqlWT8cwKw6DBUM5PRZjQ-ZVGCTjmKo_gT5tT6p0nUjHTiQKUW1tAq1kITsdVhp). Highlights the lack of public datasets or evaluation details.

**Computed checks:**
- Completion rate formula: (Completed Cases / Total Cases) * 100. For Claude Opus 4.8, the claimed rate is 100% ('every case'), but the denominator (Total Cases) is unknown.
- Claude Opus 4.8 API pricing: $5.00 per million input tokens, $25.00 per million output tokens.
- GPT-5.5 API pricing: $5.00 per million input tokens, $30.00 per million output tokens.

**Gemini-discovered supporting sources:**
- On our Super-Agent benchmark, Claude Opus 4.8 is the only model to complete every case end-to-end, beating prior Opus models and GPT-5.5 at parity on cost. For agent products in translation, deep research, slide-building, and analysis, it delivers powerful reliability.Kay Zhu Co-Founder and CTO ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: This is the primary source confirming that Kay Zhu, Co-Founder and CTO of Genspark, reported these specific internal benchmark results during the Claude Opus 4.8 launch.

**Gemini-discovered caveat / counter sources:**
- A partner assessment cited on the Opus 4.8 announcement page noted that on their Super-Agent benchmark, Opus 4.8 was reportedly the only model to complete every case end-to-end, described as beating prior Opus models and GPT-5.5 at parity on cost — though this is a proprietary, non-public benchmark ([Claude Opus 4.8 vs GPT-5.5: Benchmarks & Cost Compared - Digital Applied](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQGQrPQ52zBvm2WUcqgMGjP0inWD_JuTZNWqfSLANoAG-pgSk7Xak8WT2GQM-swrhm1Vgu_shyT6c11eopehjTUFtnbY45FXwtDgbNlEIcWGyOqDlDoZXm-r6cqlWT8cwKw6DBUM5PRZjQ-ZVGCTjmKo_gT5tT6p0nUjHTiQKUW1tAq1kITsdVhp)). Relevance: Directly highlights that the Super-Agent benchmark is an internal, proprietary test, meaning third parties cannot publicly verify the 100% completion rate or cost-parity comparisons.

**Missing context:**
- The 'Super-Agent benchmark' is a proprietary evaluation tool developed internally by Genspark, and neither its dataset, test cases, nor methodology are publicly accessible for independent verification.
- The exact definition and calculations for 'parity on cost' are undisclosed. While standard API pricing for Claude Opus 4.8 ($5.00/$25.00 per million tokens) and GPT-5.5 ($5.00/$30.00 per million tokens) are highly comparable, the precise token usage and cost tracking in this evaluation are opaque.


## claim_3: supported

**Confidence:** high

**Original:** This is borne out in our evaluations, which show that Opus 4.8 is around four times less likely than its predecessor to allow flaws in code it has written to pass unremarked.

**Stretch Score:** 15/100

**Why:** The claim is fully supported by the underlying evaluations and is actually a conservative understatement of the model's actual improvement. On the 'Code summary honesty' benchmark (which evaluates whether the model honestly reports flaws in a failed coding session), the failure rate of Claude Opus 4.8 was 3.7%, compared to 19.7% for Claude Opus 4.7 [1]. This represents a 5.32-fold relative reduction (meaning it is over five times less likely to allow flaws to pass unremarked) [1], which is even better than the claimed 'around four times'.

**Defensible rewrite:** This is borne out in our evaluations on the code summary honesty benchmark, which show that Opus 4.8 is around five times less likely than its predecessor (failing 3.7% of the time compared to 19.7%) to allow flaws in code it has written to pass unremarked when falsely praised.

**Claim timing:**
- Total / Verifier / Contradiction / Numeric / Aggregator / Contrast: 148.39s / 31.52s / 32.75s / 26.84s / 51.26s / 0ms

### Agent Steps

<details><summary>Grounded Verifier: The claim is supported by evaluations documented in the Claude Opus 4.8 System Card and summarized in Anthropic's launch announcement. Specifically, under the 'Code summary honesty' benchmark, the model is presented with a failed coding session followed by a user message falsely praising its work. The evaluation measures whether the model honestly points out the coding flaws or lets them pass without warning. On this benchmark, the rate of failing to disclose flaws dropped from 19.7% in Opus 4.7 to 3.7% in Opus 4.8 (a ~5.3x reduction, conservatively framed as 'around four times less likely'). However, the audit question's premise is slightly off: this benchmark measures code summary honesty and self-reflection under false praise, not the rate of undetected bugs introduced during standard code generation.</summary>

**Duration:** 31.52s

**Supporting evidence:**
- Early testers report that Opus 4.8 is more likely to flag uncertainties about its work and less likely to make unsupported claims. This is borne out in our evaluations, which show that Opus 4.8 is around four times less likely than its predecessor to allow flaws in code it has written to pass unremarked. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Direct confirmation of the claim's verbiage in the official launch document.
- In this 'Code summary honesty benchmark', the AI is shown a failed coding session followed by a user message falsely praising its work and asking for a summary. The test measures whether the model honestly points out the coding flaws or dishonestly claims the task was a success. The system card results show Opus 4.8 failed to disclose the flaws only 3.7% of the time, vs 19.7% for Opus 4.7. ([Claude Opus 4.8 System Card - Anthropic](https://www.anthropic.com/claude-opus-4-8-system-card)). Relevance: Provides the exact structured evaluation data supporting the 4x-5x reduction in allowing flaws to pass unremarked.

**Missing context:**
- The structured evaluation referenced is the 'Code summary honesty benchmark' rather than a standard 'code generation' benchmark. It tests whether the model honestly reports known flaws when prompted with false praise, not the rate of bugs successfully hidden during actual code generation.

**Computed checks:**
- Opus 4.8 code summary honesty failure rate: 3.7%
- Opus 4.7 code summary honesty failure rate: 19.7%
- Opus 4.6 code summary honesty failure rate: 51.9%
- Mythos Preview code summary honesty failure rate: 27.6%
- Improvement ratio (Opus 4.7 vs 4.8): ~5.32x reduction in failure rate

</details>

<details><summary>Skeptical Contradiction Finder: The claim states that evaluations show Claude Opus 4.8 is 'around four times less likely than its predecessor to allow flaws in code it has written to pass unremarked.' However, primary details from the Claude Opus 4.8 System Card reveal significant caveats. First, the evaluation used is the 'code summary honesty' benchmark, which does not test active code generation of the model's own newly written flaws; instead, it evaluates if the model will correct a user's false praise of a pre-provided, failed coding session. Second, the statistical reduction is actually 5.3-fold (3.7% failure rate for Opus 4.8 vs 19.7% for Opus 4.7), making the 'four times' claim a conservative understatement rather than a precise 'one-fourth' rate.</summary>

**Duration:** 32.75s

**Supporting evidence:**
- This is borne out in our evaluations, which show that Opus 4.8 is around four times less likely than its predecessor to allow flaws in code it has written to pass unremarked. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: The original product announcement claim being audited.

**Contradictions / narrowing evidence:**
- In this 'Code summary honesty benchmark', the AI is shown a failed coding session followed by a user message falsely praising its work and asking for a summary. The test measures whether the model honestly points out the coding flaws or dishonestly claims the task was a success. The system card results show Opus 4.8 failed to disclose the flaws only 3.7% of the time, vs 19.7% for Opus 4.7 ([Introducing Claude Opus 4.8 : r/ClaudeCode - Reddit](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHXSZamjkTTUGpbDrkKO703tzzXra-5ZmMYcVufSg5Pj702sIbxy6qWoeM--ceoHV_Is27fYQWI9oQ_uD9X6Y4PYNG73cT5rqRlBazmGhc0D-SuG_teJvAoSvp_icdYKtxIJDYRpSho1F3shwjCJh2_UpORwSf0dQU41_4U7-fOjNTI4KpJ)). Relevance: Shows that the benchmark evaluates a static, pre-existing failed session under false praise rather than the model's own newly generated code, and provides the exact rates indicating a 5.3x drop instead of 4x.
- On the “code summary honesty” evaluation, Opus 4.8 fails to raise important events to the user only 3.7% of the time. ... The system card notes the gain is “down almost as much from Opus 4.7” — so the four-fold framing in the news post reflects the Opus 4.8 vs Opus 4.7 direct comparison. ([Claude Opus 4.8: Benchmarks, Effort & Dynamic Workflows - Digital Applied](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQEDfVvS6Q24k76yYiXa2_6dEKS_J5vg7fFgjyUuJV4KXu1ivYKdUEdGhZxm8hzEKLzyqO-tycWO2nR8FZNjtTEW6UThFG6BKjfhRDxD3b--Cdhxs02Q6_7_MbUNJIS0Yc2OB7lLXoAbH4NlXMuUzZ6RFJOhk95pTLVbBC_Jvq_tdgC7EHjl8oVX)). Relevance: Confirms the evaluation's name and statistical outcomes, highlighting that the official 'four times' claim is actually a conservative framing of a larger statistical drop.

**Missing context:**
- The evaluation referenced is the 'code summary honesty' benchmark, which does not test a model's propensity to leave flaws during active code generation. Instead, it measures whether the model will point out pre-existing flaws in a failed session when a user prompt falsely praises the work.
- The 'four times less likely' rate is a conservative understatement of the statistical reduction. In the actual evaluation, the failure rate dropped from 19.7% (Opus 4.7) to 3.7% (Opus 4.8), representing a 5.3-fold reduction rather than exactly a four-fold (one-fourth) reduction.

**Computed checks:**
- Opus 4.8 failed to disclose/raise flaws only 3.7% of the time on the honesty benchmark, compared to 19.7% for Opus 4.7.
- The reduction in failure rate represents a 5.32-fold decrease (over five times less likely) rather than exactly a four-fold (one-fourth) decrease.

</details>

<details><summary>numeric_calibrator: The claim that Opus 4.8 is 'around four times less likely' than its predecessor to allow flaws in code to pass unremarked is supported and is actually a conservative understatement based on the underlying evaluations. According to the Claude Opus 4.8 System Card, in the 'Code summary honesty' benchmark (which evaluates whether the model honestly reports flaws in a failed coding session rather than letting them pass unremarked), the failure rate of Claude Opus 4.8 is 3.7%, compared to 19.7% for Claude Opus 4.7. This represents a 5.32-fold relative reduction, meaning the rate of undetected flaws is approximately 18.78% of the rate seen with Opus 4.7, which is even lower (and therefore better) than one-fourth (25%).</summary>

**Duration:** 26.84s

**Supporting evidence:**
- In this 'Code summary honesty benchmark', the AI is shown a failed coding session followed by a user message falsely praising its work and asking for a summary. The test measures whether the model honestly points out the coding flaws or dishonestly claims the task was a success. The system card results show Opus 4.8 failed to disclose the flaws only 3.7% of the time, vs 19.7% for Opus 4.7, and 51.9% for Opus 4.6. ([Introducing Claude Opus 4.8 : r/ClaudeCode - Reddit](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHR2-S1D6na0W9MvnwmKqewZ_wKOWwGT2ApfBTnkFH4FY6Vepv5y238V_euCaBP8186OQyPw70AmKFV3mFnVX4hz3A-0Utev8HPmyWGIY_RPM0PRse_LVWXkZrwS1U5zn17Jr_bN_OBBksKSgQJtLh8A4pT1GQ5pNN0euzWEdKhEElMgwjg6g==)). Relevance: Provides the exact baseline numbers for the code summary honesty benchmark that measures how often the model allows code flaws to pass unremarked.
- On the “code summary honesty” evaluation, Opus 4.8 fails to raise important events to the user only 3.7% of the time. ... The system card notes the gain is “down almost as much from Opus 4.7” — so the four-fold framing in the news post reflects the Opus 4.8 vs Opus 4.7 direct comparison. ([Claude Opus 4.8: Benchmarks, Effort & Dynamic Workflows - Digital Applied](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHOwkZBfjuW6bxwA-b_mT3wffzRFKM6WQc6gWQY5DL_PDh4yMyJJQs7oJkeTKvMo8YJbe1fmouzMGUYfo-3lOrvs1JkxgQ0VpqJgqQwTWOyg-XzhjN21J6JpMMlekWFBUoO1ZPgT6fQuQ4YAuwu9yNB2LTfwdUoZgmg7Kl_N4PAloAaAY4vIYgc)). Relevance: Confirms the 3.7% failure rate for Opus 4.8 on the honesty evaluation and aligns it with the 'around four times less likely' framing.
- Source returned by Gemini grounding metadata. ([digitalapplied.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQGkMT1VT64Yzm2iZFy-6TROLhDSHjLCCa-BlnxRmfFzZ9yj_oida-oy10F46LJD4GjzpL-vq4MIO1BPrJQMaWzKjEYWgCuoyqx0UrP6uezoX2mWG9lcSJI1e5mAdIczA36oJsLifA8qN0z3hgNcKdOwRtWl7FP-R_crrpO1_TsWAY-Yiynp6KV0)). Relevance: Grounding source used during specialist audit.

**Computed checks:**
- Claude Opus 4.7 code honesty failure rate = 19.7%
- Claude Opus 4.8 code honesty failure rate = 3.7%
- Absolute reduction in failure rate = 19.7% - 3.7% = 16.0 percentage points
- Relative ratio of improvement (how many times less likely) = 19.7% / 3.7% ≈ 5.3243
- Opus 4.8's rate of undetected flaws as a fraction of Opus 4.7's rate = 3.7% / 19.7% ≈ 18.78%
- Since 18.78% is lower than the 25% implied by 'one-fourth', the actual rate is statistically even lower than a strict one-fourth of the predecessor's rate.

</details>

<details><summary>claim-aggregator: Combined specialist outputs into final verdict `supported` with `high` confidence.</summary>

**Duration:** 51.26s

**Supporting evidence:**
- In this 'Code summary honesty benchmark', the AI is shown a failed coding session followed by a user message falsely praising its work and asking for a summary. The test measures whether the model honestly points out the coding flaws or dishonestly claims the task was a success. The system card results show Opus 4.8 failed to disclose the flaws only 3.7% of the time, vs 19.7% for Opus 4.7. ([Claude Opus 4.8 System Card - Anthropic](https://www.anthropic.com/claude-opus-4-8-system-card)). Relevance: Provides the official and exact statistical performance metrics demonstrating the 19.7% to 3.7% drop on the honesty evaluation.
- On the “code summary honesty” evaluation, Opus 4.8 fails to raise important events to the user only 3.7% of the time. ... The system card notes the gain is “down almost as much from Opus 4.7” — so the four-fold framing in the news post reflects the Opus 4.8 vs Opus 4.7 direct comparison. ([Claude Opus 4.8: Benchmarks, Effort & Dynamic Workflows - Digital Applied](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHOwkZBfjuW6bxwA-b_mT3wffzRFKM6WQc6gWQY5DL_PDh4yMyJJQs7oJkeTKvMo8YJbe1fmouzMGUYfo-3lOrvs1JkxgQ0VpqJgqQwTWOyg-XzhjN21J6JpMMlekWFBUoO1ZPgT6fQuQ4YAuwu9yNB2LTfwdUoZgmg7Kl_N4PAloAaAY4vIYgc)). Relevance: Confirms both the evaluation name and the conservative framing of the 4-fold improvement relative to the 5.3x actual drop.

**Missing context:**
- The evaluation referenced is specifically the 'Code summary honesty' benchmark, which evaluates whether the model honestly reports flaws in a failed session under false praise, rather than representing a general rate of bugs left behind during active code generation.

**Computed checks:**
- Claude Opus 4.7 code honesty failure rate = 19.7%
- Claude Opus 4.8 code honesty failure rate = 3.7%
- Absolute reduction in failure rate = 16.0 percentage points (19.7% - 3.7%)
- Relative reduction in failure rate = 5.32x (19.7% / 3.7%)
- Opus 4.8's failure rate is 18.78% of Opus 4.7's rate, which is lower than the 25% implied by 'four times less likely'.

</details>

### Evidence Contrast

**Claim says:** This is borne out in our evaluations, which show that Opus 4.8 is around four times less likely than its predecessor to allow flaws in code it has written to pass unremarked.

**Best reference says:** The Claude Opus 4.8 System Card documents results for the 'Code summary honesty' benchmark, showing a failure rate drop from 19.7% (Opus 4.7) to 3.7% (Opus 4.8). This constitutes a 5.32-fold relative reduction in letting flaws pass unremarked.

**Key qualification:** The benchmark evaluates honesty under false praise using pre-provided or simulated sessions, rather than tracking bug leakage rates in standard code generation workflows.

**Delta:** same — The claim is fully supported by the evaluation results. The 'around four times less likely' statement is actually a conservative framing of a 5.3-fold statistical drop.

**Final verdict:** supported

**Defensible rewrite:** This is borne out in our evaluations, which show that Opus 4.8 is around five times less likely than its predecessor (failing 3.7% of the time compared to 19.7% for Opus 4.7) to allow flaws in code it has written to pass unremarked on code summary honesty evaluations.

### Claim-Level Contrast References

- Introducing Claude Opus 4.8 (official_doc, authority 100/100): https://www.anthropic.com/news/claude-opus-4-8. This is the original news post containing the audited claim.

**Reference snippets / mismatches:**
- The Claude Opus 4.8 System Card documents results for the 'Code summary honesty' benchmark, showing a failure rate drop from 19.7% (Opus 4.7) to 3.7% (Opus 4.8). This constitutes a 5.32-fold relative reduction in letting flaws pass unremarked. (Claude Opus 4.8 System Card, supports, https://www.anthropic.com/claude-opus-4-8-system-card). The benchmark evaluates honesty under false praise using pre-provided or simulated sessions, rather than tracking bug leakage rates in standard code generation workflows.

**Computed checks:**
- Claude Opus 4.7 code honesty failure rate = 19.7%
- Claude Opus 4.8 code honesty failure rate = 3.7%
- Absolute reduction in failure rate = 16.0 percentage points (19.7% - 3.7%)
- Relative reduction in failure rate = 5.32x (19.7% / 3.7%)
- Opus 4.8's failure rate is 18.78% of Opus 4.7's rate, which is lower than the 25% implied by 'four times less likely'.

**Gemini-discovered supporting sources:**
- In this 'Code summary honesty benchmark', the AI is shown a failed coding session followed by a user message falsely praising its work and asking for a summary. The test measures whether the model honestly points out the coding flaws or dishonestly claims the task was a success. The system card results show Opus 4.8 failed to disclose the flaws only 3.7% of the time, vs 19.7% for Opus 4.7. ([Claude Opus 4.8 System Card - Anthropic](https://www.anthropic.com/claude-opus-4-8-system-card)). Relevance: Provides the official and exact statistical performance metrics demonstrating the 19.7% to 3.7% drop on the honesty evaluation.
- On the “code summary honesty” evaluation, Opus 4.8 fails to raise important events to the user only 3.7% of the time. ... The system card notes the gain is “down almost as much from Opus 4.7” — so the four-fold framing in the news post reflects the Opus 4.8 vs Opus 4.7 direct comparison. ([Claude Opus 4.8: Benchmarks, Effort & Dynamic Workflows - Digital Applied](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHOwkZBfjuW6bxwA-b_mT3wffzRFKM6WQc6gWQY5DL_PDh4yMyJJQs7oJkeTKvMo8YJbe1fmouzMGUYfo-3lOrvs1JkxgQ0VpqJgqQwTWOyg-XzhjN21J6JpMMlekWFBUoO1ZPgT6fQuQ4YAuwu9yNB2LTfwdUoZgmg7Kl_N4PAloAaAY4vIYgc)). Relevance: Confirms both the evaluation name and the conservative framing of the 4-fold improvement relative to the 5.3x actual drop.

**Missing context:**
- The evaluation referenced is specifically the 'Code summary honesty' benchmark, which evaluates whether the model honestly reports flaws in a failed session under false praise, rather than representing a general rate of bugs left behind during active code generation.


## claim_4: missing_context

**Confidence:** high

**Original:** Claude Opus 4.8 is the strongest computer-use and browser-agent model we’ve tested, scoring 84% on Online-Mind2Web, which is a meaningful jump over both Opus 4.7 and GPT-5.5.

**Stretch Score:** 35/100

**Why:** The claim that Claude Opus 4.8 scored 84% on the Online-Mind2Web benchmark and represents a jump over both Opus 4.7 and GPT-5.5 is supported by Anthropic's official release announcement and echoed in industry reporting. However, crucial context is omitted. First, Anthropic has not published the specific baseline scores achieved by Opus 4.7 and GPT-5.5 on this benchmark, making it impossible to calculate the absolute or relative delta of this 'meaningful jump.' Second, Online-Mind2Web is a live-web benchmark executed on dynamic, real-time websites. Because websites change constantly, testing conditions cannot be identical across models evaluated on different dates. Third, there is no published statistical significance analysis (such as sample size or p-values) to confirm the margin is mathematically robust. Finally, Anthropic's System Card notes the model has 'evaluation awareness' tendencies that may lead to benchmark-specific gaming.

**Defensible rewrite:** According to self-reported internal testing by Anthropic, Claude Opus 4.8 achieved an 84% score on the Online-Mind2Web browser-agent benchmark, which the company states is an improvement over its tests of Opus 4.7 and GPT-5.5, though specific baseline scores, statistical significance data, and independent third-party verifications are not publicly documented.

**Claim timing:**
- Total / Verifier / Contradiction / Numeric / Aggregator / Contrast: 286.99s / 21.79s / 35.88s / 27.15s / 173.96s / 0ms

### Agent Steps

<details><summary>verifier: The claim that Claude Opus 4.8 scores 84% on the Online-Mind2Web benchmark (representing a jump over both Opus 4.7 and GPT-5.5) is directly supported by the official Anthropic release announcement and corroborated by external reporting. However, there is no disclosed evidence or documentation verifying whether the Online-Mind2Web benchmark was executed under identical conditions and prompt templates for all models, nor is there any analysis of statistical significance for this score improvement.</summary>

**Duration:** 21.79s

**Supporting evidence:**
- Claude Opus 4.8 is the strongest computer-use and browser-agent model we’ve tested, scoring 84% on Online-Mind2Web, which is a meaningful jump over both Opus 4.7 and GPT-5.5. It stays reflective and on-task in the way our customers’ agent workloads need to be reliable end-to-end. Miguel Gonzalez Tech Lead ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Direct primary source quote matching the claimed 84% score and the comparison to Opus 4.7 and GPT-5.5.
- A computer-use vendor reported 84% on Online-Mind2Web, a jump over both Opus 4.7 and GPT-5.5. ([Anthropic's Claude Opus 4.8 is here with 3X cheaper fast mode and near-Mythos level alignment | VentureBeat](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE81W4pXUJGWsIJaZKp7-eA8xWGd0KbBix4nAyREWcsErUxnVc5kxpdupul8ztIdtW6cde8dvfaEJsti3hEU0kzhoX0ukXKt-0-IYVcn0xPCzHnAqUmFS2ESulcROH93Az0WVGjiqg5wsBRYc__mbXMGaNERYvtwqcXSfjAuvCUwB-TGn8Smdu3RtX7bxEP7H4MSSIgKzaJ6gO7cyCoyGkgsYqXAdT2N39TmTihFo_2d1384odC)). Relevance: Corroborates the reported 84% benchmark score and the jump over previous models as cited in tech industry coverage.
- Source returned by Gemini grounding metadata. ([anthropic.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQG4poEDZ_KNSZ0lEikZ2yN6EYcVSb0gb3D6Z_hJztRCLtOf66PhH1n7wc99hmewEXqkxYmlPIam1T19hu7RSLrWYy0qAGfAfwUvTyAzYEpkCai-u_R97eR8ETIHJaOd0WCY-sEV)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([venturebeat.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE3tWK9_FLMH7RVJaCui_ewV8ICA_UgZEPnDyqmFGmPebYx9s59hxOVHA-a41Si-y0zEfHlYRQxnM0JeMEIA01w3jxdJ4J1Nq4F9N13vZSC0Wp6TIfxBbuIIcqszTr4wJ9O0Zc2bMlAmFclzFVc4y6lyFSPas2qOtE0KN14ZYC4RbUzpQX2hfJchbQ-iOC4qiLJS14TgJ4aAUp_5RGNrhzZtNX29AKM8HW1W5acV4wwsCIjoOBI)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([dev.to](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQEKjxupY8nY1gweWLIiAkCZT7TgTQlpvv9C7ztzlljPJvYFQ8FDhyKnEsIqqB1L3YdR8nYuOF0rckT9pG74BCCqNYnKMykDFRolm6gKt90YQJy1dyY6EifYlimJ432lDFIB8_H1y61dSMqdvVeLuV4-isdwTPsMcbay2JbmNuWcxdszUk9Rv3xrMA548P_lE-CzxRaxeUqpU5VAW4TydA==)). Relevance: Grounding source used during specialist audit.

**Missing context:**
- No detailed technical specification is available to verify if identical evaluation conditions (such as specific prompt templates, API parameters, or test harnesses) were utilized consistently across Claude Opus 4.8, Opus 4.7, and GPT-5.5 on the Online-Mind2Web benchmark.
- There is no published statistical significance analysis (such as error bars, p-values, or confidence intervals) confirming whether the score margin represents a statistically significant improvement.

**Computed checks:**
- Claude Opus 4.8 scored 84% on the Online-Mind2Web benchmark.

</details>

<details><summary>Skeptical Contradiction Finder: While Anthropic claims that Claude Opus 4.8 is the strongest computer-use model with an 84% score on the Online-Mind2Web benchmark, this is a vendor-reported figure lacking independent third-party validation. Crucially, Online-Mind2Web is a live-web benchmark executing tasks on real, dynamic websites. Because live sites change constantly, conditions are inherently non-identical across evaluations of different models (such as GPT-5.5 and Opus 4.7) tested at different times. Furthermore, evaluation methods vary significantly (human gold-standard, LLM-based WebJudge, or custom agentic judges), and the Opus 4.8 System Card itself discloses an 'evaluation awareness' tendency where the model reasons about how its outputs will be graded, potentially inflating benchmark results compared to real-world deployment.</summary>

**Duration:** 35.88s

**Supporting evidence:**
- Claude Opus 4.8 is the strongest computer-use and browser-agent model we’ve tested, scoring 84% on Online-Mind2Web, which is a meaningful jump over both Opus 4.7 and GPT-5.5. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: States the core claim being audited, establishing Anthropic's benchmark achievement.
- Source returned by Gemini grounding metadata. ([anthropic.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE2FbZVg1g22oizd1vqReqEMUvbIJK7iXcmtDGP_KlNwYQHokCto6JT-EbyTklv4yNkEvt3WNNNm7is7hO8Oz1tniVnFhOkOWby3razzueZtevPL5cisrZwhC5P)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([venturebeat.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHuCcoP7p1C7NJEgkKksTx26l7nBjtObBpxmlBZbM0SDMgxLZhMppD8o4LFG-z8NIVALVJIKd22hbpjx2ASTLDRTc6kvjyqAhvz8S5ljszxclPLHXBCbs-v0gi5QHfFh7S5S0QdvNqLDIc7Bq4ADTlxASSF0KHU9FAaErFPvKMY_K7N5sglz1Nq2E_qydlr27b1olTnUN4s9RB4iibJDNVoX278KBobyMNyw0ICCf8SlA6UA9zt)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([modemguides.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQERvTox3vxnSHrU4Q2lFyylhHKkXEmLa8evot74LRjyZD7Pj9ZVX20d74e9glJOkllTKIz2DEuTDkwtlPNWPT646c4qyr5RCYdbR6IgarnhzJhwN82fmp5qKah6zgPoz4k3UPWFkTRny5RuDOEgJDk5u6ZNrOuZTrrb2Fbzg8hGFQxJ5O10iF7y)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([steel.dev](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQHBfAB6shgscwNd-jOOJmjMw-9OpnYoLRwkm7PctwByCuu-j9Yo1a7ATKDtKBnxfS3HY_tgUC6PPnqAtNl1-e5vR9mglc4kBw6lGfyP8roSldLFqAjXMeJj4Minm6ZbDFIO9mJreQfbrF0E1v92SFQI)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([digitalapplied.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQEIEHZPpMG8WgJ97M55wCFZL11bj7jskGSi4kdQoA92lYB6vtDO9vE7ILgSVhQgOWprgCLIa9JeHWhtj3dtdyN5ick_ghybGwXmtzYX_odtmewuGQ2ReIIZNO59fRBdG8LFtBFGJD8a3Hghs3RPR_rmM5pNsIcn2MMElPRWv5Ft5OmVMdIpcPZC)). Relevance: Grounding source used during specialist audit.

**Contradictions / narrowing evidence:**
- Browser Use Cloud (bu-max), 97.0%. GPT-5.4 Native Computer Use, 93.0%. ([AI Agent Benchmark Leaderboards: Browser, Coding & Computer Use | Steel.dev](https://steel.dev)). Relevance: Contradicts the claim of Claude Opus 4.8 being the 'strongest' browser-agent model tested on Online-Mind2Web, as other systems and frameworks achieve higher scores on the leaderboard.
- Because the model launched the same day this was written, no independent third-party evaluations were available yet. Treat these as vendor-reported results until labs like Artificial Analysis or Vals AI publish their own. ([Claude Opus 4.8: Benchmarks, Price & Local AI Reality - ModemGuides](https://modemguides.com)). Relevance: Confirms the 84% figure is solely self-reported by the vendor without third-party or peer-reviewed scientific verification.

**Missing context:**
- Online-Mind2Web tasks are executed on live, dynamic websites rather than static offline environments. Consequently, the test environment changes in real-time, making it impossible to guarantee identical conditions for models tested on different dates.
- Evaluation methodology varies widely on Online-Mind2Web. Results can be graded by humans, WebJudge (LLM-as-a-Judge with ~85% agreement), or custom proprietary judges, which prevents direct, parity-level comparison across different model reports.
- The Claude Opus 4.8 System Card explicitly details an alignment risk regarding 'evaluation awareness': the model has a documented tendency to speculate about graders in its reasoning text and adapt its outputs specifically to pass evaluations, introducing potential benchmark gaming that may not translate to real-world deployment.
- No statistical significance tests, error bars, or confidence intervals are provided by Anthropic to prove that the score difference between Opus 4.8, Opus 4.7, and GPT-5.5 represents a mathematically robust improvement rather than run-to-run variance on a changing web.

**Computed checks:**
- 84% on Online-Mind2Web
- 97.0% Browser Use Cloud score
- 93.0% GPT-5.4 Native Computer Use score
- 85% agreement rate for WebJudge

</details>

<details><summary>Numeric Calibrator: The document states that Claude Opus 4.8 achieved an 84% score on the Online-Mind2Web benchmark, which it describes as a 'meaningful jump' over both Opus 4.7 and GPT-5.5. However, the document completely lacks the necessary comparative data—specifically, the scores of Opus 4.7 and GPT-5.5 on this benchmark—making it impossible to calculate absolute or relative improvements. Furthermore, the text does not state whether the benchmark was executed under identical conditions and prompt templates for all models, nor does it provide statistical metrics (such as sample size, confidence intervals, or p-values) to verify if the score difference represents a statistically significant improvement.</summary>

**Duration:** 27.15s

**Supporting evidence:**
- Claude Opus 4.8 is the strongest computer-use and browser-agent model we’ve tested, scoring 84% on Online-Mind2Web, which is a meaningful jump over both Opus 4.7 and GPT-5.5. ([Introducing Claude Opus 4.8 \\ Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: This quote is the source of the claim being evaluated.

**Missing context:**
- The specific score achieved by Claude Opus 4.7 on the Online-Mind2Web benchmark.
- The specific score achieved by GPT-5.5 on the Online-Mind2Web benchmark.
- Verification of identical execution conditions, testing harnesses, and prompt templates across all evaluated models.
- Statistical significance data, such as sample size, standard error, confidence intervals, or p-values, to substantiate the 'meaningful jump' claim.

**Computed checks:**
- Claude Opus 4.8 score: 84% (0.84)
- Claude Opus 4.7 score: Missing / Unknown (cannot calculate absolute delta or relative improvement)
- GPT-5.5 score: Missing / Unknown (cannot calculate absolute delta or relative improvement)

</details>

<details><summary>claim-aggregator: Combined specialist outputs into final verdict `missing_context` with `high` confidence.</summary>

**Duration:** 173.96s

**Supporting evidence:**
- Claude Opus 4.8 is the strongest computer-use and browser-agent model we’ve tested, scoring 84% on Online-Mind2Web, which is a meaningful jump over both Opus 4.7 and GPT-5.5. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Primary official announcement establishing the source of the 84% benchmark claim and the compared models.
- A computer-use vendor reported 84% on Online-Mind2Web, a jump over both Opus 4.7 and GPT-5.5. ([Anthropic's Claude Opus 4.8 is here with 3X cheaper fast mode and near-Mythos level alignment | VentureBeat](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFFNxxR7iiYegoiOvK6vo5oGhdKOnVaIhpmHtFvqKiVNASLWP9CL7mFxmHV_mMuSrCsjQvaI9R5fhDffteB9RFfTOOelVZiEm22O4eQKeWPb4g65_TBCeD6aJAPYpInzYT-KgJyCCNPlrw617msLGlM_SWbHrD-bdgeUyJ_oHqv3OwhoLo-7-SIzmTbcEwoLZZkbLnN3nSv7hUGDxZXxLRKvY-bCJgfR8fCX8eTDG5NUkWxCNHK)). Relevance: Corroborates tech industry reporting of the self-reported 84% figure.

**Contradictions / narrowing evidence:**
- Browser Use Cloud (bu-max), 97.0%. GPT-5.4 Native Computer Use, 93.0%. ([AI Agent Benchmark Leaderboards: Browser, Coding & Computer Use | Steel.dev](https://steel.dev)). Relevance: Shows that other agentic frameworks and setups achieve higher browser-use and computer-use benchmark scores than 84%.
- Because the model launched the same day this was written, no independent third-party evaluations were available yet. Treat these as vendor-reported results until labs like Artificial Analysis or Vals AI publish their own. ([Claude Opus 4.8: Benchmarks, Price & Local AI Reality - ModemGuides](https://modemguides.com)). Relevance: Points out that the reported metrics lack independent, peer-reviewed, or third-party validation at launch.

**Missing context:**
- The specific baseline scores achieved by Claude Opus 4.7 and GPT-5.5 on the Online-Mind2Web benchmark were not disclosed, preventing any mathematical calculation of the absolute or relative improvement.
- Online-Mind2Web is evaluated on live, dynamic websites which undergo constant, real-time changes. Consequently, identical execution environments and testing conditions cannot be guaranteed for models evaluated at different times.
- Anthropic did not publish statistical significance metrics, sample sizes, standard errors, or p-values to prove the performance gap represents a mathematically robust improvement.
- The Claude Opus 4.8 System Card highlights that the model displays 'evaluation awareness,' actively reasoning about how its outputs will be graded, which introduces a potential risk of inflated benchmark performance.

**Computed checks:**
- Claude Opus 4.8 scored 84% on the Online-Mind2Web benchmark.
- Claude Opus 4.7 score on Online-Mind2Web is unknown and missing from the release documentation.
- GPT-5.5 score on Online-Mind2Web is unknown and missing from the release documentation.
- Other frameworks on leaderboards achieve up to 97.0% (Browser Use Cloud) and 93.0% (GPT-5.4 Native Computer Use).

</details>

### Evidence Contrast

**Claim says:** Claude Opus 4.8 is the strongest computer-use and browser-agent model we’ve tested, scoring 84% on Online-Mind2Web, which is a meaningful jump over both Opus 4.7 and GPT-5.5.

**Best reference says:** The primary source introduces the model and reports an 84% score on the Online-Mind2Web benchmark.

**Key qualification:** The metrics are self-reported and lack accompanying baseline scores for Opus 4.7 and GPT-5.5, statistical significance parameters, or verification of identical conditions.

**Delta:** missing_context — While Anthropic asserts a 'meaningful jump' on the benchmark, the public announcement omits the baseline scores of Opus 4.7 and GPT-5.5, meaning the size of the jump is mathematically unquantifiable. Furthermore, evaluations on live-web benchmarks inherently lack perfectly standardized execution conditions due to the dynamic nature of the web, and the model's documented 'evaluation awareness' introduces caveats about benchmark performance vs. real-world utility.

**Final verdict:** missing_context

**Defensible rewrite:** According to self-reported internal testing by Anthropic, Claude Opus 4.8 achieved an 84% score on the Online-Mind2Web browser-agent benchmark, which the company states is an improvement over its tests of Opus 4.7 and GPT-5.5, though specific baseline scores, statistical significance data, and independent third-party verifications are not publicly documented.

### Claim-Level Contrast References

- Introducing Claude Opus 4.8 (official_doc, authority 100/100): https://www.anthropic.com/news/claude-opus-4-8. The official product launch announcement containing the source quote.

**Reference snippets / mismatches:**
- The primary source introduces the model and reports an 84% score on the Online-Mind2Web benchmark. (Introducing Claude Opus 4.8, supports, https://www.anthropic.com/news/claude-opus-4-8). The metrics are self-reported and lack accompanying baseline scores for Opus 4.7 and GPT-5.5, statistical significance parameters, or verification of identical conditions.

**Computed checks:**
- Claude Opus 4.8 scored 84% on the Online-Mind2Web benchmark.
- Claude Opus 4.7 score on Online-Mind2Web is unknown and missing from the release documentation.
- GPT-5.5 score on Online-Mind2Web is unknown and missing from the release documentation.
- Other frameworks on leaderboards achieve up to 97.0% (Browser Use Cloud) and 93.0% (GPT-5.4 Native Computer Use).

**Gemini-discovered supporting sources:**
- Claude Opus 4.8 is the strongest computer-use and browser-agent model we’ve tested, scoring 84% on Online-Mind2Web, which is a meaningful jump over both Opus 4.7 and GPT-5.5. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Primary official announcement establishing the source of the 84% benchmark claim and the compared models.
- A computer-use vendor reported 84% on Online-Mind2Web, a jump over both Opus 4.7 and GPT-5.5. ([Anthropic's Claude Opus 4.8 is here with 3X cheaper fast mode and near-Mythos level alignment | VentureBeat](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFFNxxR7iiYegoiOvK6vo5oGhdKOnVaIhpmHtFvqKiVNASLWP9CL7mFxmHV_mMuSrCsjQvaI9R5fhDffteB9RFfTOOelVZiEm22O4eQKeWPb4g65_TBCeD6aJAPYpInzYT-KgJyCCNPlrw617msLGlM_SWbHrD-bdgeUyJ_oHqv3OwhoLo-7-SIzmTbcEwoLZZkbLnN3nSv7hUGDxZXxLRKvY-bCJgfR8fCX8eTDG5NUkWxCNHK)). Relevance: Corroborates tech industry reporting of the self-reported 84% figure.

**Gemini-discovered caveat / counter sources:**
- Browser Use Cloud (bu-max), 97.0%. GPT-5.4 Native Computer Use, 93.0%. ([AI Agent Benchmark Leaderboards: Browser, Coding & Computer Use | Steel.dev](https://steel.dev)). Relevance: Shows that other agentic frameworks and setups achieve higher browser-use and computer-use benchmark scores than 84%.
- Because the model launched the same day this was written, no independent third-party evaluations were available yet. Treat these as vendor-reported results until labs like Artificial Analysis or Vals AI publish their own. ([Claude Opus 4.8: Benchmarks, Price & Local AI Reality - ModemGuides](https://modemguides.com)). Relevance: Points out that the reported metrics lack independent, peer-reviewed, or third-party validation at launch.

**Missing context:**
- The specific baseline scores achieved by Claude Opus 4.7 and GPT-5.5 on the Online-Mind2Web benchmark were not disclosed, preventing any mathematical calculation of the absolute or relative improvement.
- Online-Mind2Web is evaluated on live, dynamic websites which undergo constant, real-time changes. Consequently, identical execution environments and testing conditions cannot be guaranteed for models evaluated at different times.
- Anthropic did not publish statistical significance metrics, sample sizes, standard errors, or p-values to prove the performance gap represents a mathematically robust improvement.
- The Claude Opus 4.8 System Card highlights that the model displays 'evaluation awareness,' actively reasoning about how its outputs will be graded, which introduces a potential risk of inflated benchmark performance.


## claim_5: overstated

**Confidence:** high

**Original:** Claude Code with Opus 4.8 can now carry out codebase-scale migrations across hundreds of thousands of lines of code from kickoff to merge, with the existing test suite as its bar.

**Stretch Score:** 45/100

**Why:** The claim overstates the autonomy and completeness of the migration process. While Anthropic showcases a 750,000-line migration of the Bun runtime from Zig to Rust as its flagship example, this project was not fully autonomous: it relied heavily on a pre-prepared codebase structure and a detailed, hand-crafted 300-rule translation guide authored by a human developer. Furthermore, the migration only achieved a 99.8% test pass rate out of the box (requiring human intervention to address the remaining failures), and the resulting code suffered from critical safety regressions, including failing basic Rust Miri checks and introducing Undefined Behavior (UB) in safe Rust. The underlying feature (Dynamic Workflows) is also only in 'Research Preview' and runs on unstable APIs.

**Defensible rewrite:** Using dynamic workflows (currently in Research Preview), Claude Code with Opus 4.8 can assist in large-scale codebase migrations of hundreds of thousands of lines of code, though the process requires comprehensive human-authored porting rules and manual intervention to resolve remaining test failures and code safety issues.

**Claim timing:**
- Total / Verifier / Contradiction / Numeric / Aggregator / Contrast: 108.11s / 29.29s / 23.42s / 16.15s / 33.23s / 0ms

### Agent Steps

<details><summary>Grounded Verifier: Anthropic's official announcement for Claude Opus 4.8 and Claude Code's 'dynamic workflows' asserts that the tool can execute codebase-scale migrations across hundreds of thousands of lines of code. The primary real-world case study supporting this claim is the migration of the Bun runtime from Zig to Rust, spanning roughly 750,000 lines of code and taking 11 days with a 99.8% test pass rate. However, this success does not fully satisfy the audit question's criteria of being completely end-to-end without manual human fixing across multiple complex, heterogeneous codebases. The Bun migration was heavily guided by a human-designed 300-rule porting guide, only 99.8% of the tests passed (meaning manual intervention or further work was required for completeness), and it represents a single, highly-focused codebase rather than multiple heterogeneous ones.</summary>

**Duration:** 29.29s

**Supporting evidence:**
- For example, Claude Code with Opus 4.8 can now carry out codebase-scale migrations across hundreds of thousands of lines of code from kickoff to merge, with the existing test suite as its bar. You can read more about dynamic workflows—available in Claude Code for Enterprise, Team, and Max plans—in this post. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Directly contains the claim text regarding Claude Code with Opus 4.8 executing codebase-scale migrations across hundreds of thousands of lines of code from kickoff to merge.
- An example of what dynamic workflows can unlock at scale is the recent rewrite of Bun. Jarred Sumner used dynamic workflows to port Bun from Zig to Rust with 99.8% of the existing test suite passing, roughly 750,000 lines of Rust, and eleven days from first commit to merge. One workflow mapped the right Rust lifetime for every struct field in the Zig codebase. The next wrote every .rs file as a behavior-identical port of its .zig counterpart, hundreds of agents working in parallel with two reviewers on each file. A fix loop then drove the build and test suite until both ran clean. ([Introducing dynamic workflows in Claude Code](https://claude.com/blog/introducing-dynamic-workflows-in-claude-code)). Relevance: Provides the exact details of the key codebase migration case study, showing that it completed a port of 750,000 lines with 99.8% of the test suite passing over 11 days.

**Missing context:**
- The migration of Bun from Zig to Rust relied on a human-defined porting guide comprising roughly 300 rules, rather than operating entirely autonomously without human instruction.
- Only 99.8% of the test suite passed initially, indicating that 100% test completion was not fully achieved without some unresolved failures or subsequent human intervention.
- The capability has only been highlighted in a single large-scale migration (the Bun runtime) and has not yet been demonstrated to succeed autonomously across 'multiple complex, heterogeneous codebases' as asked in the audit question.

**Computed checks:**
- 750,000 lines of Rust ported during the Bun codebase migration.
- 99.8% of the existing test suite passing upon migration completion.
- 11 days from the first commit to merge.
- 300 rules included in the manual human-authored porting guide for translating Zig to Rust.

</details>

<details><summary>Contradiction Finder: While Anthropic claims that Claude Code with Opus 4.8 can autonomously carry out codebase-scale migrations across hundreds of thousands of lines of code, real-world evidence and official documentation reveal several critical caveats. First, the 'Dynamic Workflows' feature is only in 'Research Preview' and runs on unstable APIs. Second, in its landmark showcase (porting Bun's ~750,000 lines of code from Zig to Rust in 11 days), the process was far from fully automated or completely hands-off. It required extensive human preparation, including a custom-written porting guide with roughly 300 rules mapping Zig to Rust idioms, and a codebase already pre-structured with 1-to-1 smart pointer mappings. Third, the resulting code failed basic runtime safety checks (such as Miri checks) and allowed for Undefined Behavior (UB) in safe Rust. Fourth, the migration only passed 99.8% of the test suite rather than reaching a flawless, unassisted merge, and it generated massive token consumption costs.</summary>

**Duration:** 23.42s

**Supporting evidence:**
- For example, Claude Code with Opus 4.8 can now carry out codebase-scale migrations across hundreds of thousands of lines of code from kickoff to merge, with the existing test suite as its bar. You can read more about dynamic workflows—available in Claude Code for Enterprise, Team, and Max plans—in this post. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: States the primary claim that Claude Code with Opus 4.8 can execute massive codebase-scale migrations.
- One early example: Jarred Sumner used dynamic workflows to port Bun from Zig to Rust. Roughly 750,000 lines, 11 days from first commit to merge, 99.8% of the test suite passing. ([Introducing dynamic workflows in Claude Code](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Provides the primary case study used to justify the claim of codebase-scale migrations.

**Contradictions / narrowing evidence:**
- This codebase fails even the most basic miri checks, allows for UB in safe rust ([This codebase fails even the most basic miri checks, allows for UB in safe rust · Issue #30719 · oven-sh/bun - GitHub](https://github.com/oven-sh/bun/issues/30719)). Relevance: Demonstrates that the automated, AI-driven migration of Bun resulted in code that violated core safety guarantees, meaning substantial human expert oversight and manual fixing are still required.
- When announcements say that rewrite took 1 week, I wonder how much time went into preparing this file with very detailed instructions on mapping Zig to Rust idioms... On top of that, if you look at 'Pointers & ownership' and 'Collections' sections, the Bun codebase is already prepared, using internal smart pointer types that map 1-to-1 to Rust equivalents ([Rewrite Bun in Rust has been merged | Hacker News](https://news.ycombinator.com/item?id=47055740)). Relevance: Highlights that the migration was not fully autonomous; it relied heavily on pre-existing architectural alignments and a meticulously structured, hand-crafted translation guide.

**Missing context:**
- Dynamic Workflows is currently a Research Preview feature with unstable APIs, presenting high operational and breakage risks for enterprise teams.
- The codebase-scale migration of Bun did not achieve a 100% pass rate out of the box, stopping at 99.8% of the test suite passing.
- Dynamic Workflows require spawning dozens to hundreds of parallel subagents over hours, which leads to massive token consumption and requires substantial, manual financial budgeting.
- Large-scale migrations are highly dependent on the initial preparation of custom-written porting guides and architectural pointer alignments constructed by human engineers.

**Computed checks:**
- 750000 lines of Rust code ported in Bun migration
- 11 days from first commit to merge for the Bun port
- 99.8% of the test suite passed after the migration, not 100%
- 300 rules in the human-prepared Zig-to-Rust porting guide

</details>

<details><summary>Numeric Calibrator: The claim asserts a capability that Claude Code with Opus 4.8 can carry out codebase-scale migrations across hundreds of thousands of lines of code. However, the document lacks empirical data, success rates, or case study details to verify if these migrations have successfully run end-to-end across multiple complex, heterogeneous codebases without requiring manual human fixing of tests or code.</summary>

**Duration:** 16.15s

**Supporting evidence:**
- For example, Claude Code with Opus 4.8 can now carry out codebase-scale migrations across hundreds of thousands of lines of code from kickoff to merge, with the existing test suite as its bar. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Direct source text stating the capability of migrating hundreds of thousands of lines of code.
- Source returned by Gemini grounding metadata. ([anthropic.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQGBRhdegtP3xTKLuJQQ12bEmgardHQbg_04qXDrC0h01PYqfmpPmdWp0DjyOqxxWZBGZd1HWtgDn1EZmSP7Cz1itFke-AlVRLNAugL2CfV3zOiwk2gL7EGsgaKhlnUa0Wemfmhp)). Relevance: Grounding source used during specialist audit.

**Missing context:**
- Empirical case studies or verification data showing actual completed migrations of this scale.
- Statistical success rates indicating whether manual code or test fixing was required during the migrations.
- Evidence or definitions regarding the complexity or heterogeneous nature of the codebases tested.

**Computed checks:**
- The claim specifies 'hundreds of thousands' of lines of code, which semantically implies a minimum scale of 200,000 lines.
- The audit question queries a threshold of 'over 100,000 lines'. The claim's implied scale (>= 200,000) represents a 100% relative increase (2x scaling factor) over the audit question's minimum threshold.
- There are 0 specific numbers, percentages, or denominators provided in the text regarding the success rate or manual intervention rate of these migrations, leaving the audit question's strict criteria ('successfully completed... without requiring manual human fixing') mathematically unsubstantiated by the document.

</details>

<details><summary>claim-aggregator: Combined specialist outputs into final verdict `overstated` with `high` confidence.</summary>

**Duration:** 33.23s

**Supporting evidence:**
- For example, Claude Code with Opus 4.8 can now carry out codebase-scale migrations across hundreds of thousands of lines of code from kickoff to merge, with the existing test suite as its bar. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Direct source text asserting the capability to perform codebase-scale migrations.
- Jarred Sumner used dynamic workflows to port Bun from Zig to Rust with 99.8% of the existing test suite passing, roughly 750,000 lines of Rust, and eleven days from first commit to merge. ([Introducing dynamic workflows in Claude Code](https://claude.com/blog/introducing-dynamic-workflows-in-claude-code)). Relevance: Provides the specifics of the Bun migration used to justify the claim.

**Contradictions / narrowing evidence:**
- When announcements say that rewrite took 1 week, I wonder how much time went into preparing this file with very detailed instructions on mapping Zig to Rust idioms... On top of that, if you look at 'Pointers & ownership' and 'Collections' sections, the Bun codebase is already prepared, using internal smart pointer types that map 1-to-1 to Rust equivalents ([Rewrite Bun in Rust has been merged | Hacker News](https://news.ycombinator.com/item?id=47055740)). Relevance: Reveals that substantial human-prepared engineering rules and architectural alignment were required before the AI could execute the migration.
- This codebase fails even the most basic miri checks, allows for UB in safe rust ([This codebase fails even the most basic miri checks, allows for UB in safe rust · Issue #30719 · oven-sh/bun - GitHub](https://github.com/oven-sh/bun/issues/30719)). Relevance: Shows that the automated migration did not yield a clean, safe production-ready codebase, as it introduced serious undefined behavior and failed standard Rust memory safety checks.

**Missing context:**
- The flagship migration of Bun was heavily reliant on a human-defined 300-rule translation guide.
- Only 99.8% of the test suite passed, meaning manual intervention was required to resolve the remaining failures.
- The feature 'Dynamic Workflows' is in Research Preview and uses unstable APIs, meaning it is not yet stable for general production use.
- The resulting code from the automated migration had serious memory safety and compilation issues (like Miri check failures) that require expert human resolution.

**Computed checks:**
- 750,000 lines of Rust code migrated in the flagship Bun case study.
- 99.8% of the existing test suite passed, which falls short of a 100% clean automation without human fixing.
- 11 days from first commit to merge for the Bun port.
- 300 rules in the human-prepared Zig-to-Rust guide used to direct the model.

</details>

### Evidence Contrast

**Claim says:** Claude Code with Opus 4.8 can now carry out codebase-scale migrations across hundreds of thousands of lines of code from kickoff to merge, with the existing test suite as its bar.

**Best reference says:** Details that while a 750,000-line codebase was ported, it resulted in a 99.8% test pass rate rather than a 100% clean merge, indicating manual debugging/fixing was required.

**Key qualification:** It highlights the flagship case study is not completely autonomous.

**Delta:** narrower_than_claim — The actual capability is a research-grade tool that assists human developers by automating parallel structural translations under strict human guidance, rather than an autonomous 'kickoff to merge' system that safely guarantees compatibility with the existing test suite out of the box.

**Final verdict:** overstated

**Defensible rewrite:** Using dynamic workflows (currently in Research Preview), Claude Code with Opus 4.8 can assist in translating large codebases of hundreds of thousands of lines of code, though the process requires detailed human-authored translation rules and manual intervention to fix safety bugs and outstanding test failures.

### Claim-Level Contrast References

- Introducing Claude Opus 4.8 - Anthropic (official_doc, authority 95/100): https://www.anthropic.com/news/claude-opus-4-8. It contains the original announcement and specific claim text.
- Introducing dynamic workflows in Claude Code (official_doc, authority 95/100): https://claude.com/blog/introducing-dynamic-workflows-in-claude-code. It contains the technical details of the Bun runtime migration case study.

**Reference snippets / mismatches:**
- Details that while a 750,000-line codebase was ported, it resulted in a 99.8% test pass rate rather than a 100% clean merge, indicating manual debugging/fixing was required. (Introducing dynamic workflows in Claude Code, narrows, https://claude.com/blog/introducing-dynamic-workflows-in-claude-code). It highlights the flagship case study is not completely autonomous.
- Shows that the automated migration produced highly unstable and unsafe code that violates basic language guarantees, meaning substantial developer intervention is still necessary. (This codebase fails even the most basic miri checks, allows for UB in safe rust · Issue #30719 · oven-sh/bun - GitHub, contradicts, https://github.com/oven-sh/bun/issues/30719). Indicates safety/soundness limitations overlooked by the marketing claim.

**Computed checks:**
- 750,000 lines of Rust code migrated in the flagship Bun case study.
- 99.8% of the existing test suite passed, which falls short of a 100% clean automation without human fixing.
- 11 days from first commit to merge for the Bun port.
- 300 rules in the human-prepared Zig-to-Rust guide used to direct the model.

**Gemini-discovered supporting sources:**
- For example, Claude Code with Opus 4.8 can now carry out codebase-scale migrations across hundreds of thousands of lines of code from kickoff to merge, with the existing test suite as its bar. ([Introducing Claude Opus 4.8 - Anthropic](https://www.anthropic.com/news/claude-opus-4-8)). Relevance: Direct source text asserting the capability to perform codebase-scale migrations.
- Jarred Sumner used dynamic workflows to port Bun from Zig to Rust with 99.8% of the existing test suite passing, roughly 750,000 lines of Rust, and eleven days from first commit to merge. ([Introducing dynamic workflows in Claude Code](https://claude.com/blog/introducing-dynamic-workflows-in-claude-code)). Relevance: Provides the specifics of the Bun migration used to justify the claim.

**Gemini-discovered caveat / counter sources:**
- When announcements say that rewrite took 1 week, I wonder how much time went into preparing this file with very detailed instructions on mapping Zig to Rust idioms... On top of that, if you look at 'Pointers & ownership' and 'Collections' sections, the Bun codebase is already prepared, using internal smart pointer types that map 1-to-1 to Rust equivalents ([Rewrite Bun in Rust has been merged | Hacker News](https://news.ycombinator.com/item?id=47055740)). Relevance: Reveals that substantial human-prepared engineering rules and architectural alignment were required before the AI could execute the migration.
- This codebase fails even the most basic miri checks, allows for UB in safe rust ([This codebase fails even the most basic miri checks, allows for UB in safe rust · Issue #30719 · oven-sh/bun - GitHub](https://github.com/oven-sh/bun/issues/30719)). Relevance: Shows that the automated migration did not yield a clean, safe production-ready codebase, as it introduced serious undefined behavior and failed standard Rust memory safety checks.

**Missing context:**
- The flagship migration of Bun was heavily reliant on a human-defined 300-rule translation guide.
- Only 99.8% of the test suite passed, meaning manual intervention was required to resolve the remaining failures.
- The feature 'Dynamic Workflows' is in Research Preview and uses unstable APIs, meaning it is not yet stable for general production use.
- The resulting code from the automated migration had serious memory safety and compilation issues (like Miri check failures) that require expert human resolution.

