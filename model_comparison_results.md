# LLM Domain Adaptation Results: Medical Q&A

**Research Prompt:** User: What are the primary risk factors for heart disease?
Assistant:

---
## 1. Baseline Model (Gemma-2B-IT)
The pre-trained model provides a generalized, conversational response typical of consumer AI.

```text
Sure, here are the primary risk factors for heart disease:

**1. Age:**
- The risk of heart disease increases with age, as plaque buildup and other risk factors accumulate over time.

**2. Family history:**
- Individuals with a family history of heart disease are more likely to develop the condition themselves.

**3. High blood pressure:**
- High blood pressure is a major risk factor for heart disease. High blood pressure can damage blood vessels and increase cholesterol levels.

**4. High cholesterol:**
- High cholesterol levels can contribute to plaque buildup in the arteries and increase the risk of heart disease.

**5. Obesity:**
- Being overweight or obese can increase the risk of heart disease due to increased inflammation and fatty deposits in the arteries.

**6. Smoking:**
- Smoking damages blood vessels and increases the risk of heart disease.

**7. Physical inactivity:**
- Lack of physical activity can contribute to weight gain, high blood pressure, and other risk factors for heart disease.

**8. Stress:**
- Chronic stress can raise blood pressure and increase inflammation, which can contribute to heart disease.

**9. Diabetes:**
- Diabetes can damage blood vessels and increase the risk of heart disease.

**10. High-fat diet:**
- A diet high in saturated and trans fats can increase cholesterol levels and contribute to plaque buildup in the arteries.

**11. Lack of sleep:**
- Sleep
```

---
## 2. Fine-Tuned Model (LoRA Adapted)
The fine-tuned model demonstrates a stylistic shift toward concise, domain-specific medical terminology.

```text
Heart disease is a major cause of death worldwide. The risk of heart disease increases with age, obesity, high blood pressure, high cholesterol, high triglyceride levels, diabetes, obesity, and smoking. Heart disease is also more common in men than in women.
```
