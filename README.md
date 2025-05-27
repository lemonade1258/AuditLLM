# AuditLLM

A Compact and Domain-Specialized Large Language Model Family for Intelligent Auditing via Two-Stage Continual Pre-Training

# Introduction

Domain-specific LLMs have become an increasingly important research issue in recent years and various LLMs has been proposed to specific domains, such as finance, healthcare and legal. However, the current LLMs adopted in auditing faces critical challenges like cloud-API restrictions under data privacy compliance, hardware limitations in deploying trillion-parameter models, and deficiencies in factual accuracy and logical rigor exhibited by general-purpose LLMs in auditing contexts. This paper addresses training LLMs for auditing and proposes a two-phase framework to develop compact, audit-specialized LLMs tailored for Chinese auditing workflows. First, Qwen2.5 is selected as the base model through systematic comparisons of sub-5B parameter architectures. Subsequently, domain-adaptive continual pre-training by a carefully designed data sampling strategy is performed on a curated corpus of Chinese audit texts to inject domain expertise. Finally, multi-task instruction-tuning aligns the model with practical audit requirements. Extensive experiments demonstrate that the proposed framework can significantly improve the performance of domain specific LLMs in audit tasks, enhancing their accuracy and practicality for real-world applications. This study underscores the importance of domain-adaptive pre-training.

# Explain

1.This project is still undergoing continuous iteration and updates. Due to Acl's anonymity policy, the Huggingface address hosting the model was temporarily hidden, but the experimental data is now publicly available;
2.The data and models provided in this project are for scientific research purposes only and are strictly prohibited from being used for commercial purposes.

# Architecture

## Overview framework of training Audit Language Model


<img src="" alt="Image" width="500"/>


# Result

| model        | model size | Financial Tokens (B) | English Tokens (B) | Chinese Tokens (B) | Regulation Tokens (B) | FinanceIQ | reg-entity | reg-problem-entity | reg-legal-name | reg-relation | Average Performance |
| ------------ | ---------- | -------------------- | ------------------ | ------------------ | --------------------- | --------- | ---------- | ------------------ | -------------- | ------------ | ------------------- |
| OpenAuditLLM | 0.5        | 0.0125               | 0.0125             | 0.0125             | 0.0125                | 44.03     | 41.77      | 26.8               | 14.68          | 14.53        | 28.362              |
| OpenAuditLLM | 0.5        | 0.025                | 0.025              | 0.025              | 0.025                 | 40.91     | 41.96      | 22.28              | 16.06          | 23.93        | 29.028              |
| OpenAuditLLM | 0.5        | 0.0375               | 0.0375             | 0.0375             | 0.0375                | 41.23     | 46.03      | 26.14              | 15.6           | 24.79        | 30.758              |
| OpenAuditLLM | 0.5        | 0.05                 | 0.05               | 0.05               | 0.05                  | 40.83     | 50.35      | 26.14              | 16.06          | 26.5         | 31.976              |
| OpenAuditLLM | 0.5        | 0.00625              | 0.0125             | 0.0125             | 0.0125                | 40.52     | 43.1       | 24.18              | 16.97          | 22.22        | 29.398              |
| OpenAuditLLM | 0.5        | 0.0125               | 0.025              | 0.025              | 0.025                 | 41.06     | 43.23      | 18.95              | 16.97          | 23.93        | 28.828              |
| OpenAuditLLM | 0.5        | 0.01875              | 0.0375             | 0.0375             | 0.0375                | 40.71     | 43.8       | 22.22              | 16.54          | 24.79        | 29.612              |
| OpenAuditLLM | 0.5        | 0.025                | 0.05               | 0.05               | 0.05                  | 41.01     | 45.52      | 23.53              | 16.06          | 26.5         | 30.524              |
| OpenAuditLLM | 0.5        | 0.025                | 0.0125             | 0.0125             | 0.0125                | 40.89     | 47.29      | 21.57              | 14.68          | 23.93        | 29.672              |
| OpenAuditLLM | 0.5        | 0.05                 | 0.025              | 0.025              | 0.025                 | 40.99     | 55.12      | 22.88              | 15.6           | 27.35        | 32.388              |
| OpenAuditLLM | 0.5        | 0.075                | 0.0375             | 0.0375             | 0.0375                | 41.25     | 58.61      | 22.22              | 15.14          | 28.21        | 33.086              |
| OpenAuditLLM | 0.5        | 0.1                  | 0.05               | 0.05               | 0.05                  | 41.46     | 55.24      | 22.88              | 14.68          | 29.06        | 32.664              |
| OpenAuditLLM | 0.5        | 0.0125               | 0.00625            | 0.0125             | 0.0125                | 40.89     | 47.29      | 21.57              | 14.68          | 23.93        | 29.672              |
| OpenAuditLLM | 0.5        | 0.025                | 0.0125             | 0.025              | 0.025                 | 40.99     | 55.12      | 22.88              | 15.6           | 27.35        | 32.388              |
| OpenAuditLLM | 0.5        | 0.0375               | 0.01875            | 0.0375             | 0.0375                | 41.25     | 58.61      | 22.22              | 15.14          | 28.21        | 33.086              |
| OpenAuditLLM | 0.5        | 0.05                 | 0.025              | 0.05               | 0.05                  | 41.46     | 55.24      | 22.88              | 14.68          | 29.06        | 32.664              |
| OpenAuditLLM | 0.5        | 0.0125               | 0.025              | 0.0125             | 0.0125                | 40.54     | 45.26      | 23.53              | 18.81          | 19.66        | 29.56               |
| OpenAuditLLM | 0.5        | 0.025                | 0.05               | 0.025              | 0.025                 | 41.3      | 55.63      | 23.53              | 16.51          | 27.35        | 32.864              |
| OpenAuditLLM | 0.5        | 0.0375               | 0.075              | 0.0375             | 0.0375                | 41.25     | 49.78      | 23.53              | 16.06          | 30.77        | 32.278              |
| OpenAuditLLM | 0.5        | 0.05                 | 0.1                | 0.05               | 0.05                  | 41.56     | 49.21      | 22.88              | 16.06          | 29.91        | 31.924              |
| OpenAuditLLM | 0.5        | 0.0125               | 0.0125             | 0.00625            | 0.0125                | 42.27     | 41.7       | 24.18              | 17.89          | 19.66        | 29.14               |
| OpenAuditLLM | 0.5        | 0.025                | 0.025              | 0.0125             | 0.025                 | 41.53     | 55.05      | 25.49              | 16.97          | 20.51        | 31.91               |
| OpenAuditLLM | 0.5        | 0.0375               | 0.0375             | 0.01875            | 0.0375                | 41.98     | 53.91      | 24.84              | 16.97          | 18.8         | 31.3                |
| OpenAuditLLM | 0.5        | 0.05                 | 0.05               | 0.025              | 0.05                  | 41.78     | 57.79      | 26.14              | 16.97          | 23.08        | 33.152              |
| OpenAuditLLM | 0.5        | 0.0125               | 0.0125             | 0.025              | 0.0125                | 40.83     | 50.03      | 24.84              | 17.43          | 29.06        | 32.438              |
| OpenAuditLLM | 0.5        | 0.025                | 0.025              | 0.05               | 0.025                 | 41.91     | 51.11      | 24.84              | 16.97          | 23.08        | 31.582              |
| OpenAuditLLM | 0.5        | 0.0375               | 0.0375             | 0.075              | 0.0375                | 42.11     | 50.92      | 24.84              | 16.97          | 24.79        | 31.926              |
| OpenAuditLLM | 0.5        | 0.05                 | 0.05               | 0.1                | 0.05                  | 42.29     | 47.68      | 24.84              | 16.51          | 23.08        | 30.88               |
| OpenAuditLLM | 0.5        | 0.0125               | 0.0125             | 0.0125             | 0.00625               | 42.12     | 42.15      | 24.18              | 17.89          | 17.95        | 28.858              |
| OpenAuditLLM | 0.5        | 0.025                | 0.025              | 0.025              | 0.0125                | 41.45     | 62.3       | 24.84              | 16.51          | 23.93        | 33.806              |
| OpenAuditLLM | 0.5        | 0.0375               | 0.0375             | 0.0375             | 0.01875               | 41.57     | 60.01      | 26.14              | 16.97          | 28.21        | 34.58               |
| OpenAuditLLM | 0.5        | 0.05                 | 0.05               | 0.05               | 0.025                 | 41.75     | 61.09      | 25.49              | 17.43          | 23.08        | 33.768              |
| OpenAuditLLM | 0.5        | 0.0125               | 0.0125             | 0.0125             | 0.025                 | 41.86     | 42.66      | 22.88              | 19.27          | 16.24        | 28.582              |
| OpenAuditLLM | 0.5        | 0.025                | 0.025              | 0.025              | 0.05                  | 41.29     | 52.77      | 24.18              | 18.81          | 21.37        | 31.684              |
| OpenAuditLLM | 0.5        | 0.0375               | 0.0375             | 0.0375             | 0.075                 | 41.13     | 55.88      | 24.84              | 16.97          | 25.64        | 32.892              |
| OpenAuditLLM | 0.5        | 0.05                 | 0.05               | 0.05               | 0.025#                | 41.49     | 56.83      | 24.18              | 17.89          | 26.5         | 33.378              |

# Quick start

Directory Structure

---
├─evaluation <br>
│  ├─corpus <br>
│  └─project <br>
│      ├─finlm_eval <br>
│      ├─scripts <br>
│      └─tasks #evaluation tasks <br>
│          ├─chinese <br>
│          │  ├─fineval_fewshot <br>
│          │  ├─fineval_zeroshot <br>
│          │  ├─regClassification <br>
│          │  ├─regClassification_zeroshot <br>
│          │  ├─regQa <br>
│          │  └─regQa_zeroshot <br>
│          └─plutus <br>
└─results <br>

---

## Model download

coming soon...
