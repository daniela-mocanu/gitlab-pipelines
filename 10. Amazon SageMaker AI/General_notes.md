# Amazon SageMaker AI — General Notes

Lectures 94–102.

## 95. Amazon SageMaker AI – Overview

Amazon SageMaker AI is a **fully managed AWS service** that helps developers and data scientists **build, train, and deploy machine-learning models**. It brings much of the machine-learning workflow together in one platform.

### Data Preparation

- Collect and transform historical data.
- Select useful features for the model.
- Example: use years of experience and course engagement to predict exam scores.

### Model Building, Training, and Tuning

- Use built-in algorithms for tasks such as **regression**, **classification**, **dimensionality reduction**, and **clustering**.
- Improve models through **hyperparameter tuning**, including with **SageMaker Automatic Model Tuning**.

### Inference Options

| Option | Purpose |
| --- | --- |
| **Real-time inference** | Low-latency responses. |
| **Serverless inference** | Reduce infrastructure management; cold starts can occur. |
| **Asynchronous inference** | Handle larger requests or longer processing times. |
| **Batch Transform** | Process many records together. |

### SageMaker Studio

**SageMaker Studio** is an integrated environment for managing machine-learning workflows, collaboration, tuning, debugging, and deployment.

## 97. Amazon SageMaker AI – Data Tools

### SageMaker Data Wrangler

SageMaker Data Wrangler helps prepare **tabular and image data** for machine learning. It supports:

- Importing data from sources such as **Amazon S3**.
- Exploring and visualizing datasets.
- Checking data quality.
- Applying transformations and feature engineering.

### Feature Engineering

**Feature engineering** turns raw data into useful model inputs. For example, a birth date can be transformed into a person’s **age**, which may be more useful for a prediction task.

### SageMaker Feature Store

SageMaker Feature Store provides a **centralized place to manage, share, and discover features** across datasets and teams. Features can be published from Data Wrangler to support collaboration and reuse.

| Tool | Focus |
| --- | --- |
| **Data Wrangler** | Preparing data for machine learning. |
| **Feature Store** | Managing and sharing machine-learning features. |

## 98. Amazon SageMaker – Models and Humans

### SageMaker Clarify

- Helps assess **bias and fairness**.
- Helps explain model predictions.
- Evaluates foundation models on selected tasks; some evaluations can involve human reviewers.

#### Foundation Model Evaluation

Source: “SageMaker Clarify” course slide.

- Evaluate and compare **foundation models**, including human factors such as **friendliness** or **humor**.
- Use an **AWS-managed team** of reviewers or your **own employees**.
- Use **built-in datasets** or bring your **own dataset**.
- Provides **built-in metrics and algorithms**.
- Available as part of **SageMaker Studio**.

#### Example: Comparing Model A and Model B

The slide shows a text-summarization evaluation with two criteria:

| Criterion | What is evaluated | Evaluation and rating | Model A | Model B |
| --- | --- | --- | --- | --- |
| **Brand voice** | How well the response matches the company’s tone. | Pairwise comparison using choice buttons; reported as **preference rate**. | 25% | 75% |
| **Relevance** | Whether the generated summary includes relevant knowledge or facts. | Individual evaluation using thumbs up/down; reported as **approval rate**. | 64% | 93% |

These percentages are the example results shown in the slide.

#### Model Explainability

Source: “SageMaker Clarify – Model Explainability” course slide.

SageMaker Clarify provides tools to help explain **how machine-learning models make predictions**.

- **Before deployment:** Understand the model’s characteristics as a whole.
- **After deployment:** Debug predictions provided by the model.
- Help increase trust in and understanding of the model.

Example questions:

- “Why did the model predict a negative outcome such as a loan rejection for a given applicant?”
- “Why did the model make an incorrect prediction?”

The slide’s SageMaker Studio example shows a feature-importance chart across a dataset, with features such as **MaturityMonths**, **LoanAmount**, and **Age**. This helps show which inputs influence the model’s predictions overall.

### SageMaker Ground Truth

- Helps create **labeled datasets** by having people label data for machine learning.

### Amazon Augmented AI (A2I)

- Adds **human review of model predictions**, such as reviewing low-confidence results.
- For this prediction-review use case, use A2I rather than Ground Truth.

| Service | Main purpose |
| --- | --- |
| **Clarify** | Analyze and evaluate models. |
| **Ground Truth** | Label data. |
| **A2I** | Add human review to predictions. |

## Additional Note: Amazon SageMaker AI – Governance and MLOps

| Tool | Purpose |
| --- | --- |
| **Model Cards** | Document key model information, such as intended use, risks, and training details. |
| **Model Dashboard** | Provide a central view of models, including model and data quality, risk ratings, and monitoring alerts. |
| **Role Manager** | Help define permissions for different roles in an organization. |
| **Model Registry** | Track and version models, including their approval status. |
| **SageMaker Pipelines** | Automate machine-learning workflows, such as data processing, training, tuning, registration, and quality checks, supporting repeatable processes similar to CI/CD. |

Together, these tools help teams govern models, monitor quality, manage approvals, and operationalize machine-learning workflows.
