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
