<!-- confidensia-lab — GitHub Profile README -->

<div align="center">

# ConfidensIA

**Technologies de confiance pour le secteur social et médico-social**

*Patrick Danto — Fondateur*

[🌐 confidensia.fr](https://www.confidensia.fr) · [LinkedIn](https://www.linkedin.com/in/patrick-danto-36408a380/) · [Hugging Face](https://huggingface.co/jmdanto) · [Zenodo](https://zenodo.org/records/17689395)

</div>

---

## Ce que nous construisons

ConfidensIA développe des briques d'IA spécialisées pour les ESSMS (établissements sociaux et médico-sociaux) — un secteur aux contraintes réglementaires fortes (CASF, RGPD), aux vocabulaires métier denses, et où l'IA généraliste atteint vite ses limites.

Notre parti pris : des systèmes où la rigueur technique et la lecture métier sont indissociables.

---

## Domaines d'expertise

### 🔒 Pseudonymisation fine-grained
Système hybride CamemBERT + règles expertes + gazetteers pour la pseudonymisation réversible de documents professionnels ESSMS.  
Taxonomie de **101 catégories d'entités identifiantes**, conçue spécifiquement pour le secteur médico-social français.  
Architecture *privacy by design* : les textes sont pseudonymisés localement avant tout appel LLM externe, puis dépseudonymisés localement — aucune donnée sensible ne quitte l'infrastructure.

→ [Article Zenodo](https://zenodo.org/records/17689395) · [Modèle sur Hugging Face](https://huggingface.co/jmdanto/titibongbong_camemBERT_NER)

### 🗺️ Enrichissement de données sociales et médico-sociales
Pipelines d'enrichissement sur la base FINESS (11 291 gestionnaires), croisement de sources publiques, qualification LLM et détection de signaux de tension sur le tissu institutionnel ESSMS.  
La connaissance du terrain — relations de tutelle, logiques de financement, nomenclatures — est intégrée directement dans les pipelines, pas ajoutée en post-traitement.

### 📊 Analyse budgétaire ESSMS automatisée
Parsing documentaire, application de règles tarifaires sectorielles (CPOM, dotations globales, tarification à l'acte) et analyse orchestrée par LLM sur les documents budgétaires ESSMS (CA, BP).  
Une brique qui suppose de lire simultanément un PDF de rapport financier et les circulaires DGCS correspondantes.

### 🔍 RAG sectoriel avec garde-fous métier
Système de RAG (Retrieval-Augmented Generation) construit sur un corpus documentaire sectoriel dense : CCN 66/51, recommandations HAS/RBPP, jurisprudence TITSS/CNTSS, sources comparatives internationales.  
Dimension critique : intégration des logiques de plaidoyer, des garde-fous réglementaires et des zones de tension institutionnelle directement dans la chaîne de récupération et de génération.

---

## LaPlume — notre pipeline NER sectoriel

**titibongbong v1** (11 couches, pruning magnitude-based, FP16) — F1 global 86,4%  
**titibongbong v2** (9 couches, distillation 11L→9L) — F1 86,8% · 172 MB

Une obsession partagée : l'optimisation pour déploiement local, la minimisation de l'empreinte mémoire, et l'adaptation sectorielle plutôt que la généralisation à tout prix.

```
Performances sur corpus gold standard ESSMS (330 phrases, 448 entités) :
CRIT  (NIR, dates naissance, adresses complètes) : 95,6%  [objectif ≥ 95%  ✓]
ELEV  (identités, organismes)                    : 97,7%  [objectif ≥ 85%  ✓]
MOY   (établissements, codes)                    : 91,1%  [objectif ≥ 70%  ✓]
FAIB  (entités contextuelles)                    : 82,9%  [objectif ≥ 60%  ✓]
```

---

## Stack technique

`Python` `FastAPI` `Next.js` `PostgreSQL / pgvector` `Supabase` `Railway` `Scaleway`  
`CamemBERT` `spaCy` `Transformers` `LangChain` `Anthropic Claude` `Gemini Flash`

---

## Publications

- Danto, P. (2025). *ConfidensIA : Système de pseudonymisation fine-grained pour le secteur médico-social français*. Zenodo. [10.5281/zenodo.17689395](https://doi.org/10.5281/zenodo.17689395)

---

<div align="center">

*Les pipelines complets restent privés pour des raisons de développement commercial.*  
*Les briques publiées ici illustrent nos approches techniques et notre lecture du secteur.*

[confidensia.fr](https://www.confidensia.fr) · patrick.danto@confidensia.fr

</div>

---
---

<div align="center">

# ConfidensIA

**Trusted AI technologies for the French social and medico-social sector**

*Patrick Danto — Founder*

[🌐 confidensia.fr](https://www.confidensia.fr) · [LinkedIn](https://www.linkedin.com/in/patrick-danto-36408a380/) · [Hugging Face](https://huggingface.co/jmdanto) · [Zenodo](https://zenodo.org/records/17689395)

</div>

---

## What we build

ConfidensIA develops specialized AI components for ESSMS (French social and medico-social organizations) — a sector defined by dense regulatory constraints (CASF, GDPR), highly specific professional vocabularies, and contexts where general-purpose AI quickly reaches its limits.

Our conviction: systems where technical rigor and domain expertise are inseparable.

---

## Areas of expertise

### 🔒 Fine-grained pseudonymization
Hybrid CamemBERT + expert rules + gazetteers system for reversible pseudonymization of ESSMS professional documents.  
**101-category taxonomy** of identifying entities, built specifically for the French medico-social sector.  
*Privacy by design* architecture: documents are pseudonymized locally before any external LLM call, then de-pseudonymized locally — no sensitive data leaves the infrastructure.

→ [Zenodo paper](https://zenodo.org/records/17689395) · [Model on Hugging Face](https://huggingface.co/jmdanto/titibongbong_camemBERT_NER)

### 🗺️ Social and medico-social data enrichment
Enrichment pipelines on the FINESS base (11,291 managers), cross-referencing public sources, LLM qualification and tension signal detection across the ESSMS institutional landscape.  
Domain knowledge — supervision relationships, funding structures, sector nomenclatures — is embedded directly into pipelines, not bolted on afterward.

### 📊 Automated ESSMS budget analysis
Document parsing, application of sector-specific pricing rules (CPOM, global funding, activity-based pricing) and LLM-orchestrated analysis of ESSMS financial documents.  
A component that requires reading a financial report PDF and the corresponding DGCS circulars simultaneously.

### 🔍 Sector RAG with domain guardrails
Retrieval-Augmented Generation built on a dense sector-specific corpus: CCN 66/51, HAS/RBPP recommendations, TITSS/CNTSS case law, international comparative sources.  
Critical dimension: advocacy logics, regulatory guardrails, and institutional tension zones are integrated directly into the retrieval and generation chain.

---

## LaPlume — our sector NER pipeline

**titibongbong v1** (11 layers, magnitude-based pruning, FP16) — F1 86.4%  
**titibongbong v2** (9 layers, 11L→9L distillation) — F1 86.8% · 172 MB

A shared obsession: optimization for local deployment, minimal memory footprint, and sector adaptation over generalization.

```
Performance on ESSMS gold standard corpus (330 sentences, 448 entities):
CRIT  (SSN, birth dates, full addresses)    : 95.6%  [target ≥ 95%  ✓]
ELEV  (identities, organizations)           : 97.7%  [target ≥ 85%  ✓]
MOY   (institutions, codes)                 : 91.1%  [target ≥ 70%  ✓]
FAIB  (contextual entities)                 : 82.9%  [target ≥ 60%  ✓]
```

---

## Tech stack

`Python` `FastAPI` `Next.js` `PostgreSQL / pgvector` `Supabase` `Railway` `Scaleway`  
`CamemBERT` `spaCy` `Transformers` `LangChain` `Anthropic Claude` `Gemini Flash`

---

## Publications

- Danto, P. (2025). *ConfidensIA: Fine-grained pseudonymization system for the French medico-social sector*. Zenodo. [10.5281/zenodo.17689395](https://doi.org/10.5281/zenodo.17689395)

---

<div align="center">

*Full pipelines remain private for commercial development reasons.*  
*Published components here illustrate our technical approaches and sector expertise.*

[confidensia.fr](https://www.confidensia.fr) · patrick.danto@confidensia.fr

</div>
