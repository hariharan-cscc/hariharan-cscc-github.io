---

# Machine Learning Portfolio: AI-Generated Test Data Generation

## 1. Two of the Seven Steps of Machine Learning

Machine learning (ML) follows seven steps: gathering data, preparing data, choosing a model, training, evaluation, hyperparameter tuning, and prediction ([The 7 Steps of Machine Learning](https://www.youtube.com/watch?v=WMsjl8ZRJsA)). Here are two, explained for a friend.

### Training

Imagine learning your grandmother's soup recipe. You make a batch, compare it to hers, adjust the salt, and try again. A model does the same with data. It makes a guess, checks how wrong it was, and adjusts slightly each round until its guesses are close.

### Evaluation

Before serving that soup at a party, you ask someone who has never tasted it for an honest opinion. In ML, we hold back data the model never saw during training and test it on that. If it only does well on data it memorized, it isn't ready.

## 2. The Application: AI-Generated Test Data

Software teams need realistic data to test applications. ML models can learn the patterns in a real database, such as formats, value ranges, and relationships between tables. They then generate new synthetic records that look and behave like real data but don't belong to real people.

### a. How ML Improves Existing Solutions

Teams traditionally either copy production data and mask it, or write scripts that produce fake values. Copying is risky because masking can miss sensitive fields. Scripts are slow to maintain and miss real-world edge cases. ML-generated data keeps the statistical patterns and table relationships of the original. It can be created on demand, including rare scenarios.

This connects directly to my work in Test Data Management. When test data is ready as soon as a CI/CD pipeline runs, teams stop waiting days for data refreshes.

### b. In Development or Actively Used?

Both. [Tonic.ai](https://www.tonic.ai/) is used in production by companies such as Everlywell, which cut its build process from 60 to 20 minutes. DataCebo's open-source [Synthetic Data Vault (SDV)](https://datacebo.com/sdv-dev/) handles single-table, relational, and time-series data and has over 4 million downloads. Investment is also growing: [NVIDIA acquired synthetic data startup Gretel in 2025](https://www.crn.com/news/ai/2025/nvidia-buys-synthetic-data-startup-gretel-to-boost-ai-llms-report).

## 3. Ethical Concern: Privacy Leakage

"Synthetic" doesn't automatically mean "private." Because the model learns from real records, it can memorize and leak details about real people, especially unusual ones. Researchers found that synthetic data either failed to prevent inference attacks or lost its usefulness ([Stadler et al., USENIX Security 2022](https://www.usenix.org/system/files/sec22-stadler.pdf)). In insurance or finance, that could expose a real customer's health or financial details.

Responsible use means measuring privacy risk instead of assuming it, using protections like differential privacy, and restricting access to the training data. Bias is a second concern: if real data underrepresents certain groups, the synthetic data will too, so applications may be poorly tested for those users.

## Reflection

Working in test data and DevOps, I see AI-generated data as a major speed boost that still needs production-level privacy controls.
