# EU AI Act Approval Pack

## Executive Summary
The four scenarios span the main EU AI Act outcomes: one prohibited use, one high-risk employment case, one transparency-focused consumer assistant, and one low-risk productivity tool. The main issues are whether the system infers sensitive employee states, whether it affects access to work, whether users are clearly told they are interacting with AI, and whether the low-risk tool remains bounded and human-reviewed.

## Case 1
### Client use case
A fashion retailer wants an internal dashboard for managers that combines attendance, meeting activity, and manager notes with a score meant to indicate how engaged each employee or team appears during internal video briefings. The score is used to identify where coaching or support may be needed.

### Likely AI Act category
Prohibited

### Why
The proposed design attempts to infer emotional or engagement states from employee behaviour, especially face and voice signals, and then uses that output to influence managerial decisions about support. This is inconsistent with the EU AI Act’s ban on workplace emotion recognition and similar prohibited practices under Article 5.

### Proposed AI architecture
- Business trigger: manager review of team engagement and support needs.
- Input data/signals: employee video frames, voice patterns, attendance, and internal meeting metadata.
- Model/system behaviour: infer engagement or emotional state and generate a score for each employee or team.
- Human review point: manager sees score and may decide on intervention.
- Output/decision: employee or team support recommendations.
- Logging / record layer: no lawful use here; the system should not be used for this purpose.

### Role map
- Provider: likely the software vendor building the employee analytics system.
- Deployer: the retailer as the employer using the system internally.
- Third-party vendor: possible video analytics or HR-tech partner if outsourced.

### Required obligations / controls
This design cannot launch as proposed. A lawful redesign should replace employee emotion or engagement inference with non-biometric operational signals such as voluntary pulse surveys, workload indicators, meeting participation, or aggregated workflow metrics. The redesign should avoid inferring emotions from faces or voices.

### Decision
Deny and redesign

## Case 2
### Client use case
A recruitment agency receives many applications for hospitality jobs and wants AI to rank applicants using CVs, written answers, and employment history. Recruiters normally interview candidates above a threshold, but they can review and override the ranking.

### Likely AI Act category
High-risk

### Why
This affects access to employment, which is a protected Annex III area. The risk is not only in the final decision but also in how the system shapes who is shortlisted and interviewed.

### Proposed AI architecture
- Business trigger: hiring pipeline review for hospitality roles.
- Input data/signals: CV text, application answers, employment history, and candidate metadata.
- Model/system behaviour: rank applicants by predicted suitability for the role.
- Human review point: recruiters review shortlist and can override the ranking.
- Output/decision: shortlist and interview recommendation.
- Logging / record layer: maintain candidate-level decision logs, model version history, and override records.

### Role map
- Provider: AI vendor or model developer supplying the ranking system.
- Deployer: recruitment agency using the system for hiring.
- Third-party vendor: may include ATS or staffing software provider.

### Required obligations / controls
The deployer should implement meaningful human oversight, a documented risk management process, data governance, logging, instructions to staff, accuracy and robustness checks, cybersecurity controls, documentation, and monitoring. The provider has duties linked to the system as supplied, while the deployer has duties linked to real-world deployment and oversight. Recruiters must be able to override or disregard a recommendation.

### Decision
Approve with controls

## Case 3
### Client use case
An online beauty retailer wants an AI-powered shopping assistant that helps customers choose products and skincare routines based on their concerns, skin type, and preferences. Customers can also reach a human support agent. The assistant should feel conversational and natural.

### Likely AI Act category
Limited risk / transparency

### Why
The core issue is customer interaction with AI, so the main legal focus is transparency under Article 50. The assistant is not deciding employment or other high-risk outcomes, but it should not mislead users about whether they are speaking to a human or an AI system.

### Proposed AI architecture
- Business trigger: customer asks for product or skincare advice.
- Input data/signals: skin type, concerns, product preferences, and conversation history.
- Model/system behaviour: generate recommendations and routine suggestions.
- Human review point: human support agent available for escalation and exception handling.
- Output/decision: product suggestions and advice.
- Logging / record layer: limited conversation logging for service quality, complaint handling, and privacy controls.

### Role map
- Provider: LLM vendor or system integrator.
- Deployer: retailer operating the customer assistant.
- Third-party vendor: optional AI platform or support tool provider.

### Required obligations / controls
The assistant must clearly disclose that the user is interacting with AI, and the platform should provide a straightforward path to a human agent. Advice boundaries should be defined, especially for medical or sensitive skincare claims. If personal data is processed, GDPR/privacy controls should be checked, including purpose limitation, minimisation, consent or lawful basis, and retention limits. Logging should be proportionate and relevant to service quality or complaint management.

### Decision
Approve with controls

## Case 4
### Client use case
A photography studio wants AI to organise uploaded images into groups such as portraits, interiors, products, and landscapes. The photographer reviews the folders and can reorganise them manually before publishing or storing assets.

### Likely AI Act category
Minimal risk

### Why
This is a standard productivity and organisation use case. It does not determine access to employment, education, credit, public benefits, justice, or other consequential services, so there is no specific high-risk AI Act obligation triggered by the use case itself.

### Proposed AI architecture
- Business trigger: image upload for cataloguing and studio workflow.
- Input data/signals: photo files, metadata, and manually assigned tags.
- Model/system behaviour: classify images into folders such as portraits, products, and landscapes.
- Human review point: photographer reviews and reorganises folders.
- Output/decision: image grouping recommendations.
- Logging / record layer: optional operational logs for quality checks and user corrections.

### Role map
- Provider: AI tool vendor or image-classification platform.
- Deployer: photography studio.
- Third-party vendor: optional storage or image workflow partner.

### Required obligations / controls
This case can usually be approved. It should still be checked for GDPR, confidentiality, consumer protection, copyright, and contractual issues where relevant, but no specific high-risk AI Act obligations are triggered by the scenario as described.

### Decision
Approve

## Client Discussion / Debrief

### What changed after the client discussion?
The comparison confirmed the four initial classifications, so no risk categories changed.

- Case 1 was confirmed as prohibited. The proposed workplace engagement scoring should not proceed in its current form; the recommendation remains to redesign it around non-biometric operational signals rather than facial or voice-based emotional inference.
- Case 2 was confirmed as high-risk because the system influences access to employment. Human override does not remove the high-risk classification, so the recommendation remains approval only with the required controls.
- Case 3 was confirmed as a transparency case. The final design should make the AI disclosure visible at the start of the customer interaction and retain a clear route to human support.
- Case 4 was confirmed as minimal risk. Human review remains in place and no additional high-risk AI Act controls were identified.

The discussion therefore did not change the classifications, but it clarified the operational boundaries and controls required before deployment.

For a real deployment, final legal interpretation should be validated by qualified legal counsel.
