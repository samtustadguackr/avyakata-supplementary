# Appendix A — Summary of Formal Demonstration

## 1. Corpus and Environment
- **Text:** 般若波羅蜜多心經 (CBETA, T08, No. 251)  
- **Token Unit:** Chinese characters (色, 空, 無, 般若, 涅槃, etc.)  
- **Libraries:** `gensim 4.0+`, `scikit-learn 1.2+`, `matplotlib`

---

## 2. Model Structure

| Item | Setting Value | Purpose |
|------|----------------|----------|
| Algorithm | Skip-gram (Word2Vec) | Context-based meaning extraction |
| Vector Dimension | 50 | Calculation of distance between meanings |
| Window Size | 2 | Capture proximate co-occurrence relationships |
| Epoch | 100 | Compensation for small data |

---

## 3. Conceptual Simulation Code

> **Purpose:** Illustrate relational structure, not empirical validation.  
> **Note:** This code is a formal conceptual simulation, visualizing how relational meaning structures in Buddhist cognition can be represented as patterns in information space. It does not aim for statistical rigor.

```python
# Appendix A: Conceptual Simulation of Relational Patterns in the Heart Sutra
# Author: ___________ (2025)

from gensim.models import Word2Vec
import re

# 1. Sample text (Heart Sutra Chinese text)
text = """
色不異空 空不異色 色即是空 空即是色
受想行識 亦復如是 無無明 亦無無明盡 無智亦無得
以無所得故 菩提薩埵 依般若波羅蜜多故 心無罣礙
無罣礙故 無有恐怖 遠離顛倒夢想 究竟涅槃
"""

# 2. Tokenize Chinese characters (conceptual, not linguistic preprocessing)
tokens = re.findall(r'[\u4e00-\u9fff]', text)

# 3. Train small conceptual model (window defines relational proximity)
model = Word2Vec([tokens], vector_size=20, window=3, min_count=1, sg=1)

# 4. Display relational proximity for key philosophical terms
for word in ['空', '無', '色', '智']:
    print(f"Nearest to {word}:", model.wv.most_similar(word, topn=5))
