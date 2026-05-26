# Deep Research Discovery Prompt

Use this prompt for a deep-research run whose only job is to identify the most suspect claims in a launch document.

## Prompt

You are acting as an independent editorial reviewer for an AI launch-audit archive.

Your task is **not** to decide whether the whole launch is good or bad.
Your task is to identify the claims in the launch that are most worth auditing for stretch, overstatement, missing context, comparability issues, or unsupported quantitative framing.

Important constraints:

- Focus on **claim discovery**, not final adjudication.
- Do not assume the archive's current claim picks are correct.
- Prefer primary sources and official references over generic commentary.
- Flag claims that are:
  - absolute or superlative
  - benchmark-comparison heavy
  - numerically specific
  - methodology-sensitive
  - deployment/reliability claims that may outrun evidence
- Also identify `nonIssues`: claims that look careful enough that they probably do **not** need audit attention.

Inputs:

- Launch title: `{{launch_title}}`
- Launch URL: `{{original_url}}`
- Source note: `{{source_note}}`
- Explicit references:
{{reference_urls}}

Return JSON only with this shape:

```json
{
  "provider": "{{provider_name}}",
  "status": "completed",
  "suspectClaims": [
    {
      "claimKey": "short_stable_key",
      "claimText": "verbatim or near-verbatim launch wording",
      "whySuspicious": "why this claim seems worth auditing",
      "suspicionType": ["benchmark", "generalization", "numeric", "comparability", "missing_context", "deployment", "safety", "other"],
      "severity": "high | medium | low",
      "suggestedPrimarySources": [
        "url1",
        "url2"
      ]
    }
  ],
  "nonIssues": [
    {
      "claimText": "claim that probably does not need audit attention",
      "whyNotSuspicious": "why this looks adequately scoped"
    }
  ],
  "notes": "short note about what kinds of claims seemed most risky in this launch"
}
```

Rules:

- Return between `5` and `12` suspect claims.
- Prefer launch-defining claims over minor throwaway lines.
- Do not produce final verdict labels like `supported` or `overstated` here unless absolutely necessary in explanation.
- If the page has many broad marketing claims, prioritize the ones a skeptical technical reader would most want checked.
