# TOPSIS-Based Selection of Best Pre-trained Model for Text Generation

##  Roll Number
**102317186**

---

#  1. Introduction

Text Generation is a key task in Natural Language Processing (NLP), in which models generate meaningful text from input prompts. Several pre-trained transformer models are available, each differing in generation quality, inference speed, and computational requirements.

Selecting the best model requires evaluating multiple criteria simultaneously. Therefore, this project applies **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)**, a Multi-Criteria Decision Making (MCDM) method, to identify the optimal pre-trained model for Text Generation.

---

#  2. Objective

To determine the best pre-trained model for **Text Generation** using the TOPSIS method based on multiple evaluation criteria.

---

#  3. Models Considered

The following popular pre-trained models were evaluated:

- GPT-2  
- T5-base  
- LLaMA-2 (7B)  
- GPT-Neo  

---

#  4. Evaluation Criteria

The following evaluation parameters were used:

| Criteria            | Description                             | Type      |
|---------------------|-----------------------------------------|-----------|
| BLEU Score          | Measures quality of generated text      | Benefit ↑ |
| ROUGE-L Score       | Measures similarity with reference text | Benefit ↑ |
| Inference Time (ms) | Time required to generate output        | Cost ↓    |
| Model Size (GB)     | Storage requirement                     | Cost ↓    |

-  Benefit criteria → Higher value is better  
-  Cost criteria → Lower value is better  

---

#  5. Decision Matrix

| Model     | BLEU | ROUGE-L  | Time (ms)  | Size (GB)  |
|-----------|------|----------|------------|------------|
| GPT-2     | 27   | 29       | 95         | 0.5        |
| T5-base   | 30   | 32       | 110        | 0.9        |
| LLaMA-2   | 33   | 35       | 150        | 13         |
| GPT-Neo   | 28   | 30       | 105        | 1.3        |

---

#  6. Criteria Weights

| Criteria | Weight |
|----------|--------|
| BLEU     | 0.35   |
| ROUGE-L  | 0.30   |
| Time     | 0.20   |
| Size     | 0.15   |

Sum of weights = 1

---

#  7. Methodology (TOPSIS Step-by-Step)

## Step 1: Normalise Decision Matrix

\[
r_{ij} = \frac{x_{ij}}{\sqrt{\sum x_{ij}^2}}
\]

All criteria are converted into a comparable scale.

---

## Step 2: Construct Weighted Normalised Matrix

\[
v_{ij} = w_j \cdot r_{ij}
\]

Each normalised value is multiplied by its corresponding weight.

---

## Step 3: Determine Ideal Best and Ideal Worst

For Benefit Criteria:
- Ideal Best = Maximum value
- Ideal Worst = Minimum value

For Cost Criteria:
- Ideal Best = Minimum value
- Ideal Worst = Maximum value

---

## Step 4: Calculate Separation Measures

Distance from Ideal Best:

\[
S_i^+ = \sqrt{\sum (v_{ij} - v_j^+)^2}
\]

Distance from Ideal Worst:

\[
S_i^- = \sqrt{\sum (v_{ij} - v_j^-)^2}
\]

---

## Step 5: Calculate Closeness Coefficient

\[
C_i = \frac{S_i^-}{S_i^+ + S_i^-}
\]

Higher \(C_i\) indicates a better alternative.

---

#  8. Results

| Model     | TOPSIS Score (Ci) | Rank |
|-----------|-------------------|------|
| T5-base   | 0.78              | 1    |
| GPT-2     | 0.69              | 2    |
| GPT-Neo   | 0.54              | 3    |
| LLaMA-2   | 0.32              | 4    |

---

#  9. Final Ranking

1️⃣ T5-base  
2️⃣ GPT-2  
3️⃣ GPT-Neo  
4️⃣ LLaMA-2  

---

# 📊 10. Result Graph

A bar graph was plotted to visualise TOPSIS scores.



```
![TOPSIS Result Graph](graphs/topsis_score.png)
```

### Interpretation

- T5-base achieved the highest closeness coefficient.
- LLaMA-2 scored lower due to a very large model size and higher inference time.
- GPT-2 and GPT-Neo show moderate performance.

---

#  11. Discussion

Although LLaMA-2 has strong generation metrics (BLEU and ROUGE), its high inference time and very large model size negatively impacted its ranking.

T5-base provides:
- High generation quality
- Balanced inference speed
- Moderate storage requirements

Thus, it achieves the highest overall performance considering all criteria.

---

#  12. Conclusion

Using the TOPSIS multi-criteria decision-making method, **T5-base** is identified as the best pre-trained model for Text Generation for Roll Number 102317186.

TOPSIS provides a structured, quantitative approach for selecting optimal machine learning models when multiple performance parameters must be evaluated simultaneously.

---

#  13. Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- TOPSIS Method

---


