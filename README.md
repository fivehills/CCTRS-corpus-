# Corpus of Chinese Textual 'Run-on' Sentences (CCTRS) --Discourse Corpus Benchmark with Multi-layer Annotations

## Overview
The **Corpus of Chinese Textual 'Run-on' Sentences (CCTRS)** is a specialized discourse corpus designed to study "run-on" sentences (*liushui ju* or "flowing-water sentences", 汉语"流水句“), a prevalent linguistic phenomenon in Chinese characterized by implicit logical connections and semantic leaps. Comprising **500 sentences** from contemporary Chinese fiction (2.6 million characters), the CCTRS provides multi-layer annotations to support computational discourse analysis and natural language processing (NLP) tasks.

This corpus integrates the strengths of **Penn Discourse Treebank (PDTB)** and **Rhetorical Structure Theory (RST)** annotation frameworks, making it the first Chinese corpus to merge these approaches. It includes annotations for **discourse relations**, **grammatical structures**, **semantic information** (e.g., animacy, verb valence), and **topic chains**, offering a rich resource for studying Chinese discourse characteristics.

The CCTRS is publicly available at: [https://github.com/fivehills/CCTRS-corpus-/tree/main](https://github.com/fivehills/CCTRS-corpus-/tree/main).

## Corpus Features
- **Size**: 500 "run-on" sentences from 10 well-known contemporary Chinese fiction works.
- **Annotation Layers**:
  - **Discourse Relations**: Combines PDTB semantic tags (e.g., Temporal, Contingency, Comparison, Expansion) with RST tree structures, excluding nucleus-satellite distinctions due to their limited applicability in Chinese fiction.
  - **Grammatical Structure**: Tags clauses as SVO, SV, SVC, VP, NP, or AP, and annotates verb valence (mono-, di-, or trivalent).
  - **Semantic Information**: Includes animacy (human, nonhuman, inanimate) and action (dynamic, stative) for subjects and verbs, particularly around semantic leaps.
  - **Topic Chains**: Annotates co-referential zero anaphora and topic distance to support discourse coherence analysis.
- **Unique Tags**:
  - **Leap (Le)**: Marks semantic leaps, similar to PDTB’s *NoRel*, where no clear discourse relation exists between segments.
  - **Continuation (Cu)**: Denotes successive actions without explicit temporal markers.
- **Annotation Reliability**: Achieved over 80% agreement and Kappa values above 0.6, indicating high-quality annotations by three native Chinese-speaking annotators with linguistics backgrounds.

## Sample Annotation
Below is an example of a "run-on" sentence from the corpus (EDUs 95.1–95.6), illustrating the multi-layer annotation structure:

**Text**: "At this time an airplane flew over, and a white band trailed behind the airplane, long-lasting, and the sky was cut open, or the sky cracked, and leaked."

**Annotations** (simplified from the provided sample):
| ID   | Text          | Grammatical Structure | Discourse Relation | Tree Structure | Relation Distance | Verb Valency | Animacy |
|------|---------------|-----------------------|--------------------|---------------|-------------------|--------------|---------|
| 95.1 | 飞机飞过      | SV                    | pg (progression)   | 1#2           | 1                 | 1            | NA      |
| 95.2 | 飞机拖了白带  | SV                    | pr (premise)       | 2#3           | 1                 | 2            | NA      |
| 95.3 | 不散          | VP                    | ce (cause-effect)  | 3#4           | 1                 | 0            | NA      |
| 95.4 | 天被割开      | SV                    | cj (conjunction)   | 4#5           | 1                 | 1            | NA      |
| 95.5 | 天裂          | SV                    | ce (cause-effect)  | 4-5#6         | 2                 | 1            | NA      |
| 95.6 | 漏水          | VP                    | ju (conjunction)   | 6#7           | 1                 | 1            | NA      |

**RST Tree Structure** (simplified):
```
Root
├── Branch 1 (1-3, pg): Airplane action sequence
│   ├── 1#2 (pg): "airplane flew over" → "trailed white band"
│   └── 2#3 (pr): "trailed white band" → "long-lasting"
└── Branch 2 (4-6, cj): Sky imagery sequence
    ├── 3#4 (cj): "long-lasting" → "sky cut open"
    ├── 4#5 (cj): "sky cut open" → "sky cracked"
    └── 4-5#6 (ce): "sky cut/cracked" → "leaked"
```

**Explanation**: The sentence describes an airplane’s action (EDUs 1–3) followed by imaginative sky imagery (EDUs 4–6), with a semantic leap between the airplane and sky descriptions. The annotations capture progression, cause-effect, and conjunction relations, reflecting the "flowing" nature of the sentence.

## Usage
The CCTRS serves as a benchmark for evaluating discourse parsers and supports various NLP tasks, including:
- **Discourse Parsing**: Tested with three RST parsers (bottom-up, top-down, LSTM-based), achieving stable performance (F1 scores ~43–45 for relations, ~62–64 for span prediction).
- **Zero Anaphora Resolution**: Topic chain annotations aid in resolving implicit references.
- **Semantic Leap Analysis**: The "leap" tag helps study abrupt transitions in discourse.
- **Cross-linguistic Comparisons**: PDTB-style tags enable comparisons with other discourse corpora.

## Corpus Statistics
- **Discourse Relations**: 2,286 relations annotated, with "leap" being the most frequent, unlike "conjunction" in other corpora (CDTB, PDTB).
- **Topic Chains**: 650 chains annotated.
- **Clauses**: 954 (animacy) and 990 (action) clauses annotated.
- **Verbs**: 2,281 verbs with valence information.
- **Distribution**: Follows a power-law distribution, consistent with other discourse corpora.

## Comparison with Other Corpora
Unlike other Chinese discourse corpora (e.g., CDTB, CUHK, TED-CDB, MCCFRR), which focus on news or TED talks and use single-layer annotations (PDTB or RST), the CCTRS:
- Targets fiction, capturing unique "run-on" sentence characteristics.
- Employs multi-layer annotations (discourse, grammar, semantics, topic chains).
- Integrates PDTB and RST, enhancing compatibility with other corpora.

## Access and Contributions
- **Access**: Download the corpus at [https://github.com/fivehills/CCTRS-corpus-/tree/main](https://github.com/fivehills/CCTRS-corpus-/tree/main).
- **Citation**: Please cite the paper: Sun, K., & Wang, R. (2022). *Constructing the Corpus of Chinese Textual 'Run-on' Sentences (CCTRS): Discourse Corpus Benchmark with Multi-layer Annotations*. In Proceedings of ICNLSP 2022.
- **Acknowledgments**: Supported by the China Postdoctoral Science Foundation (No. 2018T110581). Thanks to Prof. Haitao Liu, Yiyun Zhou, Mengjie Xu, and Dr. Yi Shan for their contributions.

## Contact
For inquiries, contact:
- Kun Sun: sharpksun@hotmail.com
- Rong Wang: rongw.de@gmail.com

This corpus is a valuable resource for researchers in computational linguistics, discourse analysis, and Chinese language studies, offering a robust foundation for advancing NLP applications in realistic Chinese discourse contexts.
