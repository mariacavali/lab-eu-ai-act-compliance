# EU AI Act Approval Pack

## Executive Summary
The four partner briefs cover the main EU AI Act outcomes in a realistic consulting exercise: one prohibited workplace emotion-recognition system, one high-risk recruitment ranking system, one limited-risk customer support assistant that needs clear transparency, and one low-risk operational demand-forecasting tool. The review focuses on the legal risk created by the system design, the people affected, the human-review point, and the practical controls required before deployment.

## Brief A — Call-centre employee analysis

### Client use case
A European call-centre operator is experiencing high employee turnover and wants managers to identify staff who may be disengaged or under excessive stress. The proposed system would analyse employees’ facial movements, tone of voice and speaking patterns during customer calls. It would estimate emotional states such as frustration, nervousness and enthusiasm. Managers would receive weekly employee scores that could influence coaching, shift allocation and performance discussions. A manager would review the scores before taking action, but employees could not opt out while working.

### Likely AI Act category
Prohibited

### Why
The proposed system infers employees’ emotional states from facial and voice-related signals in a workplace context. That falls squarely into the Article 5 prohibition on workplace emotion-recognition systems, even if a manager reviews the results before taking action. Human review does not make an otherwise prohibited practice acceptable.

### Proposed architecture / lawful redesign
Do not design or operate the prohibited emotion-recognition system. Instead, use a lawful redesign based on non-emotion-inference operational indicators:
- trigger: workforce wellbeing and retention review
- inputs: voluntary employee feedback, workload indicators, absence and attendance patterns, aggregated service metrics, and operational performance data
- no facial-expression emotion inference
- no voice-based emotion inference
- manager reviews aggregated indicators rather than inferred emotional scores
- output: support or coaching recommendation, not an emotional state score
- privacy controls: limited access, retention limits, employee notice, and lawful handling of any voluntary feedback

### Role map
- Provider: likely the AI vendor or workforce-analytics platform that would have built the emotion-scoring system
- Deployer: the call-centre operator as the employer
- Third-party vendor: possible workforce analytics or monitoring partner, if outsourced

### Required obligations / controls
The proposed system should not launch as designed. A lawful redesign must remove facial or voice-based emotion inference and rely instead on non-biometric operational metrics and voluntary employee feedback. Appropriate privacy and data-protection controls are essential because employee monitoring and personal data are involved.

### Decision
Deny and redesign

## Brief B — Recruitment ranking

### Client use case
A European recruitment agency receives thousands of applications for entry-level positions and wants to reduce the time recruiters spend reviewing candidates. A vendor proposes a system that analyses CVs, application answers and written skills tests. It ranks applicants and recommends which candidates should proceed to interview. Recruiters can change the ranking, but normally begin with the AI-generated shortlist. Applicants are affected through access to employment opportunities.

### Likely AI Act category
High-risk

### Why
This is an employment and recruitment use under the AI Act high-risk framework, specifically Annex III. The ranking materially influences access to employment, and human override is an important safeguard but does not automatically make the system non-high-risk.

### Proposed AI architecture
- application received
- CV/application/test data prepared for review
- AI ranking model produces candidate recommendation
- meaningful recruiter review of the shortlist and ranking
- recruiter can approve, reject, override or escalate the recommendation
- final interview decision made by the recruiter
- logging: candidate-level decision logs, ranking audit trail, override reasons, and model version history

### Role map
- Provider: third-party recruitment AI vendor
- Deployer: European recruitment agency
- Third-party vendor: optional ATS or assessment platform, if used

### Required obligations / controls
Relevant controls include meaningful human oversight, risk management, data governance, appropriate logging and record keeping, instructions and transparency, accuracy, robustness, cybersecurity, monitoring, and a documented override and escalation process. The recruitment agency should also implement deployer obligations appropriate to the hiring process. Provider and deployer responsibilities should be distinguished rather than assigned to the agency by default.

### Decision
Approve with controls

## Brief C — Furniture retailer conversational AI

### Client use case
An online furniture retailer wants customer support outside normal working hours. A third-party conversational AI would answer product questions, recommend products and explain delivery and return policies. It would use the retailer’s product catalogue, customer questions and, when the customer is signed in, order information. Difficult complaints and refund requests would be transferred to a human employee. The company wants the AI assistant to use a human first name because it believes customers will engage with it more naturally.

### Likely AI Act category
Limited risk / transparency

### Why
Customers are interacting directly with an AI system. Because the company wants the assistant to use a human first name, a clear AI disclosure is especially important so users are not misled into thinking they are speaking to a human. The key issue therefore sits in the transparency obligations, not in a high-risk decision context.

### Proposed AI architecture
- customer opens support chat
- clear AI disclosure at the start of the interaction
- inputs: product catalogue, customer questions and signed-in order information where relevant
- conversational AI responds with product and policy guidance
- difficult complaint or refund queries escalate to a human employee
- logging/privacy layer: limited conversation logs, access controls, retention limits, and privacy review for signed-in customer data

### Role map
- Provider: third-party conversational AI provider/vendor
- Deployer: furniture retailer
- Additional vendors: none required unless the retailer uses a separate support platform, which would need to be identified as an assumption

### Required obligations / controls
The system should be approved with controls. These include a clear AI disclosure at the beginning of the interaction, a clear human escalation path, defined boundaries for automated support, and GDPR/privacy safeguards for signed-in order information. Appropriate access controls and proportionate retention/logging rules should also be in place.

### Decision
Approve with controls

## Brief D — Bakery demand forecasting

### Client use case
A regional bakery chain wants to reduce food waste by forecasting how many products each shop should prepare every morning. The system analyses previous sales, public weather information, holidays and store location. It recommends production quantities for bread and pastries. Store managers review the recommendation and can change it using local knowledge. The system does not evaluate employees or customers and does not use personal data.

### Likely AI Act category
Minimal risk

### Why
This is an operational demand-forecasting system rather than a consequential decision about individuals. It forecasts production quantities and does not determine access to employment, credit, public services, education, justice or other high-impact opportunities.

### Proposed AI architecture
- daily forecast trigger
- historical sales, weather, holidays and store location as inputs
- forecasting model generates a production recommendation
- store manager reviews and can override the recommendation using local knowledge
- final output: production quantities for bread and pastries
- operational controls: data quality checks, forecast performance monitoring, human override, and basic operational logging

### Role map
- Provider: forecasting tool vendor or internal analytics team, if built in-house
- Deployer: bakery chain operating the forecast
- Third-party vendor: optional analytics platform or data provider if used

### Required obligations / controls
Controls should be proportionate. Data quality checks, forecast performance monitoring, clear manager override rights, and basic operational logging are sufficient. No high-risk AI Act obligations are implied by the scenario as described, although general laws may still be relevant where applicable.

### Decision
Approve

## Client Discussion / Debrief

### Partner review process
This lab was completed as a paired exercise. I first created four hidden client scenarios and shared the partner-facing versions for independent classification. I then received a separate set of four client briefs from my partner and reviewed them as the consultant.

### Review of the partner briefs
Brief A was classified as prohibited because it infers employee emotional states from facial and voice-related signals in the workplace. The proposed design should therefore be denied and redesigned without emotion inference.

Brief B was classified as high-risk because AI ranking materially influences candidates' access to employment. Human recruiter review remains necessary but does not remove the high-risk classification.

Brief C was classified as a transparency case because customers interact directly with conversational AI. The use of a human first name makes a clear AI disclosure at the beginning of the interaction especially important.

Brief D was classified as minimal risk because the AI forecasts bakery production quantities and does not evaluate individuals or determine access to consequential opportunities.

### Partner classification of my hidden cases
My partner independently classified the four scenarios I originally authored. The classifications were then compared with my private answer key as part of the discussion.

The comparison highlighted the importance of checking the underlying scenario facts rather than relying only on case letters when discussing classifications.

For a real deployment, final legal interpretation should be validated by qualified legal counsel.
