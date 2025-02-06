# **VIMMCQA: Vietnamese Medical Multiple-Choice Question Answering Dataset**

The **VIMMCQA** dataset is a Vietnamese medical multiple-choice question answering dataset designed for research in **medical machine reading comprehension (MRC)** and **domain-specific natural language processing (NLP)**. It provides complex, real-world medical questions requiring **reasoning and evidence-based decision-making**.

For more details, please refer to our accompanying [paper](#) (*if available*).

---

## **Dataset Description**

The **VIMMCQA** dataset consists of **10,601 question-answer pairs**, each supported by **annotated evidence**. It is designed to help train and evaluate models in medical NLP tasks requiring **domain-specific knowledge**.

The dataset is structured as follows:
- **Training Set:** 9020 samples 
- **Development Set:** 799 samples 
- **Test Set:** 800 samples 

Additionally, **VIMMCQA** includes a **comprehensive Vietnamese medical corpus** with:
- **8,153** expert-verified medical articles.
- **689 unique diseases** covering various specialties.
- **Multi-turn, context-rich questions** requiring in-depth medical knowledge.

---

## **Data Format**

The dataset is provided in **JSON format**, where each entry represents a multiple-choice question related to a **specific medical condition**. The format includes:

```json
{
  "id": "Unique Question ID",
  "disease": "Description of the disease",
  "info": "Additional medical background information about the disease",
  "question": "The medical question",
  "options": {
    "A": "Option A",
    "B": "Option B",
    "C": "Option C",
    "D": "Option D"
  },
  "answer": ["A"],
  "evidence": {
    "A": "Supporting evidence for option A",
    "B": "Supporting evidence for option B",
    "C": "Supporting evidence for option C",
    "D": "Supporting evidence for option D"
  }
}
```

### **Example Entry**
```json
{
  "id": "001",
  "disease": "Nhiễm trùng âm đạo khi mang thai",
  "info": "Trước khi mang thai, nhiễm trùng âm đạo tạo điều kiện thuận lợi cho vi khuẩn (E. coli, liên cầu khuẩn nhóm B) xâm nhập vào cơ thể. Những vi khuẩn này có thể tồn tại sâu bên trong trong suốt thai kỳ.",
  "question": "Chị Hương, 28 tuổi, đang mang thai được 4 tháng. Trước khi mang thai, chị đã được chẩn đoán mắc nhiễm trùng âm đạo. Nếu không được điều trị kịp thời, chị Hương có nguy cơ bị vỡ ối vào thời điểm nào trong thai kỳ?",
  "options": {
    "A": "Tháng thứ 3 của thai kỳ.",
    "B": "Tháng thứ 6 của thai kỳ.",
    "C": "Tháng thứ 8 của thai kỳ.",
    "D": "Bất kỳ thời điểm nào trong thai kỳ."
  },
  "answer": ["D"],
  "evidence": {
    "A": "Không có bằng chứng mạnh mẽ liên kết nhiễm trùng âm đạo trước khi mang thai với nguy cơ vỡ ối vào tháng thứ 3.",
    "B": "Không có bằng chứng kết luận rằng nguy cơ cao hơn vào tháng thứ 6.",
    "C": "Tháng thứ 8 là giai đoạn quan trọng, nhưng nguy cơ vẫn tồn tại trong suốt thai kỳ.",
    "D": "Nếu không được điều trị, nhiễm trùng âm đạo có thể kéo dài và làm tăng nguy cơ vỡ ối vào bất kỳ thời điểm nào trong thai kỳ."
  }
}

```

---

## **Dataset Features**
- **Vietnamese Medical MRC Task**: The dataset is **domain-specific**, focusing on Vietnamese medical question answering.
- **Multiple-Choice Format**: Questions have **single or multiple correct answers**.
- **Expert-Annotated Evidence**: Every question is **supported by expert-verified medical explanations**.
- **Structured JSON Format**: Standardized schema for **easy integration into NLP models**.
- **Diverse Medical Topics**: Covers **689 diseases** across different medical specialties.

---

## **Methods & Benchmark Results**

To evaluate model performance on **VIMMCQA**, we developed a **two-stage retriever-reader framework**:

1. **Retriever Stage**: Uses **BM25 (Lexical Search) + Dense Retrieval** to extract relevant passages from the corpus.
2. **Reader Stage**: Fine-tuned **large language models (LLMs)** process the retrieved evidence and generate answers.

Our best-performing model, **Qwen-2**, achieved:
- **Exact Match (EM): 72.88%**
---

## **Citation**
If you use **VIMMCQA**, please cite the following paper:

```bibtex
@article{nguyen2024VIMMCQA,
    title={VIMMCQA: A Vietnamese Medical Multiple-Choice Question Answering Dataset},
    author={Nhi Ngoc-Yen Nguyen, Phuong Dieu Nguyen, Tan Nhat Do, Huy Le Tu, Khanh Quoc Tran, Kiet Van Nguyen},
    journal={[Journal Name]},
    year={2024},
    url={#},
    abstract={Vietnamese machine reading comprehension or question answering, especially in tasks requiring reasoning over specialized domain knowledge like medical information, remains under-researched. To contribute to medical domain reading comprehension, we propose a new dataset and a new framework for low-resource languages like Vietnamese.}
}
```

---

## **License**
The **VIMMCQA** dataset is released under the **[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/)**.

- **✅ Research Use:** Allowed for non-commercial research.
- **❌ Commercial Use:** Not permitted.
- **🔄 Modifications:** Any derived datasets should be shared under the same license.

## **Availability** 
The supplementary material will be made publicly available upon acceptance.

---

## **Contact**
For any inquiries regarding **VIMMCQA**, please contact:

📩 **Email Addresses**:
- **Nhi Ngoc-Yen Nguyen**: [21521231@gm.uit.edu.vn](mailto:21521231@gm.uit.edu.vn)
- **Phuong Dieu Nguyen**: [21520091@gm.uit.edu.vn](mailto:21520091@gm.uit.edu.vn)
- **Tan Nhat Do**: [21522575@gm.uit.edu.vn](mailto:21522575@gm.uit.edu.vn)
- **Huy Le Tu**: [21522173@gm.uit.edu.vn](mailto:21522173@gm.uit.edu.vn)
- **Khanh Quoc Tran**: [khanhtq@uit.edu.vn](mailto:khanhtq@uit.edu.vn)
- **Kiet Van Nguyen**: [kietnv@uit.edu.vn](mailto:kietnv@uit.edu.vn)

---
