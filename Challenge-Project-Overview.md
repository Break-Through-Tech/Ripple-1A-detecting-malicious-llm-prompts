---

> ## Challenge Advisor: Update & Finalize Your Project Overview
>
> > 💡 **These grey text instructions are just for you, the team's Challenge Advisor; please delete them once you have completed the steps below.**
>
> We've pre-populated this Challenge Project Overview page — which is what will be shared with your Break Through Tech student team in August — using the details from your submission form. You should have received an email inviting you to join this repo as a Collaborator, enabling you to add files and make edits.
> 
> In order for your project to be finalized and assigned to a team, please:
> 1. **Review all sections below** and update or expand any content as needed, making sure to address the SME Feedback in the section immediately below. Look for square brackets to find the places below that require additional inputs from you (e.g., "About [Company / Org Name]").
> 2. **Add your dataset** to the [data folder](data) in this repo.
> 3. **Close the Issue assigned to you in this repo** to let us know that you have made your edits and the overview page is ready for final review. You can do this by going to the _Issues_ tab in the top left section of the menu above, add a comment that says "CA review complete", and click the button to Close the Issue. 
>
> If you're unfamiliar with how to edit a page like this in GitHub, check out [this tutorial](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/handson/edit-readme.html) for a quick overview (start with step 2 and only edit this page), and [this guide](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/markdown.html) on how to use Markdown to compose text.
>
>
> ❌ Remember that this is a public repo. Do NOT include: Proprietary data, PII, API keys, credentials, or anything confidential.

---
## 📋 BTT Internal Evaluation Notes
*(This section is for BTT staff and CAs only — remove before sharing with students)*

### Technical Vetting
| Check | Status | Notes |
| :--- | :--- | :--- |
| Python Compatibility | 🟢 | Tech stack relies on standard libraries (scikit-learn, Keras), which are fully compatible with Google Colab environments. |
| Data Readiness | 🟡 | Public datasets for prompt injection are often noisy and require significant manual cleaning and class balancing to avoid bias. |
| Resource Check | 🟢 | The project avoids heavy GPU compute or proprietary API dependencies, fitting well within free-tier Colab constraints. |

### Internal Scores
- **Student Fit Score:** 8/10
- **Technical Depth Score:** 7/10
- **Overall Recommendation:** REVISE

### Advisor Feedback Draft
This project offers a compelling, security-focused NLP application that perfectly aligns with current industry needs. To succeed in our 12-week model, I recommend focusing exclusively on a single vectorization approach (e.g., embeddings) to bypass the overhead of comparing too many feature extraction methods. Secondly, ensure students define a static 'threat landscape' early on to prevent them from chasing an infinite number of jailbreak variations. Please confirm these scoping guardrails to proceed.

---

# Detecting Malicious LLM Prompts: A Classifier for Prompt Injection and Jailbreak Attacks

**Company / Org:** Ripple  
**Challenge Advisor:** Naga Sujitha Vummaneni, nv262@cornell.edu  
**Program:** Break Through Tech AI Studio - Fall 2026  

---

## 🏢 About Ripple
Ripple is a technology-forward organization dedicated to securing the next generation of generative AI applications. They focus on identifying vulnerabilities in Large Language Models to ensure enterprise systems remain resilient against adversarial manipulation.

---

## 🎯 The Challenge
### Project Summary
This project involves developing a robust text classification system designed to detect and flag prompt injection and jailbreak attacks before they interact with a production LLM. By leveraging NLP techniques such as TF-IDF and word embeddings alongside supervised classifiers in scikit-learn and Keras, the team will create a security layer that mitigates the risk of unauthorized data access and command execution.

### Success Criteria
A working classifier evaluated with precision/recall/F1 and a confusion matrix, with explicit attention to the false-negative cost (a missed attack is worse than a false alarm), benchmarked against a baseline (e.g., logistic regression vs. the neural net), plus a short analysis of failure modes and dataset bias.

### Project Milestones
Use these milestones to guide your work. Your team will create a GitHub Projects board to track tasks within each milestone.

| Month | Milestone | Key Activities |
| :--- | :--- | :--- |
| September | Data Processing, EDA & Baseline Classification | • Ingest and inspect prompt injection datasets (PromptGame benchmark dataset).<br>• Clean text prompts and categorize attack vectors (direct injection, indirect injection, roleplay jailbreaks).<br>• Perform Exploratory Data Analysis (EDA) on prompt token distributions and attack patterns.<br>• Implement baseline classical NLP classifiers (TF-IDF + Logistic Regression / Naive Bayes) and establish evaluation metrics (Precision, Recall, F1-Score, False Positive Rate). |
| October | Deep Learning Modeling & Transformer Fine-Tuning | • Fine-tune pre-trained transformer models (e.g., DistilBERT, RoBERTa) for malicious prompt detection.<br>• Engineer specialized features for adversarial techniques (obfuscation, character swapping, roleplay framing, system prompt overrides).<br>• Perform hyperparameter tuning and threshold optimization to minimize false positives on benign user inputs. |
| November / December | Model Explainability, Guardrail UI & Capstone Deliverables | • Apply interpretability methods (SHAP / attention weights) to highlight specific trigger phrases causing adversarial classification.<br>• Develop an interactive Streamlit application or API wrapper to scan input prompts in real time and display threat risk scores.<br>• Package a clean, reproducible GitHub repository, comprehensive project documentation, and stakeholder presentation deck. |

### Stretch Goals
* **Real-Time Guardrail Middleware:** Integrate the prompt classifier as an automated interceptor layer that inspects and blocks malicious prompts before sending queries to downstream LLM APIs.
* **Adversarial Obfuscation Robustness:** Stress-test and fine-tune the classifier against advanced evasion techniques (e.g., Base64 encoding, ROT13, multilingual jailbreaks, and zero-width character insertion).
* **Synthetic Attack Generator:** Build a lightweight red-teaming tool that automatically generates synthetic prompt injection variants to continuously evaluate classifier boundaries.

> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset
**Name and Source:** Publicly sourced prompt-injection and jailbreak adversarial text repositories.  
**Format:** CSV, TSV, and JSON.  
**Size:** Under 1GB.  
**Location:** Internal project directory/shared repository link.  

### Key Details
- Labeled dataset of benign and adversarial text prompts (prompt-injection and jailbreak attempts collected from public repositories) available in CSV/TSV and JSON formats.
- Preprocessing requires addressing potential class imbalances, sanitizing raw string inputs, and ensuring consistent sequence lengths for vectorization.

---

## 🛠️ Suggested Approach
**ML Problem Type:** NLP & Classification  
**Recommended Libraries:**
- scikit-learn
- Keras
- Python
**Evaluation Metrics:** Precision, Recall, F1-Score, and Confusion Matrix metrics, specifically tuned to penalize false-negatives in high-security contexts.

---

## 📚 Resources to Get Started
The following resources will help your team understand the problem space and potential technical approaches for this project:
**Background Reading:**
- OWASP Top 10 for LLMs (Prompt Injection section).
**Technical Tutorials:**
- Scikit-learn text feature extraction documentation and Keras introductory guides for text classification.
**Code Examples:**
- Sample starter notebooks for text classification using embeddings in the Ripple internal codebase.

---

## 🤝 How We'll Work Together
**Check-ins:** During our biweekly 60-min AI Studio Lab Section meeting block (2nd and 4th week of every month)  
**Communication:** Slack or Microsoft Teams (as designated by the program)  
**Response time:** 24–48 hours for non-urgent inquiries  
**Recommended Tools:**
- **Coding:** Google Colab Free Tier  
- **Collaboration:** GitHub, Notion  
- **Virtual Meetings:** Zoom, Google Meet  

---

## 🚀 Getting Started
1. **Review this overview document** and note any questions for our first meeting.
2. **Begin reviewing the dataset** using the link provided in the Dataset section.
3. **Read the GitHub Projects documentation** [here](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects).

I'm excited to work with you!

---

## ❓ Questions?
Please bring any questions to our first meeting during the week of August 24th (Break Through Tech's Bridge to Studio - Session B).
