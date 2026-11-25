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
