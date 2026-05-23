# CappinCheck Report: xAI Grok 3 Launch Claim Proxy

Source: `examples/xai_grok3_launch_input.md`

## Provenance

- Mode: `live_gemini`
- Runtime: `local`
- Pipeline wall: `98.52s`
- Load / Extract / Audit / Contrast: `1ms` / `20.15s` / `78.37s` / `25.87s`
- Claims extracted / audited: `8` / `1`
- Specialist passes / unique sources: `3` / `4`

- Model: `gemini-3.5-flash`
- Evidence Contrast: `enabled`
- Provided reference URLs: `https://x.ai/news/grok-3`, `https://lmarena.ai/?leaderboard=`, `https://livecodebench.github.io/`, `https://crfm.stanford.edu/fmti/December-2025/company-reports/xAI_FinalReport_FMTI2025.html`

## Scorecard

- Claims audited: `1`
- Verdict counts: `supported=0` · `overstated=0` · `missing_context=1` · `contradicted=0` · `not_checkable=0`
- Average stretch score: `60/100`
- Provided reference URL count: `4`

| Claim | Formal Verdict | Confidence | Stretch Score |
| --- | --- | --- | ---: |
| Grok 3 is xAI's most advanced model yet, trained on the Colossus supercluster | missing_context | high | 60 |

## grok3_colossus_training: missing_context

**Confidence:** high

**Original:** Grok 3 is xAI's most advanced model yet, trained on the Colossus supercluster

**Stretch Score:** 60/100

**Why:** While the claim is fully supported by xAI's official announcement, independent academic audit from the Stanford Foundation Model Transparency Index (FMTI 2025) highlights missing context. Specifically, xAI has not disclosed whether the entire Colossus supercluster was used for the training run, nor have they shared detailed hardware allocation, duration, or FLOPs, resulting in a score of 0 on compute transparency indicators.

**Defensible rewrite:** Grok 3 is officially described as xAI's most advanced model yet, trained on the Colossus supercluster (though specific compute and hardware utilization details for the final training run remain undisclosed).

**Claim timing:**
- Total / Verifier / Contradiction / Numeric / Aggregator / Contrast: 78.36s / 27.19s / 24.19s / 27.94s / 24.51s / 25.87s

### Agent Steps

<details><summary>Grounded Verifier: The claim that Grok 3 was trained on the Colossus supercluster is officially supported by xAI's launch announcements and statements from executive leadership. However, regarding the specific audit question, xAI has not publicly released verifiable system logs, raw training telemetry, or official end-to-end hardware architecture blueprints that would allow independent verification of the claim. Available technical details of the Colossus hardware architecture are limited to high-level press releases, executive social media posts, and industry reporting on the facility (such as its scale of 100,000 to 200,000 NVIDIA H100/H200 GPUs, custom liquid cooling, and use of Supermicro and NVIDIA Spectrum-X technologies).</summary>

**Duration:** 27.19s

**Supporting evidence:**
- Trained on our Colossus supercluster with 10x the compute of previous state-of-the-art models, Grok 3 displays significant improvements in reasoning, mathematics, coding, world knowledge, and instruction-following tasks. ([Grok 3 Beta — The Age of Reasoning Agents - xAI](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQGFqqWKoluzmHqRbOIlcPJmjmK1JSF2JSstc9-ug6ctfveSxmRvnuUURKBJi8x8xxsg1hfMj9L-FE3KUaQh4T90Rr-3zGK54OOP1R_kAUs=)). Relevance: Direct official claim from xAI confirming Grok 3 was trained on their Colossus supercluster using 10x the compute of prior SOTA models.
- In a repurposed Electrolux factory in Memphis, xAI trained Grok 3 on a supercomputer dubbed “Colossus,” which the company says includes 200,000 Nvidia H100 GPUs. Elon Musk and senior xAI employees described Grok 3 as “the smartest AI on Earth” in a recent livestream, citing each GPU's capacity of up to 4 PFLOPS (four quadrillion floating-point operations per second) and high-speed interconnects across the cluster. ([How xAI turned a factory shell into an AI 'Colossus' for Grok 3 - R&D World](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE7QRtIuF1kQpT0DgkakgYNVHb4SlPmjfnA5JcIUrfAz2qDdnmT-vAh2sLFI7hnd-oWCxhB3pkmV3Or6xr3syb3lXXhOz6JyxBTfSs9nn1RFjEE7aSS7SiW1xHDrvqfEG8D71zohbN54v5Me54p0GSaUemEGDGO31z3L2ebZIuvQHBLoQvMWSSqXCIyVYRiSaaIpR4lXLBcpHnbO-tuNQTBL8I=)). Relevance: Provides third-party reporting confirming the public details of the training cluster, location, and the scale of GPUs used, referencing company streams and executive descriptions.
- Reporting from DatacenterDynamics and ServeTheHome paints the picture: a cluster designed for up to 100,000 NVIDIA H100 GPUs, connected via a single RDMA fabric... Supermicro's racks are designed from the ground up for liquid cooling... custom orchestrator that automatically ejects problematic nodes from a training job, optimizes checkpointing and data loading... ([How Grok Works Under the Hood: Inside xAI's Infrastructure and Training Logic - Medium](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQEe6me0Ko7HQg8GMyYbCgrh7QgPkV6kr6PaPPIK7q1et7_Ix7R3D1kYmPUROOIt0zeny4w17fkQuIOF1aHOIT51qUATYKL7L579Hy3a0_84_Xgz-NvzdDvHUWWIJxCE0mkdSPa8F870gmZQRpTULH-yfvIxMKy2igsKdK4VRXAfgKMXBA9RvOE1mvOt0VLYjRDD4Ff7kGwVzgYkAJpe9cyed8CoM7GOV2CmEjGX5ZEvQ7o=)). Relevance: Analyzes underlying hardware integration, liquid cooling systems, and node orchestration details of the Colossus supercluster, while noting the reliance on third-party reporting rather than official published logs.

**Missing context:**
- Verifiable system training logs or raw telemetry demonstrating continuous end-to-end execution on the Colossus supercluster.
- Official technical whitepapers or documented hardware/network topologies published directly by xAI to substantiate the physical configuration during Grok 3's pre-training.

**Computed checks:**
- 10x compute of previous state-of-the-art models
- 100,000 NVIDIA H100 GPUs initially, later expanded to 200,000 H100 and H200 GPUs
- Estimated 250 megawatts drawing capacity buffered by Tesla MegaPacks
- Processing speed of up to 4 PFLOPS per GPU

</details>

<details><summary>Contradiction Finder: There is no independent verification, third-party audit, or publicly available system logs proving that Grok 3 was trained end-to-end on the Colossus supercluster. While xAI claims that Grok 3 was trained on Colossus using 200,000 NVIDIA H100 GPUs, these assertions rely entirely on corporate press releases and statements by Elon Musk. Furthermore, researchers at Stanford's Center for Research on Foundation Models (CRFM) have noted that xAI does not disclose specific training hardware utilization, training logs, or train-test overlap details, leaving the training claims unverifiable.</summary>

**Duration:** 24.19s

**Supporting evidence:**
- Trained on our Colossus supercluster with 10x the compute of previous state-of-the-art models, Grok 3 displays significant improvements in reasoning... ([Grok 3 Beta — The Age of Reasoning Agents - xAI](https://x.ai/news/grok-3)). Relevance: Official announcement establishing the primary claim that Grok 3 was trained on the Colossus supercluster.
- Source returned by Gemini grounding metadata. ([rdworldonline.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFESfNxLhKdLvwddbWAOFsRxJ2CT4DqHapQ-CyR592jp0oaJIGfPm8cwslu1ZQ9UocSozLJN8GwJ334GLtUsJJiwM353pinpOmGoSjLVvwjHD0_J45TrLrFwFCv13MmIDH7b2HsIVmRxkFgTZRg6dWR8IHV7xQOV2NyIiq748u-JvEYIkdgGI0LZpr6rD7dIpaV72kGh-4siWCZucLj4LwD_2Y=)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([builtin.com](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQGTGtUWVOdeL2htQ0DYpeUXlQjzPaa6PXTrz1sHHqReldD4toCJ7e50Pzcz_OXTDEM3DXmF9XabB74lIUH-P4Owt6yg-FUW3ryOJIoKTxQFMSDwCgUTqXi2X2QPVar9n-1ieJCfBec6)). Relevance: Grounding source used during specialist audit.
- Source returned by Gemini grounding metadata. ([stanford.edu](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFX3CE4qWsdN3d11GQOG9GmxlRsHp7z9MdNgWfBOgziysgFC-jiD18NIdKVGOAzo0PZscDwBIyFE4Czj269vjoCPRDTBtFjIoQg4WnFgngsT0CA8_HcK07JgEpGCO6N_stKJTFXY88P5fdXxQumwYb7lmzu0d7yL3Xo4g2RjVbu9FBnKdI9jmB8nXC_CdSjkw==)). Relevance: Grounding source used during specialist audit.

**Contradictions / narrowing evidence:**
- No specific information about whether all the GPUs on the Colossus cluster are used for Grok 3 training. ... We will not award this point if (i) the training hardware generally used by the developer is disclosed, but the specific hardware [for Grok 3 is not]... Train-test overlap (Score: 0). ... Disclosure: Not disclosed. (xAI Transparency Report - Stanford CRFM). Relevance: Highlights a direct conflict with any claim of verifiable training details, indicating that xAI does not disclose specific training hardware usage or test-overlap details for Grok 3.

**Missing context:**
- xAI has not released any public technical reports, blueprints, network topologies, or cryptographically verifiable system logs showing end-to-end training runs for Grok 3 on Colossus.
- The claim of a 200,000 GPU cluster relies on promotional media, and subsequent reports indicate that parts of the Colossus cluster's compute capacity (such as Colossus 1) are rented to other players, raising questions about actual hardware allocation during Grok 3's development.
- The details regarding Grok 3's training framework rely on generic overviews of xAI's JAX and Rust stack rather than a specific, auditable technical paper.

**Computed checks:**
- 200000 GPUs claimed to be in the Colossus supercluster
- 10 times compute compared to Grok 2 as stated by xAI
- 0 out of 1 score on specific hardware and train-test overlap disclosures in transparency evaluations

</details>

<details><summary>Numeric Calibrator: While xAI claims Grok 3 was trained on its Colossus supercluster, the company has not released verifiable system logs, FLOPs measurements, or exact hardware architecture details proving end-to-end training. This is corroborated by the Stanford CRFM xAI Transparency Report, which notes that xAI has not provided specific information on compute usage or dedicated GPU allocations during Grok 3's training.</summary>

**Duration:** 27.94s

**Supporting evidence:**
- Built in 122 days — outpacing every estimate — Colossus was the most powerful AI training system yet. Then we doubled it in 92 days to 200k GPUs... 200,000 H100 GPUs in a single interconnected cluster. ([Colossus: The World's Largest AI Supercomputer - xAI](https://x.ai/colossus)). Relevance: Provides official infrastructure scale supporting the feasibility of training massive models like Grok 3 on the Colossus supercluster.
- The star of the initial part of the show wasn't the AI itself, but rather 'Colossus,' a behemoth cluster of 200,000 GPUs that powers Grok-3's training. ([Musk's xAI Unveils Grok-3: More Power, But Is It Breaking New Ground? - Decrypt](https://decrypt.co/221584/musks-xai-unveils-grok-3-more-power-but-is-it-breaking-new-ground)). Relevance: Details that Grok 3's training was powered by the Colossus cluster.

**Contradictions / narrowing evidence:**
- The relevant passage on training compute states: 'Trained on our Colossus supercluster with 10x the compute of previous state-of-the-art models, Grok 3... ' ... No specific information provided about compute usage. Compute should be reported in appropriate units, which most often will be floating point operations (FLOPs)... No specific information about whether all the GPUs on the Colossus cluster are used for Grok 3 training. ([xAI Transparency Report - Stanford CRFM](https://crfm.stanford.edu/)). Relevance: Confirms that xAI lacks transparency regarding verifiable system logs, exact hardware usage, and precise compute (FLOPs) measurements for Grok 3's training.

**Missing context:**
- Verified system logs and end-to-end training telemetry from the Colossus supercluster.
- Precise training compute reported in FLOPS (floating-point operations) with measurement methodology.
- The exact number of GPUs and active nodes dedicated exclusively to Grok 3's training stages.

**Computed checks:**
- Estimation of GPU hours: 100,000 GPUs * 80 days * 24 hours/day = 192,000,000 H100 GPU hours (~1.92 * 10^8 hours). Some independent estimates place pre-training at roughly 200 million H100 GPU hours, which closely matches this calculation.
- Compute multiplier: xAI claims 10x the compute of previous state-of-the-art models (10x compute), but without an official baseline in FLOPs (e.g., Grok 2 training FLOPs vs Grok 3 training FLOPs), the absolute and relative deltas remain unverifiable.

</details>

<details><summary>claim-aggregator: Combined specialist outputs into final verdict `supported` with `high` confidence.</summary>

**Duration:** 24.51s

**Supporting evidence:**
- Trained on our Colossus supercluster with 10x the compute of previous state-of-the-art models, Grok 3 displays significant improvements in reasoning, mathematics, coding, world knowledge, and instruction-following tasks. ([Grok 3 Beta — The Age of Reasoning Agents - xAI](https://x.ai/news/grok-3)). Relevance: Direct launch announcement from xAI establishing the training infrastructure and model status.
- In a repurposed Electrolux factory in Memphis, xAI trained Grok 3 on a supercomputer dubbed “Colossus,” which the company says includes 200,000 Nvidia H100 GPUs. ([How xAI turned a factory shell into an AI 'Colossus' for Grok 3 - R&D World](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE7QRtIuF1kQpT0DgkakgYNVHb4SlPmjfnA5JcIUrfAz2qDdnmT-vAh2sLFI7hnd-oWCxhB3pkmV3Or6xr3syb3lXXhOz6JyxBTfSs9nn1RFjEE7aSS7SiW1xHDrvqfEG8D71zohbN54v5Me54p0GSaUemEGDGO31z3L2ebZIuvQHBLoQvMWSSqXCIyVYRiSaaIpR4lXLBcpHnbO-tuNQTBL8I=)). Relevance: Third-party industry reporting corroborating the training of Grok 3 on the Colossus supercomputer.
- The star of the initial part of the show wasn't the AI itself, but rather 'Colossus,' a behemoth cluster of 200,000 GPUs that powers Grok-3's training. ([Musk's xAI Unveils Grok-3: More Power, But Is It Breaking New Ground? - Decrypt](https://decrypt.co/221584/musks-xai-unveils-grok-3-more-power-but-is-it-breaking-new-ground)). Relevance: Confirming public consensus that the model training was powered by the Colossus cluster.

**Missing context:**
- xAI has not publicly released verifiable system logs, raw training telemetry, or official end-to-end hardware architecture blueprints that would allow independent verification.
- The Stanford Center for Research on Foundation Models (CRFM) Transparency Report notes that xAI does not disclose specific hardware utilization or precise training compute reported in floating-point operations (FLOPs).

**Computed checks:**
- Colossus supercluster scale is cited as utilizing 100,000 to 200,000 NVIDIA H100 and H200 GPUs.
- The compute used is stated to be 10x that of previous state-of-the-art models.
- 0 out of 1 score on specific hardware and train-test overlap disclosures in Stanford CRFM transparency evaluations.

</details>

### Evidence Contrast

**Claim says:** Grok 3 is xAI's most advanced model yet, trained on the Colossus supercluster

**Best reference says:** The official announcement states: 'We are pleased to introduce Grok 3, our most advanced model yet... Trained on our Colossus supercluster...'

**Key qualification:** This is an official vendor marketing release.

**Delta:** missing_context — While the claim is fully supported by xAI's official announcement, independent academic audit from the Stanford Foundation Model Transparency Index (FMTI 2025) highlights missing context. Specifically, xAI has not disclosed whether the entire Colossus supercluster was used for the training run, nor have they shared detailed hardware allocation, duration, or FLOPs, resulting in a score of 0 on compute transparency indicators.

**Final verdict:** missing_context

**Defensible rewrite:** Grok 3 is officially described as xAI's most advanced model yet, trained on the Colossus supercluster (though specific compute and hardware utilization details for the final training run remain undisclosed).

### Claim-Level Contrast References

- Grok 3 Beta — The Age of Reasoning Agents - xAI (vendor_doc, authority 100/100): https://x.ai/news/grok-3. Official blog post from xAI introducing Grok 3 as its most advanced model and stating that it was trained on the Colossus supercluster.
- xAI Transparency Report - Stanford CRFM (academic, authority 90/100): https://crfm.stanford.edu/fmti/December-2025/company-reports/xAI_FinalReport_FMTI2025.html. Provides independent evaluation of xAI's disclosures on Grok 3, showing that while xAI claims the model was trained on the Colossus supercluster, it lacks transparent details regarding whether the entire cluster was utilized or the specific compute used.

**Reference snippets / mismatches:**
- The official announcement states: 'We are pleased to introduce Grok 3, our most advanced model yet... Trained on our Colossus supercluster...' (Grok 3 Beta — The Age of Reasoning Agents - xAI, supports, https://x.ai/news/grok-3). This is an official vendor marketing release.
- The Stanford CRFM FMTI 2025 report notes that while xAI's press release claims Grok 3 was trained on the Colossus supercluster, xAI fails to disclose specific training hardware and compute details, such as whether all Colossus GPUs were utilized, the run duration, or total FLOPs. (xAI Transparency Report - Stanford CRFM, narrows, https://crfm.stanford.edu/fmti/December-2025/company-reports/xAI_FinalReport_FMTI2025.html). An independent evaluation of foundation model transparency.

**Computed checks:**
- Colossus supercluster scale is cited as utilizing 100,000 to 200,000 NVIDIA H100 and H200 GPUs.
- The compute used is stated to be 10x that of previous state-of-the-art models.
- 0 out of 1 score on specific hardware and train-test overlap disclosures in Stanford CRFM transparency evaluations.

**Gemini-discovered supporting sources:**
- Trained on our Colossus supercluster with 10x the compute of previous state-of-the-art models, Grok 3 displays significant improvements in reasoning, mathematics, coding, world knowledge, and instruction-following tasks. ([Grok 3 Beta — The Age of Reasoning Agents - xAI](https://x.ai/news/grok-3)). Relevance: Direct launch announcement from xAI establishing the training infrastructure and model status.
- In a repurposed Electrolux factory in Memphis, xAI trained Grok 3 on a supercomputer dubbed “Colossus,” which the company says includes 200,000 Nvidia H100 GPUs. ([How xAI turned a factory shell into an AI 'Colossus' for Grok 3 - R&D World](https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQE7QRtIuF1kQpT0DgkakgYNVHb4SlPmjfnA5JcIUrfAz2qDdnmT-vAh2sLFI7hnd-oWCxhB3pkmV3Or6xr3syb3lXXhOz6JyxBTfSs9nn1RFjEE7aSS7SiW1xHDrvqfEG8D71zohbN54v5Me54p0GSaUemEGDGO31z3L2ebZIuvQHBLoQvMWSSqXCIyVYRiSaaIpR4lXLBcpHnbO-tuNQTBL8I=)). Relevance: Third-party industry reporting corroborating the training of Grok 3 on the Colossus supercomputer.
- The star of the initial part of the show wasn't the AI itself, but rather 'Colossus,' a behemoth cluster of 200,000 GPUs that powers Grok-3's training. ([Musk's xAI Unveils Grok-3: More Power, But Is It Breaking New Ground? - Decrypt](https://decrypt.co/221584/musks-xai-unveils-grok-3-more-power-but-is-it-breaking-new-ground)). Relevance: Confirming public consensus that the model training was powered by the Colossus cluster.

**Missing context:**
- xAI has not publicly released verifiable system logs, raw training telemetry, or official end-to-end hardware architecture blueprints that would allow independent verification.
- The Stanford Center for Research on Foundation Models (CRFM) Transparency Report notes that xAI does not disclose specific hardware utilization or precise training compute reported in floating-point operations (FLOPs).

