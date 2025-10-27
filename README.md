# dehomogenized-recommender：> *"From Echo Chambers to Exploration"*
A hybrid recommender system that combats homogenization through entropy-based personalized diversification.

# 🎬 Adaptive-Diversity-Recsys  
*A hybrid recommender system to reduce content homogenization using entropy-aware diversification.*

---

## 🌍 Project Overview
Most recommender systems optimize only for accuracy, leading to homogenization — users are repeatedly exposed to the same popular items or genres.  
This project aims to **balance accuracy and diversity** by introducing a **personalized diversification module**, where the diversification strength is adapted based on each user's taste entropy.

---

## 🚀 Key Features
✅ Hybrid model combining **Collaborative Filtering (CF)** + **Content-Based Filtering (CB)**  
✅ **Entropy-based personalization:** users with more repetitive behavior receive stronger diversification  
✅ **Year-normalized novelty** & **genre entropy** to reveal homogenization  
✅ Comprehensive evaluation: **NDCG, Precision/Recall, ILD, Coverage, Novelty, Calibration, Exposure Gini**

---

## ⚙️ How to Run
1. Clone the repository:
```bash
git clone https://github.com/your-username/adaptive-diversity-recsys.git
cd adaptive-diversity-recsys
````

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Download MovieLens 25M dataset and place it under `./data/`.

4. Run notebooks in order (1 → 5).

---

## 📊 Evaluation Metrics

| Category        | Metrics                                                   |
| --------------- | --------------------------------------------------------- |
| Accuracy        | NDCG@10, Recall@10, Precision@10                          |
| Diversity       | ILD@10 (intra-list diversity), Catalog Coverage           |
| Novelty         | Year-normalized Novelty (−log popularity per year)        |
| Calibration     | KL/EMD between user genre history and recommendation list |
| Fairness / Bias | Exposure Gini Index, Popularity Concentration             |

---

## 🧠 Innovation Highlight

> **Personalized Entropy-Aware Diversification**
> Instead of using a fixed λ in MMR, we define:
> [
> λ_u = \sigma(a - b \cdot H_u / H_{max})
> ]
> where (H_u) is the user’s short-window genre entropy.
> → Users with low diversity get more exploration; high-diversity users stay relevant.

