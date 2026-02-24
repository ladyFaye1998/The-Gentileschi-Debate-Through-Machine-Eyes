<div align="center">

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b7/Artemisia_Gentileschi_-_Judith_Beheading_Holofernes_-_WGA8563.jpg/1200px-Artemisia_Gentileschi_-_Judith_Beheading_Holofernes_-_WGA8563.jpg" alt="Artemisia Gentileschi - Judith Beheading Holofernes" width="100%" style="border-radius: 8px; margin-bottom: 20px;" />

# 👁️ The Gentileschi Debate Through Machine Eyes
**A Dual-Model Machine Learning Framework for Resolving Baroque Art's Most Intractable Attribution Problem.**

[cite_start]*Research & Codebase for the Master of Arts Thesis, Ben-Gurion University of the Negev[cite: 1, 17].*

[cite_start]**[Explore the Interactive Findings Dashboard](https://ladyfaye1998.github.io/The-Gentileschi-Debate-Through-Machine-Eyes/index.html)** [cite: 45]

</div>

---

## 📖 The Research Problem
[cite_start]The attribution of paintings between Orazio Gentileschi (1563–1639) and his daughter Artemisia (1593–after 1654) represents a notoriously complex diagnostic knot in Baroque connoisseurship[cite: 33, 54]. [cite_start]They shared a surname, a Roman workshop, training methods, and a Caravaggesque visual vocabulary[cite: 55, 58]. [cite_start]Their documented collaboration—particularly during their London overlap (1638–1640)—produced works of hybrid authorship that fundamentally resist binary classification[cite: 59].

[cite_start]This project deploys convolutional neural networks to ask a precise question: **Can computational analysis isolate the individual technical signatures of a father versus a daughter, and what happens when those algorithms confront historically disputed canvases?** [cite: 69]

---

## 🔬 Computational Methodology
This repository does not simply apply generic computer vision to historical artifacts. [cite_start]It translates the qualitative observations of traditional connoisseurship (the "Morellian" method) into a highly constrained, quantifiable machine-learning pipeline[cite: 94, 322].

### The Architecture & Pipeline
* **Dual-Model Framework:**
  1. [cite_start]**Artist-Specific Classifier:** Trained exclusively to differentiate authenticated works by Orazio vs. Artemisia[cite: 34, 566].
  2. [cite_start]**Gender-Based Classifier:** Trained in parallel on a broad, balanced corpus of male and female painters to test for demographic stylistic patterns[cite: 34, 567].
* [cite_start]**Network Backbone:** EfficientNet-B0 (with ResNet-50 validation), selected for its parameter efficiency to prevent overfitting on a scarce, highly curated historical dataset[cite: 570, 571].
* [cite_start]**Art-Historical Preprocessing:** To mitigate the domain shifts of 400-year-old canvases and modern photography, the pipeline utilizes EXIF-aware orientation, intelligent padding to preserve aspect ratios, Contrast Limited Adaptive Histogram Equalization (CLAHE) in the LAB color space, and white-balance correction[cite: 580, 581, 582].
* [cite_start]**Epistemic Humility (Uncertainty Quantification):** Rather than forcing binary outputs, the system utilizes softmax probability distributions and entropy calculations[cite: 616, 618]. [cite_start]If the machine encounters ambiguity—such as a collaborative workshop piece—it explicitly flags the work as requiring traditional human connoisseurship[cite: 628, 636].

---

## 📊 Principal Findings & Insights

[cite_start]Based on the evaluation of 60 disputed works, the models generated insights that both validate and challenge centuries of art-historical scholarship[cite: 37, 730]:

### 1. The Fallacy of Gendered Style
[cite_start]The artist-specific model successfully distinguished between Artemisia and Orazio with **81.2% accuracy**[cite: 642]. [cite_start]In stark contrast, the gender-based model failed to generalize, hovering at a volatile **66.9%**[cite: 676]. 
* [cite_start]**Insight:** This provides quantitative evidence against essentialist assumptions regarding "gendered" artistic production[cite: 687, 923]. [cite_start]Artistic identity manifests in highly specific individual technical habits, not broad demographic categories[cite: 754, 983].

### 2. Quantifying Connoisseurship: "Action Nodes" vs. Architectural Regularity
The neural networks learned to identify exactly what master conservators look for. [cite_start]The model identified Artemisia by her concentration of pictorial energy at **"action nodes"**—steep tonal transitions at narrative focal points, wrists under tension, and irregular drapery compression[cite: 191, 276, 758]. [cite_start]Conversely, Orazio was identified by his methodical, architectural execution: narrow specular highlights on satin (2-4mm) and geometrically predictable fold periods[cite: 268, 269].

### 3. Radical Reattributions & Workshop Realities
The system flagged several high-confidence anomalies that demand scholarly reevaluation:
* [cite_start]***Young Jesus Sleeping on the Cross* (1601):** Currently attributed to Orazio, the model assigns it to Artemisia with **88% confidence**[cite: 783]. [cite_start]As she was eight years old at the time, this points to either a massive chronological dating error, or evidence that Orazio's improvisational passages (revealed by pentimenti) were heavily influenced by his daughter's stylistic development, not just the other way around[cite: 786, 791, 792].
* [cite_start]***Il ratto di Lucrezia* (1626):** Despite Medici ledgers documenting payment to Artemisia, the model attributes the execution to Orazio with **79% confidence**[cite: 814, 815, 817]. [cite_start]This suggests a highly sophisticated division of creative labor: Artemisia designed the psychological narrative, while Orazio executed the crystalline surface[cite: 818, 820].
* [cite_start]**The London Period (1638-1640):** The model showed a massive **45% disagreement rate** on works from their London overlap, quantitatively confirming what historians have long suspected: these were genuine, messy, collaborative workshop productions[cite: 766, 767].

### 4. Algorithmic Blindspots: What the Machine Got Wrong
A rigorous ML deployment must document its failure modes. [cite_start]The network proved hypersensitive to non-stylistic artifacts[cite: 39]:
* [cite_start]**Institutional Signatures:** The model learned to recognize documentation workflows, showing a +12% bias toward Artemisia for Uffizi photographs, and a +9% bias toward Orazio for Palazzo Barberini lighting setups[cite: 879].
* [cite_start]**Conservation Bias:** The model heavily weighted modern restoration interventions (mechanical inpainting, lack of historical craquelure) over original 17th-century brushwork, proving that computational attribution cannot function without corresponding material conservation reports[cite: 884].

---

## 🛠️ Repository Structure
* `/notebooks/`: Jupyter notebooks detailing the data harvesting, CLAHE preprocessing pipeline, and EfficientNet training loops.
* `/datasets/`: Metadata matrices for the 1,000+ image master corpus (excluding the physical images to comply with museum copyright restrictions).
* `/results/`: Visualizations of model predictions, probability distributions, and confidence/entropy scores for the disputed corpus.

---

## 🎓 About the Researcher
[cite_start]**Danielle Lesin** [cite: 8] [cite_start]is an Application Security Strategist, AI Researcher, and Art Historian holding an MA from Ben-Gurion University of the Negev [cite: 1] and an MA in Celtic Studies from the University of Wales Trinity Saint David. 

[cite_start]Bridging the gap between secure cloud architectures and classical humanities, her work focuses on leveraging machine learning not to replace human interpretation, but to quantify uncertainty and generate testable hypotheses in historical datasets[cite: 962].

---
### 📝 Citation
*As this research is currently unpublished, please reference this repository and the companion interactive dashboard for any citations regarding the methodology or dataset findings.*
