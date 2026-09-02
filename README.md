# Awesome Synthetic Data Generation [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

Synthetic, semi-synthetic, simulated, rendered, silver-standard, and automatically labeled data for knowledge graph extraction and scientific image understanding.

## Contents

- [Scope and Organization](#scope-and-organization)
- [Knowledge Graph Extraction](#knowledge-graph-extraction)
- [Scientific Image Understanding](#scientific-image-understanding)

## Scope and Organization

This list focuses on data creation rather than general-purpose extraction or generation systems. A resource belongs when synthetic, semi-synthetic, simulated, rendered, silver-standard, or automatically labeled data are a substantive contribution and are used for one of the two target areas below.

**Knowledge graph extraction** covers entity and relation annotations, relation triples, linked entities, attributes, graph-text pairs, silver knowledge graphs, and synthetic evaluation data for structured knowledge extraction.

**Scientific image understanding** covers scientific figures, plots, tables, multimodal papers, scientific-image classification and VQA, as well as simulated scientific imagery with ground truth for downstream analysis.

Each resource appears once in the section where its data-creation contribution is most useful. Labels such as **Method**, **Dataset**, **Benchmark**, and **Tool** indicate the resource's primary role rather than an exhaustive taxonomy.

## Knowledge Graph Extraction

### Synthetic and Generative Methods

- [RelationPrompt](https://github.com/declare-lab/RelationPrompt) ([paper](https://aclanthology.org/2022.findings-acl.5/)) - **Method.** Generates relation-conditioned sentences containing specified head entities, tail entities, and relation labels to train zero-shot relation-triplet extractors.
- [SynthIE](https://github.com/epfl-dlab/SynthIE) ([paper](https://aclanthology.org/2023.emnlp-main.96/)) - **Method.** Samples coherent triple sets from a knowledge graph and generates text that expresses those triples, producing paired training data for closed information extraction.
- [GenRDK](https://doi.org/10.1145/3589334.3645678) - **Method.** Prompts an LLM to generate relation-labeled long documents and filters noisy facts through cross-document consistency before training zero-shot document-level relation-triplet extractors.
- [KGAST](https://aclanthology.org/2024.kallm-1.5/) - **Framework.** Verbalizes knowledge graphs into synthetic documents, selects candidates by model voting, and derives entity, relation, evidence, event, and attribute annotations for information extraction.
- [CycleGT](https://github.com/QipengGuo/CycleGT) ([paper](https://aclanthology.org/2020.webnlg-1.8/)) - **Method.** Learns graph-to-text and text-to-graph mappings from non-parallel collections by iteratively creating and training on pseudo-parallel graph-text pairs.
- [From Graph to Text and Back](https://github.com/KamyarZeinalipour/round-trip-kg) ([paper](https://aclanthology.org/2026.acl-industry.140/)) - **Method.** Verbalizes knowledge-graph triples, reconstructs them from the generated text, and retains high-fidelity graph-text pairs for extractor fine-tuning.

### Silver, Automatically Labeled, and Synthetic Corpora

- [Distant Supervision for Relation Extraction without Labeled Data](https://aclanthology.org/P09-1113/) - **Method.** Introduces knowledge-base distant supervision for automatically labeling relation mentions in text without a manually annotated relation corpus.
- [DocRED](https://github.com/thunlp/DocRED) ([paper](https://aclanthology.org/P19-1074/)) - **Dataset.** Provides document-level entity and relation annotations together with a large distantly supervised split constructed from Wikipedia and Wikidata.
- [DocIE@XLLM25](https://github.com/nicpopovic/docie-xllm25) ([paper](https://aclanthology.org/2025.xllm-1.26/)) - **Dataset and method.** Automatically annotates Wikipedia abstracts with entities and relation triples to build reusable demonstrations for joint document-level information extraction.
- [DrugProt](https://doi.org/10.5281/zenodo.7252201) ([paper](https://doi.org/10.1093/database/baad080)) - **Dataset and silver knowledge graph.** Aggregates chemical-protein relation predictions over 2.3 million PubMed abstracts into a weighted silver-standard graph for biomedical relation extraction and knowledge-graph construction.
- [SynEL](https://doi.org/10.5281/zenodo.11470053) ([code](https://github.com/alik-kirillovich/synel)) - **Benchmark and dataset.** Generates or pseudonymizes dialogues with entity mentions, canonical identifiers, attributes, and relations for entity linking, named-entity recognition, and relation extraction.
- [iMAKS](https://zenodo.org/records/20075430) - **Synthetic dataset.** Simulates an industrial facility with SOPs, sensor records, rules, anomalies, and reference graph structure for multi-source knowledge and rule extraction evaluation.

### Synthetic Evaluation

- [Beyond Known Facts](https://github.com/Aethor/fiction) ([dataset](https://huggingface.co/collections/aeth0r/yago-temporal-knowledge-graph-extraction-datasets)) - **Benchmark.** Forecasts schema-consistent future temporal-knowledge-graph quadruples and verbalizes them into text for renewable, contamination-resistant extraction evaluation.

## Scientific Image Understanding

### Scientific Figures and Multimodal Documents

- [ACL-Fig](https://arxiv.org/abs/2301.12293) ([dataset](https://huggingface.co/datasets/citeseerx/ACL-fig)) - **Dataset.** Reports an automatically organized corpus of 112,052 ACL figures; the official release currently exposes the 1,671-figure manually labeled pilot used for 19-class scientific-figure classification.
- [OmniScience](https://huggingface.co/collections/UniParser/omniscience) ([paper](https://arxiv.org/abs/2602.13758)) - **Dataset.** Uses dynamically routed multimodal models to create dense, context-aware recaptions for 1.5 million scientific figures across more than ten disciplines.
- [MatMMExtract / MatSciFig](https://github.com/CMEG-IITR/matmmextract) ([dataset](https://huggingface.co/datasets/CMEG-IITR/MatSciFig)) - **Tool and dataset.** Extracts materials-science figures, detects panels, and generates taxonomy-guided subcaptions, categories, and summaries for multimodal training and retrieval.
- [Multimodal ArXiv](https://mm-arxiv.github.io/) ([paper](https://aclanthology.org/2024.acl-long.775/)) - **Dataset.** Automatically aligns 6.4 million scientific figures with 3.9 million author-written captions and adds GPT-4V-generated figure-grounded question-answer supervision.

### Scientific Plots, VQA, and Tables

- [PlotQA](https://github.com/NiteshMethani/PlotQA) - **Dataset and benchmark.** Renders 224,377 plots from real-world scientific data and instantiates 28,952,641 question-answer pairs for numerical plot reasoning.
- [SciGraphQA](https://github.com/findalexli/SciGraphQA) ([dataset](https://huggingface.co/datasets/alexshengzhili/SciGraphQA-295K-train)) - **Dataset.** Generates open-vocabulary, multi-turn dialogues grounded in graphs and context extracted from scientific papers for figure understanding and VQA.
- [SPIQA](https://huggingface.co/datasets/google/spiqa) ([paper](https://proceedings.neurips.cc/paper_files/paper/2024/hash/d74033a247989e8f6f3bf9e0c9629fb5-Abstract-Datasets_and_Benchmarks_Track.html)) - **Dataset and benchmark.** Combines machine-generated training, validation, and test-A questions with a manually curated test-A split and human-written test-B/test-C questions grounded in scientific figures, tables, and text.
- [SciClaimEval](https://sciclaimeval.github.io/) ([paper](https://aclanthology.org/2026.lrec-1.864/)) - **Dataset and benchmark.** Creates refuted examples by modifying authentic figure and table evidence while preserving the associated scientific claims, then validates the pairs through expert annotation.
- [PubTabNet](https://github.com/ibm-aur-nlp/PubTabNet) - **Dataset and benchmark.** Automatically matches table regions in PubMed Central papers to their XML and pairs cropped table images with structured HTML for table recognition.

### Synthetic Scientific Imaging and Simulation

- [Scientific Image Synthesis / SciGenBench](https://github.com/SciGenBench/SciGenBench) ([paper](https://arxiv.org/abs/2601.17027)) - **Benchmark and method.** Evaluates scientific-image generation and provides ImgCoder, an understand-plan-code workflow that renders verifiable diagrams for downstream multimodal reasoning.
- [DeepTrack 2.0](https://github.com/DeepTrackAI/DeepTrack2) ([paper](https://doi.org/10.1063/5.0034891)) - **Tool.** Composes parameterized objects, optics, aberrations, and noise to generate microscopy images with positions, classes, masks, trajectories, and other exact properties.
- [Construction Zone / HRTEM](https://github.com/lerandc/construction_zone) ([paper](https://www.nature.com/articles/s41524-024-01336-0)) - **Framework.** Generates nanoscale atomic scenes and physics-simulated HRTEM images with exact segmentation labels for synthetic-to-experimental materials-image analysis.
- [SimuScan](https://github.com/Rmillansol/SimuScan-AFMtools) ([generator](https://zenodo.org/records/18134911)) - **Tool and method.** Simulates AFM images with controllable morphology, exact masks, and instrument artifacts for segmentation, detection, and autonomous microscopy.
- [3DMSL](https://doi.org/10.18710/JX6JXF) ([code](https://github.com/bioailab/3DMSL)) - **Dataset.** Provides more than 27,000 EM-derived mitochondrial shapes and simulated fluorescence-microscopy views with 3D ground truth for segmentation and reconstruction.
- [Deep Learning for Image Sequence Classification of Astronomical Events](https://doi.org/10.1088/1538-3873/aaef12) - **Method.** Simulates telescope image sequences under survey, instrument, atmospheric, sampling, and noise conditions to train classifiers evaluated on real astronomical observations.

## Contributing

Contributions are welcome through issues and pull requests. Keep additions directly within the scope above, use a stable primary or official URL, add each resource to one primary section, and provide one concise factual sentence explaining both the created data and its downstream task.

Before proposing a resource, verify that synthetic, semi-synthetic, simulated, rendered, silver-standard, or automatically labeled data are a substantive contribution rather than an incidental preprocessing step or a hypothetical downstream use. Prefer resources with public data, code, generators, or stable archival records, and avoid near-duplicates when a stronger representative already covers the same mechanism.
