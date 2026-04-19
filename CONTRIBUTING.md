<!-- HEADER BANNER -->
<div align="center">

<img src="https://img.shields.io/badge/Contributions-Welcome-brightgreen?style=for-the-badge&logo=github" />
<img src="https://img.shields.io/badge/ML%20Project-Credit%20Card%20Fraud-blue?style=for-the-badge&logo=python" />
<img src="https://img.shields.io/badge/NSoC-2026-orange?style=for-the-badge" />

# 🤝 Contributing to Credit Card Fraud Detection Model

**We're thrilled you want to contribute!**
Every pull request, bug report, and suggestion makes this project better.
Please read this guide carefully before getting started.

</div>

---

## 📋 Table of Contents

| # | Section | Description |
|---|---------|-------------|
| 1 | [👋 Welcome](#-welcome) | Why contribute? |
| 2 | [🚀 Getting Started](#-getting-started) | Fork, clone, branch |
| 3 | [🗂️ Project Structure](#️-project-structure) | How the repo is organized |
| 4 | [⚙️ Development Setup](#️-development-setup) | Environment & dependencies |
| 5 | [💡 How to Contribute](#-how-to-contribute) | Types of contributions |
| 6 | [🧹 Coding Guidelines](#-coding-guidelines) | Standards & best practices |
| 7 | [📬 Submitting a Pull Request](#-submitting-a-pull-request) | Step-by-step PR guide |
| 8 | [🐛 Issue Guidelines](#-issue-guidelines) | How to report bugs & request features |
| 9 | [📜 Code of Conduct](#-code-of-conduct) | Community standards |

---

## 👋 Welcome

This is an open-source **Machine Learning project** aimed at detecting fraudulent credit card transactions using classification algorithms. We are part of the **NSoC'26** open-source initiative and actively welcome contributors of all skill levels.

> 💬 **First time contributing to open source?**
> No worries! Check out [this beginner guide](https://opensource.guide/how-to-contribute/) and look for issues tagged `good first issue` in our repo.

---

## 🚀 Getting Started

Follow these steps to set up the project on your local machine:

### Step 1 — Fork the Repository

Click the **Fork** button at the top-right of the GitHub repo page.

```
https://github.com/TUFAQUE/CREDIT-CARD-FRAUD-DETECTION-MODEL
```

> This creates a personal copy of the repo under your GitHub account.

---

### Step 2 — Clone Your Fork

```bash
git clone https://github.com/YOUR-USERNAME/CREDIT-CARD-FRAUD-DETECTION-MODEL.git
cd CREDIT-CARD-FRAUD-DETECTION-MODEL
```

---

### Step 3 — Add Upstream Remote

Keep your fork in sync with the original repo:

```bash
git remote add upstream https://github.com/TUFAQUE/CREDIT-CARD-FRAUD-DETECTION-MODEL.git
git remote -v   # verify both origin and upstream are set
```

---

### Step 4 — Create a New Branch

Always work on a separate branch — **never directly on `main`**:

```bash
git checkout -b feature/your-feature-name
# Examples:
# git checkout -b fix/duplicate-split-cell
# git checkout -b docs/add-contributing
# git checkout -b feat/fraud-prediction-api
```

---

## 🗂️ Project Structure

Here is how the repository is organized:

```
CREDIT-CARD-FRAUD-DETECTION-MODEL/
│
├── 📓 CreditCardModel.ipynb       ← Main notebook: EDA, preprocessing, training
│
├── 📁 dataset/                    ← Raw & processed data (not tracked in git)
│   └── creditcard.csv
│
├── 📁 models/                     ← Saved model files (.pkl, .joblib)
│   └── fraud_model.pkl
│
├── 📁 api/                        ← (Planned) Real-time prediction API
│   └── app.py
│
├── 📄 requirements.txt            ← Python dependencies
├── 📄 README.md                   ← Project overview & usage
├── 📄 CONTRIBUTING.md             ← This file
├── 📄 CODE_OF_CONDUCT.md          ← Community standards
└── 📄 SECURITY.md                 ← Security policy
```

> ⚠️ **Do not commit dataset files.** The `/dataset` folder is in `.gitignore`.

---

## ⚙️ Development Setup

### Prerequisites

Make sure the following are installed on your system:

| Tool | Minimum Version | Download |
|------|----------------|---------|
| Python | 3.8+ | [python.org](https://www.python.org/downloads/) |
| pip | Latest | Included with Python |
| Git | Any | [git-scm.com](https://git-scm.com/) |
| Jupyter | Latest | Via pip |

---

### Installation Steps

```bash
# 1. Create a virtual environment
python -m venv venv

# 2. Activate it
source venv/bin/activate          # macOS / Linux
venv\Scripts\activate             # Windows

# 3. Install all dependencies
pip install -r requirements.txt
```

---

### Core Libraries Used

```
pandas           → Data loading & manipulation
numpy            → Numerical operations
scikit-learn     → ML models, metrics, preprocessing
imbalanced-learn → SMOTE & class imbalance handling
matplotlib       → Plotting & visualization
seaborn          → Statistical data visualization
joblib           → Model saving & loading
jupyter          → Running .ipynb notebooks
```

---

### Running the Notebook

```bash
jupyter notebook CreditCardModel.ipynb
```

> 🔁 Always **Restart Kernel & Run All Cells** before committing to verify no errors.

---

## 💡 How to Contribute

There are many ways to contribute — pick what suits you best:

---

### 🐛 Bug Fix
Found something broken in the notebook or code?
- Open an issue first describing the bug
- Fix it on a new branch
- Submit a PR referencing the issue

### ✨ New Feature
Want to add a fraud prediction API, model persistence, or a new algorithm?
- Check existing issues to avoid duplication
- Open a `[Feature Request]` issue
- Discuss the approach before implementing

### 📊 Model Improvement
Have a better algorithm, preprocessing technique, or evaluation method?
- Document the improvement clearly in the notebook
- Show metrics comparison (before vs after)
- Set `random_state=42` for reproducibility

### 📝 Documentation
Improve README, fix typos, add docstrings, or write guides:
- Documentation PRs are always welcome
- Use clear, simple English

### ✅ Tests & Validation
Add unit tests or data validation scripts:
- Place tests in a `/tests` folder
- Use `pytest` for test scripts

---

## 🧹 Coding Guidelines

Follow these standards to keep the codebase clean, consistent, and reproducible:

---

### 🐍 Python Style

- Follow **[PEP 8](https://peps.python.org/pep-0008/)** conventions
- Use meaningful variable names (`X_train` not `x1`)
- Keep functions short and focused
- Add **docstrings** to all functions:

```python
def preprocess_data(df):
    """
    Scales features and removes duplicates.

    Args:
        df (pd.DataFrame): Raw transaction data

    Returns:
        pd.DataFrame: Cleaned and scaled dataframe
    """
    ...
```

---

### 📓 Notebook Hygiene

```
✅ Clear all outputs before committing
✅ Restart kernel and run all cells top-to-bottom
✅ Add markdown cells to explain each major step
✅ Keep cells small and focused
❌ Do not leave debugging print() statements
❌ Do not hardcode absolute file paths
```

---

### 🔒 No Data Leakage — Critical Rule

```python
# ✅ CORRECT — split first, then fit scaler
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)   # fit only on train
X_test  = scaler.transform(X_test)        # transform only on test

# ❌ WRONG — scaling before split causes data leakage
X_scaled = scaler.fit_transform(X)
X_train, X_test = train_test_split(X_scaled, ...)
```

---

### 🎲 Reproducibility

Always set random seeds:

```python
import random
import numpy as np

random.seed(42)
np.random.seed(42)

# In sklearn functions:
train_test_split(..., random_state=42)
RandomForestClassifier(random_state=42)
```

---

## 📬 Submitting a Pull Request

### Before You Submit — Checklist

- [ ] Code follows PEP 8 style
- [ ] Notebook runs without errors (Restart & Run All)
- [ ] No hardcoded paths or API keys
- [ ] No data leakage in preprocessing steps
- [ ] `random_state=42` set where needed
- [ ] Branch is up to date with `main`

---

### Sync Your Branch with Main

```bash
git fetch upstream
git checkout main
git merge upstream/main
git checkout your-branch-name
git rebase main
```

---

### Commit & Push

```bash
git add .
git commit -m "feat: add model persistence using joblib"
git push origin your-branch-name
```

---

### Commit Message Format

| Prefix | Use Case | Example |
|--------|----------|---------|
| `feat:` | New feature | `feat: add real-time fraud API` |
| `fix:` | Bug fix | `fix: remove duplicate train-test split` |
| `docs:` | Documentation | `docs: update README setup steps` |
| `refactor:` | Code restructure | `refactor: extract preprocessing to function` |
| `chore:` | Config / maintenance | `chore: update requirements.txt` |
| `test:` | Tests | `test: add unit test for scaler pipeline` |
| `perf:` | Performance improvement | `perf: optimize SMOTE oversampling` |

---

### Open the Pull Request

1. Go to your fork on GitHub
2. Click **"Compare & pull request"**
3. Set base branch to `main` of the original repo
4. Fill in the PR description:
   - What did you change?
   - Why was this change needed?
   - Link the related issue: `Closes #2`
5. Submit and wait for a review

---

## 🐛 Issue Guidelines

Before opening an issue, **search existing issues** to avoid duplicates.

---

### 🐞 Bug Report Template

```
**Describe the bug:**
A clear description of what went wrong.

**Steps to reproduce:**
1. Open CreditCardModel.ipynb
2. Run cell #X
3. See error

**Expected behavior:**
What should have happened.

**Environment:**
- OS: Windows 11 / macOS / Ubuntu
- Python version: 3.10
- Key library versions: scikit-learn==1.3.0
```

---

### ✨ Feature Request Template

```
**Problem this solves:**
What gap or limitation does this address?

**Proposed solution:**
What should be implemented and how?

**Alternatives considered:**
Any other approaches you thought of?
```

---

### 🏷️ Labels to Use

| Label | Meaning |
|-------|---------|
| `bug` | Something is broken |
| `enhancement` | Improvement to existing feature |
| `documentation` | Docs update needed |
| `good first issue` | Beginner-friendly |
| `help wanted` | Extra attention needed |
| `NSoC'26` | Part of NSoC initiative |

---

## 📜 Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](./CODE_OF_CONDUCT.md).

By contributing, you agree to:

- ✅ Use welcoming and inclusive language
- ✅ Respect differing viewpoints and experiences
- ✅ Accept constructive criticism gracefully
- ✅ Focus on what is best for the community
- ❌ No harassment, discrimination, or disrespectful behavior

Violations can be reported by opening a private issue or contacting the maintainer directly.

---

<div align="center">

## 🙌 Thank You for Contributing!

Every contribution — big or small — helps make fraud detection more accessible and robust.

<img src="https://img.shields.io/badge/Made%20with-%E2%9D%A4-red?style=flat-square" />
<img src="https://img.shields.io/badge/Open%20Source-Yes-brightgreen?style=flat-square" />
<img src="https://img.shields.io/badge/NSoC'26-Contributor-orange?style=flat-square" />

**Happy Contributing! 🚀**

</div>