# Multi-Conditional Ranking with Large Language Models
This repository is the implementation for the paper "[Multi-Conditional Ranking with Large Language Models](https://arxiv.org/pdf/2404.00211)"

![alt text](https://github.com/rit-git/multi-condition-ranking/blob/main/figs/overview-exsir.jpg)

---

## 🛠️ **Dataset Construction Process**

The benchmark evaluates LLMs on a **multi-conditional ranking (MCR)** task, where the goal is to order items based on various unsorted conditions. Each item is paired with a *gold label* that identifies its category or feature value, forming the basis for determining the correct ranking. The dataset is organized around two item types—*token-level* (short text segments) and *paragraph-level* (up to 150 tokens)—and involves five distinct condition types:

- **Positional Conditions:**  
  Require placing items in specific positions using nuanced spatial language (e.g., “the last item from the left”), adding complexity beyond basic fixed placements.

- **Locational Conditions:**  
  Involve ranking items based on geographical attributes, with data drawn from sources such as T-REx and Dice job descriptions.

- **Temporal Conditions:**  
  Require ranking depend on dates—like birthdates or deadlines—with examples sourced from benchmarks including CACD, Dice, and SQuAD.

- **Trait-Based Conditions:**  
  Rankings are based on physical features (such as size or height) with items collected from resources like VEC and Amazon reviews.

- **Reason-Based Conditions:**  
  Demand logical or mathematical reasoning for ranking, using samples from Big-Bench and DROP.

For each condition type, 200 samples were generated, each pairing a condition with a randomly arranged set of items. To mimic realistic scenarios with conflicting priorities, additional conditions are introduced (e.g., a low-priority character count or an extra high-priority positional condition), resulting in 18 unique scenarios (varying by item count and condition combinations).

Upon assigning these priorities, the order of conditions is randomized to further increase the task's complexity, and samples from each condition type are combined to form the final dataset for each scenario. For clarity, samples where multiple items share the same character count are removed, resulting in approximately 1000 curated samples per scenario.


---

## 📝 **Data Source Attribution**

Our benchmarks build upon data derived from several publicly available datasets:

1. **T-REx**  
   - Source: [T-REx Website](https://hadyelsahar.github.io/t-rex/downloads/)  
   - License: **[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)**
     
2. **CACD**  
   - Source: [CACD Website](https://bcsiriuschen.github.io/CARC/)  
   - License: **Public Domain**

3. **VEC Dataset**  
   - Source: [VEC Repository](https://github.com/TobiasLee/VEC)  
   - License: **Public Domain**
  
4. **Big-Bench Dataset**  
   - Source: [Big-Bench Repository](https://github.com/google/BIG-bench)  
   - License: **[Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0)**

5. **Dice Job Description Dataset**  
   - Source: [Kaggle](https://www.kaggle.com/datasets/PromptCloudHQ/us-technology-jobs-on-dicecom)  
   - License: **[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)**

6. **SQUAD Dataset**  
   - Source: [SQUAD Website](https://rajpurkar.github.io/SQuAD-explorer/)  
   - License: **[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)**

7. **Amazon Reviews Dataset**  
   - Source-1: [Amazon Reviews Repository-1](https://github.com/nijianmo/recsys_justification)
   - License: **Public Domain**
   - Source-2: [Amazon Reviews Repository-2](https://github.com/google-research-datasets/MAVE?tab=readme-ov-file)  
   - License: **[Attribution-NonCommercial 4.0 International](https://creativecommons.org/licenses/by-nc/4.0/legalcode.en)**
     
8. **Drop Dataset**  
   - Source: [Drop Huggingface Page](https://huggingface.co/datasets/ucinlp/drop)  
   - License: **[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)**

**Please refer to the respective sources for detailed licensing terms.**

---

## 🧠 **Usage Guidelines**

- Use this dataset for **research and educational purposes**.  
- Commercial use may require additional permissions depending on source licenses.  

---

## ⭐ **Citation**

If you would like to cite our work, the bibtex is:


    @article{pezeshkpour2024multi,
    title={Multi-Conditional Ranking with Large Language Models},
    author={Pezeshkpour, Pouya and Hruschka, Estevam},
    journal={arXiv preprint arXiv:2404.00211},
    year={2024}
    }

---

## 📜 **Disclosure**
Embedded in, or bundled with, this product are open source software (OSS) components, datasets and other third party components identified below. The license terms respectively governing the datasets and third-party components continue to govern those portions, and you agree to those license terms, which, when applicable, specifically limit any distribution. You may receive a copy of, distribute and/or modify any open source code for the OSS component under the terms of their respective licenses, which may be CC license and Apache 2.0 license. In the event of conflicts between Megagon Labs, Inc., license conditions and the Open Source Software license conditions, the Open Source Software conditions shall prevail with respect to the Open Source Software portions of the software. You agree not to, and are not permitted to, distribute actual datasets used with the OSS components listed below. You agree and are limited to distribute only links to datasets from known sources by listing them in the datasets overview table below. You are permitted to distribute derived datasets of data sets from known sources by including links to original dataset source in the datasets overview table below. You agree that any right to modify datasets originating from parties other than Megagon Labs, Inc. are governed by the respective third party’s license conditions. All OSS components and datasets are distributed WITHOUT ANY WARRANTY, without even implied warranty such as for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE, and without any liability to or claim against any Megagon Labs, Inc. entity other than as explicitly documented in this README document. You agree to cease using any part of the provided materials if you do not agree with the terms or the lack of any warranty herein. While Megagon Labs, Inc., makes commercially reasonable efforts to ensure that citations in this document are complete and accurate, errors may occur. If you see any error or omission, please help us improve this document by sending information to contact_oss@megagon.ai.

