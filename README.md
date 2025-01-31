# Contextual and Syntactic Impact on Sarcasm Detection

## Overview
This project investigates the impact of contextual information and syntactic structure on sarcasm detection. By implementing a hierarchical BERT-based model and conducting experiments on a Reddit sarcasm dataset, we examine how context size and syntactic features affect classification accuracy.

## Dataset
The dataset used in this project is sourced from the ACL FigLang Workshop 2020, which consists of Reddit posts labeled as sarcastic or non-sarcastic. The dataset includes both response text and a variable number of preceding utterances providing context.

## Model Architecture
The sarcasm detection model is built using a **Hierarchical BERT Architecture**, consisting of:
1. **Sentence Encoding Layer**: BERT encodes context utterances and responses.
2. **Context Summarization Layer**: A 2D convolution reduces dimensionality.
3. **Context Encoder Layer**: A BiLSTM captures sequential dependencies.
4. **CNN Layer**: Captures relationships between the response and context.
5. **Fully Connected Layer**: Outputs sarcasm probabilities using a sigmoid function.

The model is trained using **binary cross-entropy loss** and the **AdamW optimizer**.

## Experiments
### 1. Impact of Context Length
- Models were trained with context sizes ranging from **2 to 6 utterances**.
- Results show **peak accuracy at 3 utterances (69.59%)**, with performance declining beyond this point due to noise.

### 2. Role of Syntactic Features
- Additional syntactic features extracted using **SpaCy** (negations, rhetorical questions, exclamations, modifiers).
- Results show **no improvement in accuracy** (64%) compared to the base model, indicating that **BERT's attention mechanism inherently captures syntactic relationships**.

## Results
| Model                      | Accuracy |
|----------------------------|----------|
| Hierarchical BERT (Main)   | 64%      |
| Logistic Regression        | 59%      |
| Simplified Hierarchical Baseline | 49% |
| Contextual Model (3 utterances) | 69.59% |
| Syntax-Sensitive Model     | 64%      |

- **Confusion Matrices and Training Curves**: Available in the `results/` folder.

## Limitations
- **Dataset is Reddit-specific**, limiting generalizability.
- **English-only data**, may not capture sarcasm nuances in other languages.
- **Computational constraints** prevented extensive hyperparameter tuning.

## Future Work
- **Cross-platform and multilingual dataset** integration.
- **Hyperparameter optimization** for better performance.
- **Exploring multimodal sarcasm detection** using images, emojis, and speech tone.

## Ethics Statement
- The dataset may contain politically or socially sensitive content; we maintain a neutral stance.
- The project aims for **academic research** only and discourages unethical uses of NLP technology.

## Contributors
- **Simon**: Model implementation, training, and testing.
- **Leen**: Syntactic structure experiment.
- **Idris**: Contextual information experiment.
- **All members** contributed to writing the report.



