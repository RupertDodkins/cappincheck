# Deep Research Adjudication Prompt

Use this prompt after discovery review has identified the claims worth checking.

## Prompt

You are acting as an independent editorial reviewer for an AI launch-audit archive.

Your task is to adjudicate a **specific set of already selected claims** from an AI launch.

This is not a generic summary task. For each claim, decide what a fair audit outcome should be given the launch and the cited evidence.

Important constraints:

- Work claim by claim.
- Prefer primary sources and explicit reference URLs.
- Distinguish carefully between:
  - `supported`
  - `overstated`
  - `missing_context`
  - `contradicted`
  - `not_checkable`
- A claim can be directionally true and still be `overstated` or `missing_context`.
- Preserve the strongest defensible meaning in the rewrite.

Inputs:

- Launch title: `{{launch_title}}`
- Launch URL: `{{original_url}}`
- Source note: `{{source_note}}`
- Explicit references:
{{reference_urls}}

- Claims to adjudicate:
{{selected_claims}}

Return JSON only with this shape:

```json
{
  "provider": "{{provider_name}}",
  "status": "completed",
  "claims": [
    {
      "claimKey": "same_key_from_discovery_or_review",
      "claimText": "claim wording being adjudicated",
      "expectedVerdict": "supported | overstated | missing_context | contradicted | not_checkable",
      "verdictRationale": "concise explanation grounded in evidence",
      "requiredCaveat": "most important caveat or qualifier",
      "rewriteMustContain": [
        "key phrase 1",
        "key phrase 2"
      ],
      "rewriteMustAvoid": [
        "too-strong phrase 1"
      ],
      "approvedPrimarySources": [
        "url1",
        "url2"
      ],
      "citationAdequacyNote": "what kind of citation proof would make this claim feel adequately substantiated"
    }
  ],
  "notes": "short note about the overall pattern of stretch or disclosure quality in this launch"
}
```

Rules:

- Do not invent certainty if the evidence packet is weak.
- If you think the claim is mostly okay but missing crucial setup, use `missing_context`.
- If the claim is broader or stronger than the sources support, use `overstated`.
- Rewrites should keep launch energy where possible while removing the unsupported stretch.
