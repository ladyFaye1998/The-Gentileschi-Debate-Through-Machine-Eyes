<div align="center">

<a href="https://www.uffizi.it/en/artworks/judith-beheading-holofernes#gallery" target="_blank">
<img src="./judith-banner.jpg" alt="Artemisia Gentileschi - Judith Beheading Holofernes" width="100%" style="border-radius: 8px; margin-bottom: 10px;" />
</a>
<br>
<em><small>Image source: <a href="https://www.uffizi.it/en/artworks/judith-beheading-holofernes#gallery">Uffizi Galleries</a></small></em>

<br><br>

# 👁️ The Gentileschi Debate Through Machine Eyes
**A Dual-Model Machine Learning Framework for Resolving Baroque Art's Most Intractable Attribution Problem.**

*Research & Codebase by [Danielle Lesin](https://www.bgu.ac.il/en/people/lesindan/) for the M.A. in Art History and Visual Culture.*
*The Faculty of Humanities and Social Sciences, Ben-Gurion University of the Negev.*

**[Explore Findings Here!](https://ladyfaye1998.github.io/The-Gentileschi-Debate-Through-Machine-Eyes/index.html)**

</div>

---

## 📖 The Research Problem
The attribution of paintings between Orazio Gentileschi (1563–1639) and his daughter Artemisia (1593–after 1654) represents a notoriously complex diagnostic knot in Baroque connoisseurship. They shared a surname, a Roman workshop, training methods, and a Caravaggesque visual vocabulary. Their documented collaboration—particularly during their London overlap (1638–1640)—produced works of hybrid authorship that frequently resist binary classification.

In this research, I deployed convolutional neural networks to explore a specific question: **Can computational analysis isolate the individual technical signatures of a father versus a daughter, and what can we learn when those algorithms confront historically disputed canvases?**

---

## 🔬 Computational Methodology
This repository translates the qualitative observations of traditional connoisseurship (the "Morellian" method) into a constrained, quantifiable machine-learning pipeline. The goal is to augment human expertise with data-driven insights, not replace it.

### The Architecture & Pipeline
* **Dual-Model Framework:**
  1. **Artist-Specific Classifier:** Trained exclusively to differentiate authenticated works by Orazio vs. Artemisia.
  2. **Gender-Based Classifier:** Trained in parallel on a broad, balanced corpus of male and female painters to test for demographic stylistic patterns.
* **Network Backbone:** EfficientNet-B0 (with ResNet-50 validation), selected for its parameter efficiency to prevent overfitting on a scarce, highly curated historical dataset.
* **Art-Historical Preprocessing:** To mitigate the domain shifts of 400-year-old canvases and modern photography, the pipeline utilizes EXIF-aware orientation, intelligent padding to preserve aspect ratios, Contrast Limited Adaptive Histogram Equalization (CLAHE) in the LAB color space, and white-balance correction.
* **Uncertainty Quantification:** Rather than forcing binary outputs, the system utilizes softmax probability distributions and entropy calculations. If the machine encounters ambiguity—such as a collaborative workshop piece—it explicitly flags the work as requiring traditional human connoisseurship.

---

## 📊 Principal Findings & Insights

Based on the evaluation of 60 disputed works, the models generated insights that offer a new lens on centuries of art-historical scholarship:

### 1. Style as Individual Practice
The artist-specific model successfully distinguished between Artemisia and Orazio with **81.2% accuracy**. In contrast, the gender-based model struggled to generalize, hovering at **66.9%**. This provides quantitative evidence challenging essentialist assumptions about "gendered" artistic production. Artistic identity appears to manifest in highly specific individual technical habits, not broad demographic categories.

### 2. Identifying "Action Nodes"
The neural networks learned to identify patterns that mirror traditional conservation analysis. The model identified Artemisia by her concentration of pictorial energy at **"action nodes"**—steep tonal transitions at narrative focal points, wrists under tension, and irregular drapery compression. Conversely, Orazio was identified by his methodical, architectural execution: narrow specular highlights on satin (2-4mm) and geometrically predictable fold periods.

### 3. Algorithmic Observations on Disputed Works
The system flagged several anomalies that offer interesting hypotheses for future scholarly review:
* ***Young Jesus Sleeping on the Cross* (1601):** Currently attributed to Orazio, the model assigns it to Artemisia with **88% confidence**. Given the chronology, this points to either a dating error or suggests that Orazio's improvisational passages were heavily influenced by his daughter's stylistic development.
* ***Il ratto di Lucrezia* (1626):** Despite Medici ledgers documenting payment to Artemisia, the model attributes the execution to Orazio with **79% confidence**. This suggests a potential division of creative labor: Artemisia designing the psychological narrative, while Orazio executed the crystalline surface.
* **The London Period (1638-1640):** The model showed a **45% disagreement rate** on works from their London overlap, quantitatively supporting the historical consensus that these were genuine, collaborative workshop productions.

### 4. Documenting Algorithmic Blindspots
A crucial part of this research was documenting where the machine learning failed. The network proved hypersensitive to non-stylistic artifacts:
* **Institutional Signatures:** The model inadvertently learned to recognize documentation workflows, showing a bias toward Artemisia for Uffizi photographs, and a bias toward Orazio for Palazzo Barberini lighting setups.
* **Conservation Bias:** The model heavily weighted modern restoration interventions (mechanical inpainting, lack of historical craquelure) over original 17th-century brushwork.

---

## 🛠️ Repository Structure
* `/Artemisia/`, `/Orazio/`, `/Gender attribution/`: Contains the datasets (secure, questioned, workshop), CSV and JSON databases, HTML galleries, and Wikidata SPARQL queries. All images are fully sourced and cited within the companion site.
* `/trained_models/`: The compiled `.pth` weight files for the EfficientNet models.
* `/attribution_analysis_results/`: Saliency maps, confidence distributions, and evaluation metrics for the disputed corpus.
* `gentileschi_ml_attribution.py`: The core machine learning pipeline and evaluation script.

---
### 📝 Citation
*This research was completed for my M.A. thesis and is currently under peer review for academic journal publication. In the meantime, please reference this repository and the companion site for methodologies or dataset findings.*
