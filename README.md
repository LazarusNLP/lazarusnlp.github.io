# Welcome to Lazarus NLP!

**Lazarus NLP** is a collective initiative to revive the dying languages of Indonesia through speech and language technology.

<p align="center">
    <img src="./docs/assets/images/logo_web.png" alt="logo" width="400"/>
</p>

## Projects

<table>
  <tr>
    <td valign="top">
      <h3>NusaBERT: Teaching IndoBERT to be multilingual and multicultural!</h3>
      <p>This project aims to extend the multilingual and multicultural capability of <a href="https://github.com/IndoNLP/indonlu">IndoBERT</a>. We expanded the IndoBERT tokenizer on 12 new regional languages of Indonesia, and continued pre-training on a large-scale corpus consisting of the Indonesian language and 12 regional languages of Indonesia. Our models are highly competitive and robust on multilingual and multicultural benchmarks, such as <a href="https://github.com/IndoNLP/indonlu">IndoNLU</a>, <a href="https://github.com/IndoNLP/nusax">NusaX</a>, and <a href="https://github.com/IndoNLP/nusa-writes">NusaWrites</a>.</p>
    </td>
    <td valign="top">
      <h3>IndoT5: T5 Language Models for the Indonesian Language</h3>
      <p>IndoT5 is a T5-based language model trained specifically for the Indonesian language. With just 8 hours of training on a limited budget, we developed a competitive sequence-to-sequence, encoder-decode model capable of fine-tuning tasks such as summarization, chit-chat, and question-answering. Despite the limited training constraints, our model is competitive when evaluated on the <a href="https://github.com/IndoNLP/indonlg">IndoNLG</a> (text generation) benchmark.</p>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <h3>Indonesian Sentence Embedding Models</h3>
      <p>We trained open-source sentence embedding models for Indonesian, enabling applications such as information retrieval (useful for retrieval-augmented generation!) semantic text similarity, and zero-shot text classification. We leverage existing pre-trained Indonesian language models like <a href="https://github.com/IndoNLP/indonlu">IndoBERT</a> and state-of-the-art unsupervised techniques and established sentence embedding benchmarks.</p>
    </td>
    <td valign="top">
      <h3>Indonesian Natural Language Inference Models</h3>
      <p>Open-source lightweight NLI models that are competitive with larger models on IndoNLI benchmark, with significantly less parameters. We applied knowledge distillation methods to small existing pre-trained language models like IndoBERT Lite. These models offer efficient solutions for tasks requiring natural language inference capabilities while minimizing computational resources such as cross-encoder-based semantic search.</p>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <h3>Many-to-Many Multilingual Translation Models</h3>
      <p>Adapting mT5 to 45 languages of Indonesia, we developed a robust baseline model for multilingual translation for languages of Indonesia. This facilitates further fine-tuning for niche domains and low-resource languages, contributing to greater linguistic inclusivity. Our models are competitive with existing multilingual translation models on the <a href="https://github.com/IndoNLP/nusax">NusaX</a> benchmark.</p>
    </td>
    <td valign="top">
    </td>
  </tr>
</table>

## Languages of Indonesia

Although the Indonesian language (_Bahasa Indonesia_) is the country's national language and lingua franca, the Indonesian people continue to use their region's native/indigenous language on a daily basis.

The nation is home to over 700 distinct languages, each with its own characteristics and origins. Some languages share similarities, but each language continues to evolve in its own ways over time and in the regions where the language is predominantly spoken.

Wikipedia gives a very nice overview of the spread and usage of several regional languages:

| Language        | Number (millions) | % of total population | Branch             | Main areas where spoken                                                        |
| --------------- | ----------------- | --------------------- | ------------------ | ------------------------------------------------------------------------------ |
| Javanese        | 84.3              | 32.28                 | Javanese           | throughout Java Island and several provinces in Sumatra and Kalimantan island. |
| Sundanese       | 42.0              | 16.08                 | Sundanese          | West Java, Banten, Jakarta                                                     |
| Madurese        | 13.6              | 5.21                  | Madurese           | Madura Island (East Java)                                                      |
| Minangkabau     | 5.5               | 2.11                  | Malayic            | West Sumatra, Riau, Jambi, Bengkulu, Jakarta                                   |
| Buginese        | 5.0               | 1.91                  | South Sulawesi     | South Sulawesi                                                                 |
| Palembang Malay | 3.9               | 1.49                  | Malayic            | South Sumatra                                                                  |
| Banjarese       | 3.5               | 1.34                  | Malayic            | South Kalimantan, East Kalimantan, Central Kalimantan                          |
| Acehnese        | 3.5               | 1.34                  | Chamic             | Aceh                                                                           |
| Balinese        | 3.3               | 1.26                  | Bali-Sasak-Sumbawa | Bali Island and Lombok Island                                                  |
| Betawi          | 2.7               | 1.03                  | Malay-based creole | Jakarta                                                                        |

## Tech 🤝 Languages

What is deeply concerning about these languages is that, although they may have millions of active speakers, they might still be prone to becoming endangered. Furthermore, UNESCO classified ^^137 languages^^ in Indonesia as either vulnerable, definitely endangered, severely endangered, or critically endangered.

Despite the richness and diversity of these regional languages, there has very been minimal progress in the application of modern technologies to the many languages of Indonesia. It is only in recent years (~2020) that advancements began to appear, starting with the Indonesian language.

Through this project, we hope to see the same successes occur in other languages of Indonesia. In the long run, we also hope that through these technological advancements, we will be able to prevent these languages from becoming endangered and in turn, spark innovative work around these languages.

## Members

LazarusNLP is driven with love by:

<div style="display: flex;">
<a href="https://github.com/anantoj">
    <img src="https://github.com/anantoj.png" alt="GitHub Profile" style="border-radius: 50%;width: 64px;margin:0 4px;">
</a>

<a href="https://github.com/BrandonScottt">
    <img src="https://github.com/BrandonScottt.png" alt="GitHub Profile" style="border-radius: 50%;width: 64px;margin:0 4px;">
</a>

<a href="https://github.com/DavidSamuell">
    <img src="https://github.com/DavidSamuell.png" alt="GitHub Profile" style="border-radius: 50%;width: 64px;margin:0 4px;">
</a>

<a href="https://github.com/stevenlimcorn">
    <img src="https://github.com/stevenlimcorn.png" alt="GitHub Profile" style="border-radius: 50%;width: 64px;margin:0 4px;">
</a>

<a href="https://github.com/w11wo">
    <img src="https://github.com/w11wo.png" alt="GitHub Profile" style="border-radius: 50%;width: 64px;margin:0 4px;">
</a>
</div>
