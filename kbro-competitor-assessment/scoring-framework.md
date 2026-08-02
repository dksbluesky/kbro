# kbro competitor-assessment scoring framework

Use this framework for every competitor feasibility report. The score measures execution feasibility for a defined project scope and delivery role at the review date. It is not a bid-win probability, investment return, or permanent limit on kbro's capabilities.

## Standard score anchors

Report one of these anchors for each materially different scenario:

| Score | Label | Meaning |
|---|---|---|
| 100 | Fully executable | kbro has verified delivery evidence, team, qualifications, security, SLA, commercial capacity, and contractual control to execute independently at the stated scope. |
| 80 | Executable | Core capability is mature. Limited gaps can be closed within normal project planning or by partners already controlled by kbro. The scenario can enter formal planning. |
| 60 | Conditionally executable | Important capabilities match, but execution still depends on material partners, a POC, qualifications, acceptance evidence, or clarified responsibility boundaries. |
| 30 | Not executable under the original scope | kbro has useful underlying capability but multiple critical gaps prevent it from taking the original end-to-end or prime-contract scope. Limit participation to a controlled work package. |
| 0 | Do not pursue | Core capability is materially mismatched, or qualification, technology, cost, schedule, liability, or delivery risk cannot be closed reasonably. |

Use the anchors to avoid false precision. Do not invent intermediate headline scores. A weighted raw score may be shown in a calculation note, but the executive dashboard must use the mapped anchor.

## Weighted dimensions

Score each dimension with one of the same anchors: 0, 30, 60, 80, or 100.

| Dimension | Weight | Evidence focus |
|---|---:|---|
| Core technical fit | 25% | Network, optical, data center, HPC, cloud, AI, AIoT, platform, and solution-specific technology required by the scenario. |
| Engineering and integration | 20% | Site survey, design, deployment, device integration, testing, commissioning, and multi-vendor coordination. |
| Performance evidence and acceptance | 15% | Comparable references, measurable KPIs, POC results, test reports, customer acceptance, and permission to cite results. |
| Partners and domain capability | 15% | Named partners, responsibility matrix, domain experts, supply assurance, and kbro's control over partner delivery. |
| Operations, security, and SLA | 15% | NOC, monitoring, incident response, spares, recovery, cybersecurity, privacy, resilience, and service commitments. |
| Commercial and qualification capacity | 10% | Bid qualifications, licenses, insurance, contractual responsibility, staffing availability, cash-flow exposure, and referenceability. |

Calculate:

`weighted raw score = sum(dimension score x dimension weight)`

Map the weighted raw score to the reporting anchor:

| Weighted raw score | Reporting anchor |
|---:|---:|
| 90-100 | 100 |
| 70-89 | 80 |
| 45-69 | 60 |
| 15-44 | 30 |
| 0-14 | 0 |

If a critical gating condition makes the mapped anchor misleading, lower the final anchor and explain the gate. Never raise an anchor above the calculated mapping without new verified evidence.

## Evidence rules

- Award score only for evidence available at the review date.
- Treat "not documented" as an evidence gap, not proof that kbro cannot perform the work.
- Do not award capability credit for an unsupported claim.
- Separate kbro-owned capability from partner-dependent capability.
- Do not treat registered capital, total headcount, subscriber count, or general company scale as proof of available project cash, qualified staffing, delivery capacity, or bid eligibility.
- Treat competitor presentations as claims or demonstrations, not as kbro evidence or formal customer requirements unless supported by an RFP, contract, specification, or acceptance record.
- Label named target companies as potential accounts inferred from public operating scenarios, not confirmed buyers.

## Scenario and decision presentation

Split the assessment whenever scope or delivery responsibility changes materially. Use scenario names appropriate to the source; common patterns include:

- complete solution as prime contractor;
- alliance member or subcontractor with a controlled work package;
- formal regional AIoT deployment;
- bounded single-site POC with measurable KPIs.

For each scenario, show:

1. reporting anchor and label;
2. recommended kbro role;
3. strongest evidence supporting the score;
4. critical Cons or evidence gaps;
5. named partner roles and responsibility boundaries;
6. proceed, explore, hold, or no-bid recommendation;
7. current-to-target anchor and exact conditions required to improve;
8. high, medium, or low confidence with a short reason.

The executive conclusion must identify the recommended entry scenario. Prefer a bounded, measurable POC when it is the highest-feasibility path and do not describe a 60-point scenario as independently executable.
