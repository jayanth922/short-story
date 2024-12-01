
Link for Medium Article : https://medium.com/@jayanth.kalyanam/tnt-llm-transforming-text-mining-with-smarter-automation-b73a87c29118

Link for PPT : https://www.slideshare.net/slideshow/tnt-llm-text-mining-at-scale-with-large-language-models/273748006

Link for Video Demo : https://youtu.be/KmoPaYYR0OE

Link for Research Paper : https://arxiv.org/abs/2403.12173




# TnT-LLM: Text Mining at Scale with Large Language Models

### Authors
Mengting Wan, Tara Safavi, Sujay Kumar Jauhar, Yujin Kim, Scott Counts, Jennifer Neville, Siddharth Suri, Chirag Shah, Ryen W. White, Longqi Yang, Reid Andersen, Georg Buscher, Dhruv Joshi, Nagu Rangan  
**Affiliations**: Microsoft Corporation, University of Washington  

---

## Introduction

**Problem Statement**  
Text mining involves converting unstructured text into structured insights. Existing methods struggle with:
- **Manual Taxonomies**: Require expensive domain expertise and time-consuming curation.
- **Automated Clustering**: Often generates results that are difficult to interpret.

**Proposed Solution**  
TnT-LLM leverages Large Language Models (LLMs) to:
- Understand text contextually like humans.
- Process data at machine speed for scalability and efficiency.

---

## System Architecture

The modular design includes four key components:
1. **Text Summarization Module**: Prepares the dataset by condensing raw data into concise summaries.
2. **Taxonomy Generator**: Iteratively generates and refines structured taxonomies using LLMs.
3. **Data Labeling System**: Uses LLM-generated taxonomies to pseudo-label data.
4. **Lightweight Classifier**: Trains efficient, scalable models using pseudo-labeled data.

**Advantages**:
- Modular architecture allows for independent optimization and updates.
- Balances interpretability with scalability.

---

## Technical Implementation

### Taxonomy Generation Pipeline
- **Inspired by stochastic optimization**: Iteratively refines taxonomies, akin to how neural networks improve during training.
- **Key Parameters**:
  - **Batch size**: 200 conversations.
  - **Taxonomy structure**: Parameters {𝝁, 𝚺}.
  - **Temperature settings**: 0.5 for generation, 0.2 for updates.

### Classification Tasks
1. **Intent Detection**: Classifies user intent into 10 categories.
2. **Domain Classification**: Categorizes conversations into 25 broader topics.

---

## Experimental Setup

### Dataset Design
- **Source**: Bing Copilot conversations.
- **Diversity**: Multilingual, open-domain dataset.
- **Split**:
  - **Phase 1**: 9,592 conversations for taxonomy generation.
  - **Phase 2**: 48,160 conversations for testing scalability.

---

## Evaluation Metrics

1. **Coverage**: Measures the percentage of data points classified.
2. **Label Accuracy**: Assesses how well labels match the text.
3. **Inter-Rater Reliability**: Compares system-generated labels with human annotations.

---

## Key Findings

### Ablation Studies
- **LLM Choice**:
  - GPT-4 significantly outperformed GPT-3.5-Turbo for intent detection.
  - For simpler domain classifications, performance was similar between the two.
- **Embedding Models**:
  - ada2 embeddings showed robust multilingual performance, capturing universal semantic features.

### Performance Analysis
- **Coverage**: >99.5% across datasets.
- **Accuracy**:
  - **Intent**: 0.746 (English), 0.725 (Non-English).
  - **Domain**: 0.733 (English), 0.673 (Non-English).
- **Latency**: <100ms per classification.

### Scaling Characteristics
- Resource utilization reduced by **85%** through pseudo-labeling.
- Processing capacity:
  - Batch: 10k texts per minute.
  - Real-time: <100ms per text.

---
