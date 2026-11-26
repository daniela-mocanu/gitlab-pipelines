# AI Challenges and Responsibilities — General Notes

Lectures 104–111, from **104. AI Challenges and Responsibilities – Overview** through **111. MLOps**.

## 104. AI Challenges and Responsibilities – Overview

### Overview

This lecture introduces responsible AI, security, governance, and compliance. As AI becomes more capable, it is important to define how it should be used so that systems remain ethical, responsible, and safe.

**Exam focus:** Understand the purpose of these topics and the principles behind them, rather than memorizing detailed implementation steps.

The lecture sets the stage for exploring challenges such as **bias**, **transparency**, **explainability**, **privacy**, and **accountability** in later material.

Source: “Responsible AI & Security” and “Governance & Compliance” course slides.

### Responsible AI

- Ensure AI systems are **transparent and trustworthy**.
- Mitigate potential risks and negative outcomes.
- Apply these practices throughout the **AI lifecycle**: design, development, deployment, monitoring, and evaluation.

### Security

- Maintain **confidentiality, integrity, and availability**.
- Protect organizational data, information assets, and infrastructure.

### Governance

- Ensure AI adds business value while managing operational risk.
- Establish clear **policies, guidelines, and oversight mechanisms** so AI systems align with legal and regulatory requirements.
- Improve trust.

### Compliance

- Ensure adherence to **regulations and guidelines**.
- Especially relevant in sensitive domains such as **healthcare**, **finance**, and **legal applications**.

| Concept | Main focus |
| --- | --- |
| **Responsible AI** | Trustworthy, transparent AI and mitigation of negative outcomes throughout its lifecycle. |
| **Security** | Confidentiality, integrity, and availability of data, assets, and infrastructure. |
| **Governance** | Policies and oversight that support business value and risk management. |
| **Compliance** | Adherence to applicable regulations and guidelines. |

## 105. Responsible AI

### Overview and Key Principles

Responsible AI means designing and using AI systems **ethically, safely, and transparently** so people can trust their outcomes. It applies throughout the **AI lifecycle**: design, development, deployment, monitoring, and evaluation.

| Principle | Focus |
| --- | --- |
| **Fairness and bias mitigation** | Aim for equitable outcomes and check datasets and models for bias. |
| **Inclusivity** | Make systems accessible and considerate of different users. |
| **Robustness and safety** | Build systems that perform reliably and reduce potential harm. |
| **Veracity** | Seek accurate, truthful outputs and address hallucinations. |
| **Transparency and explainability** | Help people understand how AI systems work and why they produce results. |
| **Sustainability** | Consider environmental impact when selecting and using models. |

Responsible AI also involves managing risks such as **discriminatory outputs**, **intellectual-property concerns**, **inaccurate content**, and **loss of user trust**. Tools such as **Amazon Bedrock Guardrails** can help control model behavior and reduce undesirable outputs.

Source: Seven course slides covering AWS services, core dimensions, AI Service Cards, interpretability trade-offs, decision trees, partial dependence plots, and human-centered design.

### Responsible AI – AWS Services

| Service or feature | Responsible AI use |
| --- | --- |
| **Amazon Bedrock** | Human or automatic model evaluation. |
| **Guardrails for Amazon Bedrock** | Filter harmful content, block undesirable topics, and redact personally identifiable information (PII) to improve safety and privacy. |
| **SageMaker Clarify** | Evaluate foundation models for accuracy, robustness, and toxicity; detect bias, such as data skewed toward middle-aged people. |
| **SageMaker Data Wrangler** | Help address representation bias by balancing datasets, including augmenting data for underrepresented groups. Balancing alone does not guarantee fairness. |
| **SageMaker Model Monitor** | Analyze model quality in production. |
| **Amazon Augmented AI (A2I)** | Human review of ML predictions. |
| **SageMaker Role Manager, Model Cards, and Model Dashboard** | Support governance through permissions, documentation, and centralized visibility. |

### Core Dimensions of Responsible AI

| Dimension | Meaning |
| --- | --- |
| **Fairness** | Promote inclusion and prevent discrimination. |
| **Explainability** | Help people understand model predictions and behavior. |
| **Privacy and security** | Protect data and support individuals’ control over when and whether their data is used. |
| **Transparency** | Communicate relevant information about the system, its use, and limitations. |
| **Veracity and robustness** | Produce reliable results, including in unexpected situations. |
| **Governance** | Define, implement, and enforce responsible AI practices. |
| **Safety** | Make algorithms safe and beneficial for individuals and society. |
| **Controllability** | Enable alignment with human values and intent. |

### AWS AI Service Cards

- A form of **responsible AI documentation**.
- Help users understand a service and its features.
- Describe **intended use cases and limitations**.
- Explain **responsible AI design choices**.
- Examples shown: **Amazon Textract AnalyzeID** and **Amazon Rekognition Face Matching**.

[Example AWS AI Service Card: Textract AnalyzeID](https://aws.amazon.com/machine-learning/responsible-machine-learning/textract-analyzeid/).

### Interpretability and Explainability

- **Interpretability:** How directly a human can understand a model’s decision process and interpret its output; helps answer **“why and how.”**
- **Explainability:** Methods for understanding a model’s nature and behavior, including explaining outputs through inputs and outputs without fully understanding every internal computation.
- Explainability can sometimes meet the use case’s needs even when the model is not directly interpretable.

#### Interpretability Trade-Offs

The slide illustrates decreasing interpretability and increasing performance in this order:

**Linear Regression → Decision Tree → Logistic Regression → Naïve Bayes → K-nearest Neighbors → Support Vector Machines → Ensemble Methods → Neural Networks.**

This is a conceptual illustration, not a universal ranking. **High transparency or interpretability does not inherently imply poor performance**; performance and interpretability depend on the task, data, model size, and implementation.

### High Interpretability – Decision Trees

- A **supervised learning** algorithm for **classification and regression**.
- Split data into branches based on feature values, using rules such as **“Is the feature greater than 5?”**
- A clear visual structure makes small trees easy to interpret.
- Too many branches can lead to **overfitting** and make interpretation harder.

The slide’s illustrative risk-classification tree uses income and credit history:

| Income branch | Credit history | Predicted risk |
| --- | --- | --- |
| More than $50K | Good | Low |
| More than $50K | Bad or unknown | Moderate |
| $20–50K | Good | Low |
| $20–50K | Bad or unknown | High |
| Less than $20K | Not checked in this branch | High |

### Partial Dependence Plots (PDP)

- Show how a feature influences the model’s **average predicted outcome**.
- Compute predictions over a range of values for the selected feature while retaining other features’ observed values, then average across examples. This clarifies the slide’s shorthand of “holding other features constant.”
- Particularly useful for explaining **black-box models**, such as neural networks.
- Support interpretability and explainability.
- The example shows predicted **loan approval probability increasing with income**, then leveling off near 1.
- A PDP describes model behavior, not a causal effect. Correlated features can make its hypothetical input combinations unrealistic.

### Human-Centered Design (HCD) for Explainable AI

Design AI systems with **human needs as a priority**.

#### Design for Amplified Decision-Making

- Minimize risks and errors in stressful or high-pressure environments.
- Prioritize **clarity, simplicity, and usability**.
- Support **reflexivity**—reflection on the decision-making process—and **accountability**.

#### Design for Unbiased Decision-Making

- Aim for decision processes free from bias.
- Train decision-makers to recognize and mitigate biases.

#### Design for Human and AI Learning

- **Cognitive apprenticeship:** AI systems learn from human instructors and experts.
- **Personalization:** Meet the specific needs and preferences of a human learner.
- **User-centered design:** Make systems accessible to a wide range of users.

## 106. GenAI Challenges

Source: Seven course slides on generative AI capabilities and challenges, toxicity, hallucinations, plagiarism and cheating, and prompt misuses.

### Capabilities of Generative AI

- Adaptability.
- Responsiveness.
- Simplicity.
- Creativity and exploration.
- Data efficiency.
- Personalization.
- Scalability.

### Challenges of Generative AI

- Regulatory violations.
- Social risks.
- Data security and privacy concerns.
- Toxicity.
- Hallucinations.
- Interpretability.
- Nondeterminism.
- Plagiarism and cheating.

### Toxicity

**Toxicity** is the generation of content that is offensive, disturbing, or inappropriate.

- Defining toxicity can be difficult and context-dependent.
- There is a boundary to consider between restricting toxic content and censorship.
- Quotations of offensive material raise questions about when such content is appropriate to include.
- The slide illustrates a request to express strong disagreement producing a personal insult instead of respectful disagreement.

**Mitigation:**

- Curate training data by identifying and removing offensive phrases in advance, while considering context.
- Use guardrail models to detect and filter unwanted content.

### Hallucinations

**Hallucinations** are assertions or claims that sound true but are incorrect, including plausible descriptions of content that does not exist.

LLMs generate text through next-token prediction rather than guaranteed factual verification. The slide links hallucinations to probability sampling; however, hallucinations can also occur with deterministic decoding, so sampling is not their sole cause.

**Mitigation:**

- Educate users that model-generated content must be checked.
- Verify content against independent sources.
- Mark unverified generated content so users know verification is necessary.

### Plagiarism and Cheating

- GenAI can be misused for college essays, writing samples for job applications, and other forms of cheating or illicit copying.
- Debate continues about when these technologies should be accepted or restricted.
- Tracing the source of a specific LLM output can be difficult.
- Technologies attempt to detect AI-generated text or images; their results are not definitive proof of authorship.

### Prompt Misuses and Related Threats

#### Poisoning

- Intentionally introduce malicious or biased data into a model’s **training dataset**.
- This can lead to biased, offensive, or harmful outputs.
- Although grouped under “Prompt Misuses” in the slide, training-data poisoning targets the training data rather than an inference-time prompt.

#### Hijacking and Prompt Injection

- Embed instructions in prompts or other model inputs to redirect model behavior toward an attacker’s intentions.
- Potential outcomes include misinformation or attempts to trigger harmful actions in connected systems.
- Model-generated text does not execute code by itself; execution requires access to tools or an application that runs it.

#### Exposure

- Sensitive or confidential information supplied during **training or inference** may be exposed through model outputs or surrounding systems.
- A model may reproduce memorized training information or reveal sensitive information present in its current context, creating data-leak or privacy risks.
- Supplying information during inference does not itself mean that the model is retrained on it.

#### Prompt Leaking

- Disclosure of prompts or inputs used by a model, whether accidental or deliberately induced.
- Can expose protected information, internal instructions, or details about the application’s configuration.

#### Jailbreaking

- Attempt to circumvent a model’s ethical or safety constraints, such as restrictions on offensive content or sensitive information.
- Aims to obtain outputs or functionality that the safeguards are intended to restrict.

### Exam Distinctions

| Term | Key distinction |
| --- | --- |
| **Toxicity** | Offensive, disturbing, or inappropriate content. |
| **Hallucination** | Plausible but incorrect or fabricated content. |
| **Poisoning** | Malicious modification of training data. |
| **Prompt injection / hijacking** | Instructions in inputs redirect model or application behavior. |
| **Exposure** | Sensitive information is placed at risk of disclosure. |
| **Prompt leaking** | Prompts or internal input content are disclosed. |
| **Jailbreaking** | Attempts to bypass safety constraints. |

## 107. Compliance for AI

Source: “AI Standard Compliance Challenges,” “AWS Compliance,” and “Model Cards” course slides.

### AI Standard Compliance Challenges

| Challenge | Why it matters |
| --- | --- |
| **Complexity and opacity** | It can be difficult to audit how AI systems make decisions. |
| **Dynamism and adaptability** | AI systems can change over time through updates, retraining, or changes in their operating context. |
| **Emergent capabilities** | Systems may exhibit unintended or previously unrecognized capabilities. |
| **Unique risks** | Algorithmic bias, privacy violations, and misinformation complicate compliance. |
| **Algorithm accountability** | Transparency and explainability support scrutiny of decisions and responsibility for outcomes. |

#### Algorithmic and Human Bias

- **Algorithmic bias:** Biased or unrepresentative data can cause a model to perpetuate bias.
- **Human bias:** People who create an AI system can introduce bias through their choices.
- The slide uses an AI-generated picture of doctors to illustrate concerns about representation in generated outputs.

#### Regulations and Accountability

- The lecture references the **EU Artificial Intelligence Act** and AI regulations in several **US states and cities**.
- These measures seek to promote **fairness, non-discrimination, and human rights**.
- Specific obligations depend on the applicable law, jurisdiction, system, and use case.

### AWS Compliance

The slide states that AWS supports **over 140 security standards and compliance certifications**. This is the course slide’s figure, rather than a current verified count.

The slide lists the following organizations, frameworks, standards, and laws; they are not all certifications:

| Name | What it refers to |
| --- | --- |
| **NIST** | National Institute of Standards and Technology; develops standards and frameworks. |
| **ENISA** | European Union Agency for Cybersecurity. |
| **ISO** | International Organization for Standardization; develops international standards. |
| **SOC** | System and Organization Controls reports on service organizations’ controls. |
| **HIPAA** | Health Insurance Portability and Accountability Act; US health-information requirements. |
| **GDPR** | General Data Protection Regulation; EU personal-data protection law. |
| **PCI DSS** | Payment Card Industry Data Security Standard. |

AWS compliance coverage does not automatically make a customer’s AI application compliant; the customer’s implementation and responsibilities also matter.

### Model Cards

- A **standardized format** for documenting key details about an ML model.
- For generative AI, can include **source citations** and **data-origin documentation**.
- Document datasets, their sources and licenses, and known biases or quality issues in training data.
- Include **intended use**, **risk rating**, **training details**, and **metrics**.
- **SageMaker Model Cards** centralize documentation of your ML models.
- Support **audit activities** by making relevant model information available for review.
- The slide also references **AWS AI Service Cards**. These document AWS services’ intended uses, limitations, and responsible AI considerations; they are related documentation, distinct from SageMaker Model Cards for individual models.

## 108. Governance for AI

### Definition and Exam Focus

**AI governance** is the set of policies, guidelines, and oversight processes that help an organization manage AI responsibly and consistently.

| Goal | Meaning |
| --- | --- |
| **Managing risk** | Identify and reduce potential harms or operational risks. |
| **Creating business value** | Ensure AI use supports organizational objectives. |
| **Meeting legal and regulatory requirements** | Set expectations for how AI systems are designed and used. |
| **Building trust** | Make responsibilities and oversight clear to users and stakeholders. |

Governance is related to, but distinct from, **responsible AI**, **security**, and **compliance**. Responsible AI focuses on trustworthy and transparent outcomes throughout the AI lifecycle. Security protects **confidentiality, integrity, and availability**. Compliance focuses on following applicable regulations and guidelines.

**Exam reminder:** Governance provides the **policies and oversight** that guide AI use, manage risk, and align systems with business and regulatory expectations.

Source: Course slides on the importance of governance and compliance, a governance framework, governance strategies, and data management concepts.

### Importance of Governance and Compliance

- Manage, optimize, and scale organizational AI initiatives.
- Build trust through responsible and trustworthy AI practices.
- Mitigate risks such as **bias**, **privacy violations**, and **unintended consequences**.
- Establish clear **policies, guidelines, and oversight mechanisms** so AI systems align with legal and regulatory requirements.
- Protect against legal and reputational risks.
- Build public confidence in the responsible deployment of AI.

### Governance Framework: Example Approach

1. **Establish an AI Governance Board or Committee.** Include representatives from legal, compliance, data privacy, and subject matter experts (SMEs) in AI development.
2. **Define roles and responsibilities.** Cover oversight, policy-making, risk assessment, and decision-making processes.
3. **Implement policies and procedures.** Address the entire AI lifecycle, from data management through model deployment and monitoring.

### Governance Strategies

#### Policies

- Define principles, guidelines, and responsible AI considerations.
- Cover **data management**, **model training**, **output validation**, **safety**, and **human oversight**.
- Address **intellectual property**, **bias mitigation**, and **privacy protection**.

#### Review Cadence

- Combine **technical**, **legal**, and **responsible AI** reviews.
- Set a clear schedule, such as monthly, quarterly, or annually.
- Include **SMEs**, **legal and compliance teams**, and **end-users**.

#### Review Strategies

- **Technical reviews:** Assess model performance, data quality, and algorithm robustness.
- **Non-technical reviews:** Assess policies, responsible AI principles, and regulatory requirements.
- Test and validate outputs before deploying a new model.
- Use clear decision-making frameworks to act on review results.

#### Transparency Standards

- Publish information about AI models, training data, and key decisions made.
- Document AI solutions’ **limitations**, **capabilities**, and **use cases**.
- Provide channels for end-users and stakeholders to offer feedback and raise concerns.

#### Team Training Requirements

- Train teams on relevant policies, guidelines, and best practices.
- Include bias mitigation and responsible AI practices.
- Encourage cross-functional collaboration and knowledge-sharing.
- Implement a training and certification program.

### Data Management Concepts

| Concept | Focus |
| --- | --- |
| **Data lifecycle** | Collection → processing → storage → consumption → archival. |
| **Data logging** | Track inputs, outputs, performance metrics, and system events. |
| **Data residency** | Where data is processed and stored, considering regulations, privacy requirements, and proximity between compute and data. |
| **Data monitoring** | Assess data quality and identify anomalies and data drift. |
| **Data analysis** | Statistical analysis, visualization, and exploration. |
| **Data retention** | Decide how long to keep data, considering regulatory requirements, historical training data needs, and cost. |

## 109. Security and Privacy for AI

Source: Seven course slides on AI system security and privacy, monitoring, the AWS Shared Responsibility Model, and secure data engineering.

### Threat Detection

- Threat examples include **fake content**, **manipulated data**, and **automated attacks**.
- Deploy AI-based threat detection systems.
- Analyze **network traffic**, **user behavior**, and other relevant data sources.

### Vulnerability Management

- Identify vulnerabilities such as **software bugs** and **model weaknesses**.
- Conduct security assessments, authorized penetration testing, and code reviews.
- Maintain patch management and update processes.

### Infrastructure Protection

- Secure cloud platforms, edge devices, and data stores.
- Use **access controls**, **network segmentation**, and **encryption**.
- Design systems to withstand failures.

### Prompt Injection

- Manipulated inputs can redirect model behavior toward malicious or undesirable outputs.
- The slide recommends guardrails such as **prompt filtering**, **sanitization**, and **validation**.
- These measures reduce risk but do not guarantee prevention; maintain authorization checks and restricted tool permissions outside the model as well.

### Data Encryption

- Encrypt data **at rest** and **in transit**.
- Manage encryption keys properly and protect them against unauthorized access.

### Monitoring AI Systems

#### Performance Metrics

The definitions below correct the slide’s shorthand for accuracy and F1. For binary classification, TP = true positives, TN = true negatives, FP = false positives, and FN = false negatives.

| Metric | Meaning or formula |
| --- | --- |
| **Accuracy** | Proportion of all predictions that are correct: **(TP + TN) / (TP + TN + FP + FN)**. It is not the proportion of positive predictions. |
| **Precision** | Proportion of predicted positives that are actually positive: **TP / (TP + FP)**. |
| **Recall** | Proportion of actual positives correctly identified: **TP / (TP + FN)**. |
| **F1-score** | **Harmonic mean** of precision and recall: **2 × precision × recall / (precision + recall)**. |
| **Latency** | Time taken by the model to make a prediction. |

#### Infrastructure and Responsible AI Monitoring

- Monitor **CPU and GPU usage**, **network performance**, **storage**, and **system logs** to detect bottlenecks and failures.
- Monitor **bias and fairness**, **compliance**, and **responsible AI** considerations.

### AWS Shared Responsibility Model

**Exam distinction: AWS secures “of” the cloud; customers secure “in” the cloud.** The precise division depends on the service being used.

| Responsibility | Scope and examples |
| --- | --- |
| **AWS: Security of the cloud** | Protect the hardware, software, facilities, and networking that run AWS services, including managed services such as Bedrock, SageMaker, and S3. |
| **Customer: Security in the cloud** | Manage customer data, applications, identities, access controls, and security configuration. For Bedrock, examples include data management, access permissions, and configuring guardrails. Protect application data through appropriate encryption. |
| **Shared controls** | Patch management, configuration management, and awareness and training: AWS and customers each handle their respective layers and responsibilities. |

#### Layers Shown in the Diagram

- **Customer layer:** Customer data; platform and applications; identity and access management; applicable operating-system, network, and firewall configuration; client-side data encryption and integrity authentication; server-side encryption configuration; and network traffic protection.
- **AWS layer:** Underlying service software; compute, storage, database, and networking infrastructure; physical hardware and global infrastructure, including **Regions**, **Availability Zones**, and **edge locations**.
- The diagram is a general model. With managed services, AWS operates more of the stack; customers do not manage every operating-system or infrastructure layer shown.

[AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/).

### Secure Data Engineering – Best Practices

#### Assessing Data Quality

| Dimension or practice | Focus |
| --- | --- |
| **Completeness** | Cover a diverse and comprehensive range of scenarios. |
| **Accuracy** | Ensure data is accurate, up to date, and representative. |
| **Timeliness** | Assess the age of stored data and whether it remains suitable for the task. |
| **Consistency** | Maintain coherence and consistency throughout the data lifecycle. |
| **Data profiling and monitoring** | Examine data characteristics and track quality over time. |
| **Data lineage** | Track data origins and transformations. |

#### Privacy-Enhancing Technologies

- Use **data masking** and **obfuscation** to reduce the risk of sensitive-data exposure.
- Use **encryption** and **tokenization** to protect data as appropriate during processing and usage. Here, tokenization replaces sensitive values with substitutes; it is distinct from splitting text into LLM tokens.

#### Data Access Control

- Establish a comprehensive data governance framework with clear policies.
- Use **role-based access control** and **fine-grained permissions**.
- Use **single sign-on (SSO)**, **multi-factor authentication (MFA)**, and **identity and access management (IAM)** solutions.
- Monitor and log data access activities.
- Regularly review and update access rights according to **least privilege**.

#### Data Integrity

- Keep data complete, consistent, and free from errors and inconsistencies.
- Maintain a robust **backup and recovery strategy**.
- Preserve **data lineage** and **audit trails**.
- Monitor and test integrity controls to ensure they are effective.
