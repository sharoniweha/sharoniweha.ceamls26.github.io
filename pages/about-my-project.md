---
layout: project
title: Cross-View Multi-Graph Contrastive Learning with LLM-Guided Knowledge Initialization for Predicting Antidepressant Treatment Response in Major Depressive Disorder
permalink: /about-my-project.html

subtitle: 
project_title: "My Summer Research Project"

problem: |
  Major Depressive Disorder (MDD) is a leading cause of disability worldwide, yet finding the right antidepressant remains a frustrating process of trial and error. Currently, between one-third and one-half of patients do not respond to the first medication they are prescribed. Because doctors must wait several weeks to observe whether a treatment is working based on subjective symptom surveys, patients often endure months of ineffective therapy and prolonged suffering before a better alternative is tried. There is a critical, urgent need to transition psychiatry toward personalized care by predicting a patient's treatment response using objective biological signals before therapy even begins.

  High-throughput biological data—specifically "multi-omic" layers that capture a patient's DNA, gene expression, and chemical modifications simultaneously—holds the molecular signatures needed to make these predictions. However, current computational methods fail to use this data effectively. Traditional machine learning treats complex, interconnected biological networks as flat lists, discarding vital relationship structures. Furthermore, massive datasets like genomics completely drown out smaller but highly informative layers like gene expression, and standard AI models easily break down and overfit when trained on massive feature spaces with very small groups of patients (the High-Dimensional, Low-Sample-Size problem). 

  This project addresses these critical gaps by introducing a robust, network-aware computational framework. By integrating multiple distinct biological views, correcting for data scale imbalances, and stabilizing learning in small clinical groups, this work aims to extract reliable molecular signatures that can accurately anticipate antidepressant treatment response.

approach: |
  We will address this problem using a structured, six-phase bioinformatics pipeline:

  - Phase 1: Establish Baseline Rigor — We will implement four classical reference models (including Penalized Logistic Regression, XGBoost, and Non-Negative Matrix Factorization) on a matched 111-patient clinical cohort to establish a strict "decision gate" that our advanced model must statistically outperform.
  - Phase 2: Multi-Omic Graph Construction — Instead of flat vectors, we will map patient data into three 3D network structures (patient-similarity graphs) based on cosine similarity, alongside a biologically grounded gene-to-pathway graph utilizing a 1,087-geneset prior matrix.
  - Phase 3: LLM-Guided Knowledge Initialization — To keep the model from overfitting on a small patient sample, we will inject external biomedical knowledge by initializing gene nodes with fixed, precomputed text embeddings from a frozen language model (GenePT/OpenAI ada-002) applied to NCBI Gene summaries. 
  - Phase 4: Architecture and Joint Training — We will build the MV-GCLLLM framework in PyTorch Geometric, projecting all biological views to an equal hidden dimension to prevent genomic dominance. We will jointly optimize a supervised classification head alongside a self-supervised, three-way InfoNCE contrastive loss to align and synchronize the patient views.
  - Phase 5: Evaluation and Bias Sensitivity — Models will be rigorously evaluated under a repeated, nested stratified k-fold cross-validation protocol. We will also run an in-fold feature re-filtering sensitivity analysis to eliminate any potential ascertainment bias or data leakage inherited from the source dataset.
  - Phase 6: Biological Validation — Using post-hoc gradient attribution, we will rank predictive features and map them back to specific biological pathways via DAVID and KEGG. We will treat the recovery of known immune and inflammatory signatures as an internal positive control to ensure the AI learned genuine biology rather than cohort artifacts.

outcome: |
  By the end of the program, we expect to produce an end-to-end bioinformatics pipeline implemented in PyTorch Geometric as a working computational prototype. The primary artifact will be the MV-GCLLLM framework, complete with documented preprocessing scripts that map asymmetric multi-omic layers (SNPs, expression, methylation) to a language-model-guided, topology-aware network topology.

  Additionally, the findings and performance benchmarks of this architecture against established baseline models will be compiled into a formal research poster and an academic short paper. This work will deliver a clear interpretation of the biological pathways driving the model's predictions, surfacing prioritized candidate biomarkers for psychiatric care. Ultimately, other researchers and bioinformaticians will be able to leverage this framework to stabilize deep learning on low-sample-size clinical cohorts and advance personalized, biomarker-driven treatment selection.
  
final_report_url: https://example.com/your-report.pdf

grad_mentor:
  name: Ricky Gole
  linkedin: https://www.linkedin.com/in/ricky-gole/

faculty_mentor:
  name: Dr. Jamell Dacon
  linkedin: https://www.linkedin.com/in/jamelldacon/
---
