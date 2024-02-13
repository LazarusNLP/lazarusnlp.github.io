---
title: "Launching LazarusNLP"
description: "Today we are launching LazarusNLP, an independent research group dedicated to leveraging Natural Language Processing (NLP) to preserve and revitalize the diverse languages of Indonesia. In a nation boasting over 700 distinct languages, our mission is to ensure that each language receives the attention it deserves in the digital age."
---

# Launching LazarusNLP: Reviving Indonesia's Dying Languages through NLP

Today we are launching LazarusNLP, an independent research group dedicated to leveraging Natural Language Processing (NLP) to preserve and revitalize the diverse languages of Indonesia. In a nation boasting over 700 distinct languages, our mission is to ensure that each language receives the attention it deserves in the digital age.

This blog aims to discuss the gaps in NLP research and development for Indonesian languages and introduce our initial projects. We are excited to share our work and invite the community to join us in our mission!

## Background

Indonesia's linguistic landscape is rich and varied, with languages evolving independently across different regions. Despite the prevalence of Indonesian (*Bahasa Indonesia*) as the national language, many of these regional languages face the threat of extinction. UNESCO has identified 137 Indonesian languages as vulnerable or endangered, highlighting the urgent need for action[^1].

While advancements in NLP have benefited major languages like Indonesian, there has been a glaring gap in applying these technologies to Indonesia's regional languages. This neglect risks further marginalizing these languages in an increasingly digital world. Our mission is to bridge this gap by developing NLP tools and resources tailored to the unique linguistic features of each Indonesian language and to reviving Indonesia's dying languages.

## Projects

### IndoT5: T5 Language Models for the Indonesian Language

<div align="center">
    <img src="https://raw.githubusercontent.com/LazarusNLP/IndoT5/main/assets/logo.png" style="align:center;width:200px;height:200px;border-radius:100%;"/>
</div>

IndoT5 is a T5-based language model trained specifically for the Indonesian language. With just 8 hours of training on a limited budget, we developed a competitive sequence-to-sequence, encoder-decode model capable of fine-tuning tasks such as summarization, chit-chat, and question-answering. Despite the limited training constraints, our model is competitive when evaluated on the [IndoNLG](https://github.com/IndoNLP/indonlg) <a href="https://github.com/IndoNLP/indonlg">IndoNLG</a> (text generation) benchmark.

- [:material-github: GitHub Repository](https://github.com/LazarusNLP/IndoT5/)
- [🤗 HuggingFace Collection](https://huggingface.co/collections/LazarusNLP/indonesian-t5-language-models-65c1b9a0f6342b3eb3d6d450)

### Indonesian Sentence Embedding Models

<div align="center">
    <img src="https://raw.githubusercontent.com/LazarusNLP/indonesian-sentence-embeddings/main/docs/assets/logo.png" style="align:center;width:200px;height:200px;border-radius:100%;"/>
</div>

We trained open-source sentence embedding models for Indonesian, enabling applications such as information retrieval (useful for retrieval-augmented generation!) semantic text similarity, and zero-shot text classification. We leverage existing pre-trained Indonesian language models like [IndoBERT](https://github.com/IndoNLP/indonlu) and state-of-the-art unsupervised techniques and established sentence embedding benchmarks.

- [:material-github: GitHub Repository](https://github.com/LazarusNLP/indonesian-sentence-embeddings)
- [:material-web: Documentation](https://lazarusnlp.github.io/indonesian-sentence-embeddings/)
- [🤗 HuggingFace Collection](https://huggingface.co/collections/LazarusNLP/indonesian-sentence-embedding-6541fce662e82d932ff360c5)

### Indonesian Natural Language Inference (NLI) Models

Open-source lightweight NLI models that are competitive with larger models on IndoNLI benchmark, with significantly less parameters. We applied knowledge distillation methods to small existing pre-trained language models like IndoBERT Lite. These models offer efficient solutions for tasks requiring natural language inference capabilities while minimizing computational resources such as cross-encoder-based semantic search.

- [🤗 HuggingFace Collection](https://huggingface.co/collections/LazarusNLP/indonesian-natural-language-inference-65b9d95539ac63290a418d67)

### Many-to-Many Multilingual Translation Models

Adapting mT5 to 45 languages of Indonesia, we developed a robust baseline model for multilingual translation for languages of Indonesia. This facilitates further fine-tuning for niche domains and low-resource languages, contributing to greater linguistic inclusivity. Our models are competitive with existing multilingual translation models on the [NusaX](https://github.com/IndoNLP/nusax) benchmark.

- [:material-github: GitHub Repository](https://github.com/LazarusNLP/machine-translation)
- [🤗 HuggingFace Collection](https://huggingface.co/collections/LazarusNLP/indot5-6541fbdfa385933e811c2e1f)

## Future Plans

Our journey has just begun. Looking ahead, we are committed to expanding our repository of open-source pre-trained language models, with a focus on Indonesia's languages, multilinguality, culture, and code-switching. By democratizing access to NLP tools for all Indonesian languages, we aim to catalyze a renaissance in linguistic diversity.

Join us in our mission to breathe new life into Indonesia's linguistic tapestry!

## Contact Us

We are always open to collaboration and welcome contributions from the community. If you are interested in our work or have ideas to share, please reach out to us at *lazarusnlp(at)gmail(dot)com*.

---

_Written by David Samuel Setiawan, Steven Limcorn, and Wilson Wongso. Last updated 13 February 2024._

[^1]: Moseley, Christopher, ed. (2010). Atlas of the World’s Languages in Danger. Memory of Peoples (3rd ed.). Paris: UNESCO Publishing. ISBN 978-92-3-104096-2.
