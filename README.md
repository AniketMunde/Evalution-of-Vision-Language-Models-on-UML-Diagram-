# **Evaluation of Vision-Language Models on UML Diagrams**

This project evaluates the capability of Vision-Language Models (VLMs) such as Qwen2VL, LLAVA 1.6, and Kosmos-2 to comprehend UML diagrams and generate semantically meaningful natural language descriptions. It incorporates a custom Chain-of-Thought (CoT) prompting mechanism and GPT-4o-mini as an evaluation judge.

---

## **Abstract**

This research explores the use of VLMs in analyzing UML diagrams—key components in software engineering. By benchmarking models like Qwen2VL, LLAVA 1.6, and Kosmos-2 on a custom dataset of 20 UML diagrams with 100 questions, this study highlights their strengths and weaknesses. Qwen2VL achieved the highest pass rate of 66%, followed by LLAVA 1.6 and Kosmos-2. Future work includes improving dataset quality, model efficiency, and contextual comprehension.

---

## **Repository Structure**

### **1. Kosmos-2**

- **Files:**
  - `Kosmos2_single_image.ipynb`: Evaluates Kosmos-2 on single UML images.
  - `kosmos_generated_answers.json`: Generated answers by Kosmos-2.
  - `kosmosdataset.ipynb`: Script for running Kosmos-2 dataset processing and evaluation.

### **2. Llava-1.6**

- **Files:**
  - `llava1.6dataset.ipynb`: Script for running Llava-1.6 dataset processing and evaluation.
  - `llava_1.6_Single_Image.ipynb`: Evaluates Llava-1.6 on single UML images.
  - `llava_generated_answers.json`: Generated answers by Llava-1.6.

### **3. Qwen2-VI**

- **Files:**
  - `Qwen2vl_Single_Image.ipynb`: Evaluates Qwen2VL on single UML images.
  - `answers_with_qwen2vl.csv`: Qwen2VL detailed answers in CSV format.
  - `qwen2vl_generated_answers.csv`: Qwen2VL generated answers in CSV format.
  - `qwen2vl_generated_answers.json`: JSON file of generated answers by Qwen2VL.
  - `qwen2vldataset.ipynb`: Script for running Qwen2VL dataset processing and evaluation.

### **4. Dataset**

- **Files:**
  - UML Images: `datasetUML1.png` to `datasetUML20.png`.

### **5. Supporting Files**

- `1.jpg`: Sample UML class diagram for single image evaluation.
- Environment setup scripts: `0.12.0`, `0.26.0`.
- Combined dataset Files in both Format:
  - `backupcombined_dataset.json`: Combined dataset with questions, ground truth, and generated answers.
  - `backupconverted_dataset.csv`: Converted dataset for analysis.
- `dataset_convert.ipynb`: Converts datasets from JSON to CSV or vice versa .

---

## **Setup Instructions**

### **1. Environment Setup**

Install required Python libraries:

```bash
pip install numpy pandas torch transformers matplotlib
```

### **2. Running Evaluation Scripts**

- For **Kosmos-2**:
  ```bash
  python Kosmos2_single_image.ipynb
  ```
- For **Llava-1.6**:
  ```bash
  python llava_1.6_Single_Image.ipynb
  ```
- For **Qwen2-VI**:
  ```bash
  python Qwen2vl_Single_Image.ipynb
  ```

### **3. Running Dataset Processing Scripts**

- For **Kosmos-2 Dataset Processing**:
  ```bash
  python kosmosdataset.ipynb
  ```
- For **Llava-1.6 Dataset Processing**:
  ```bash
  python llava1.6dataset.ipynb
  ```
- For **Qwen2-VI Dataset Processing**:
  ```bash
  python qwen2vldataset.ipynb
  ```

### **4. Dataset Conversion**

To convert datasets from JSON to CSV, run:

```bash
python dataset_convert.ipynb
```

---

## **Evaluation Pipeline**

The evaluation uses a customized Chain-of-Thought (CoT) prompting mechanism guided by GPT-4o-mini as the evaluation judge. This method ensures a semantic alignment between model-generated and ground-truth answers, prioritizing intent over stylistic differences.

### **Chain-of-Thought Prompting**

The CoT prompting mechanism guides the evaluation process as follows:

1. **You are an evaluation assistant tasked with assessing a model's generated answer against a ground truth answer. Your primary focus is on the overall meaning and intent, not the exact wording, phrasing, or structure.**

### **Step-by-Step Evaluation Process**:

1. **Read Carefully**: Understand the question, the model's answer, and the ground truth answer fully.
2. **Identify Key Information**:
   - Extract the critical facts or ideas conveyed in the ground truth answer.
   - Compare these facts with the model's answer.
3. **Focus on Semantic Similarity**:
   - If the model's answer conveys the same meaning, intent, and key details, even if rephrased or reorganized, mark it as **Pass**.
   - Minor omissions or stylistic differences should be ignored **as long as they do not alter the core meaning**.
4. **Fail Conditions**:
   - The answer introduces contradictions or incorrect facts.
   - The model omits critical details that are central to the ground truth.
   - The overall meaning changes significantly or becomes unclear.
5. **Edge Cases**: If the model’s answer is incomplete but still accurate for the part it covers, and the missing details are non-critical, lean toward marking it as **Pass**.

### **Output Format**:

1. Final Decision: Pass/Fail
2. Explanation: Provide a clear, step-by-step justification for your decision. Highlight key similarities and any differences, and explain why you marked the answer as correct or incorrect.

### Input Example:

- Question: {{item.question}}
- Model's Answer (qwen2vl): {{item.generated\_answer\_qwen2vl}}
- Ground Truth Answer: {{item.ground\_truth\_answer}}

---

The evaluation uses a customized Chain-of-Thought (CoT) prompting mechanism guided by GPT-4o-mini as the evaluation judge. This method ensures a semantic alignment between model-generated and ground-truth answers, prioritizing intent over stylistic differences.

### **Dataset Details**

- **Total UML Diagrams:** 20.
- **Total Questions:** 100 (5 questions per image).
- **Data Formats:** JSON and CSV.
- **Metrics:**
  - Accuracy
  - Semantic similarity
  - Execution time
### ** Result Images** 
**Single Image:**
Qwen2-vl-
![finaloutput](https://github.com/user-attachments/assets/1bdf4070-d5cf-4b37-8d39-b8a97b23553d)

Llava-1.6-
![finaloutput](https://github.com/user-attachments/assets/9b3ccb56-f2eb-4706-86b7-fb105b494b13)

Kosmos-2
![finaloutput](https://github.com/user-attachments/assets/9ae952dc-83b8-45ef-aa02-4b64aa745541)




**Dataset-**
Kosmos-2 Results-
![KOSMOSRESULT](https://github.com/user-attachments/assets/58f740e7-8379-47ed-91f7-a667bd44c0ef)

LLava-1.6 Results-
![LLAVARESULT (1)](https://github.com/user-attachments/assets/99c2b61e-fc6b-4ed1-ae57-0e207f5e90d4)

Qwen2-VL Results-
![QWEN2VL (1)](https://github.com/user-attachments/assets/b76d9f17-0417-445f-ad63-0f90cbc8e58b)


### **Results Summary**

- **Qwen2VL:**
  - Pass Rate (Dataset Evaluation on GPT-4o-mini): 66%.
  - Strength: Accurate, fast (Execution time for a single image: 13.51 seconds per query).
  - Weakness: Limited speculative reasoning.
- **LLAVA 1.6:**
  - Pass Rate (Dataset Evaluation on GPT-4o-mini): 45%.
  - Strength: Handles simpler tasks efficiently.
  - Weakness: Struggles with complex tasks.
  - Execution Time (Single Image): 23.10 seconds per query.
- **Kosmos-2:**
  - Pass Rate (Dataset Evaluation on GPT-4o-mini): 44%.
  - Strength: Direct and clear public methods.
  - Weakness: Insufficient detail.
  - Execution Time (Single Image): 112.85 seconds per query.

---

## **Contributors**

- **Aniket Ramchandra Munde**: MSc. Artificial Intelligence and Robotics, Hof University of Applied Science, Germany.

---

## **Future Scope**

- Expand datasets with high-quality annotations.
- Develop advanced VLM architectures for better semantic alignment.
- Improve computational efficiency for real-time applications.
- Introduce domain-specific pretraining for better contextual understanding.

---

## **License**

This project is licensed under the MIT License.



