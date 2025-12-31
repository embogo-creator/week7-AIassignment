Ethical AI Assignment

This repository contains an analysis of ethical issues in Artificial Intelligence, including theoretical concepts, real-world case studies, a bias audit using Python, and an ethical reflection.

Part 1: Theoretical Understanding (30%)
1. Short Answer Questions
Q1: Algorithmic Bias

Algorithmic bias refers to systematic and unfair discrimination produced by AI systems due to biased training data, flawed model design, or unequal deployment contexts.

Examples:

A hiring system trained on historical data that favors male candidates.

Facial recognition software that misidentifies individuals with darker skin tones more frequently.

Q2: Transparency vs Explainability in AI

Transparency involves openness about how an AI system is built, including data sources, algorithms, and decision processes.
Explainability focuses on clearly explaining why a specific AI decision or prediction was made.

Both are essential for trust, accountability, regulatory compliance, and enabling users to challenge automated decisions.

Q3: GDPR Impact on AI Development

The GDPR enforces strict data protection rules in the EU, requiring lawful data collection, user consent, data minimization, and protection of personal information. It also grants users rights over automated decision-making, influencing how AI systems are designed and deployed.

2. Ethical Principles Matching
Principle	Definition
Justice	Fair distribution of AI benefits and risks
Non-maleficence	Ensuring AI does not harm individuals or society
Autonomy	Respecting users’ right to control their data and decisions
Sustainability	Designing AI to be environmentally friendly
Part 2: Case Study Analysis (40%)
Case 1: Biased Hiring Tool (Amazon)

Source of Bias:

Training data reflected historical gender imbalance.

Model learned biased correlations from past hiring patterns.

Proposed Fixes:

Balance and diversify training data.

Remove gender-identifying features.

Conduct regular fairness audits.

Fairness Metrics:

Disparate Impact Ratio

Equal Opportunity Difference

False Positive / False Negative Rates

Case 2: Facial Recognition in Policing

Ethical Risks:

Wrongful arrests due to misidentification.

Privacy and civil rights violations.

Disproportionate harm to minority communities.

Recommended Policies:

Mandatory human oversight.

Accuracy thresholds across demographics.

Public transparency and accountability.

Part 3: Practical Audit – Dataset Bias (25%)
Dataset

COMPAS Recidivism Dataset

Tool

AI Fairness 360 (IBM)

Python Code Example
from aif360.datasets import CompasDataset
from aif360.metrics import BinaryLabelDatasetMetric

dataset = CompasDataset()
privileged_groups = [{'race': 1}]
unprivileged_groups = [{'race': 0}]

metric = BinaryLabelDatasetMetric(
    dataset,
    privileged_groups=privileged_groups,
    unprivileged_groups=unprivileged_groups
)

print("Disparate Impact:", metric.disparate_impact())
print("Statistical Parity Difference:", metric.statistical_parity_difference())

Summary of Findings

The analysis revealed racial disparities in COMPAS risk scores, with minority groups experiencing higher false positive rates. This bias is linked to historical inequalities in the criminal justice system.

Remediation Steps:

Apply data reweighing techniques.

Use in-processing debiasing methods.

Implement post-processing fairness adjustments.

Conduct regular audits and reporting.

Part 4: Ethical Reflection (5%)

In my projects, I will uphold ethical AI principles by ensuring fairness, transparency, and data privacy. I will audit datasets for bias, document AI decisions clearly, and include human oversight in high-impact systems to promote responsible AI use.

Bonus Task: Ethical AI Policy for Healthcare (Extra 10%)
Ethical AI Guidelines for Healthcare

Patient Consent

Obtain informed and explicit consent.

Clearly explain AI usage and data handling.

Bias Mitigation

Use diverse medical datasets.

Regularly test models across demographics.

Transparency

Ensure explainable AI decisions.

Maintain clear documentation of systems and limitations.
