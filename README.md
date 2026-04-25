# MUC Tibetan Speech LLM Test Dataset Public Release

This repository releases the **public test subset of MUC-Tibetan-Speech-LLM**, a dataset constructed by Professor Yue Zhao's research group at the School of Information Engineering, Minzu University of China. It is one component of the full data collection used to build and evaluate the Tibetan speech large language model **Ti-audio**. The released data can be used to evaluate tasks such as Tibetan automatic speech recognition and Tibetan-Chinese speech translation.


The complete Ti-audio data collection includes both training and test data and is assembled from multiple Tibetan datasets. This repository does **not** release the entire Ti-audio dataset. Instead, it releases only the public test portion of MUC-Tibetan-Speech-LLM. Aggregate statistics of the training data are provided for reference, and further release details may be announced in the future if conditions permit.

Paper URL: [Ti-Audio: The First Multi-Dialectal End-to-End Speech LLM for Tibetan](https://arxiv.org/abs/2604.11110)

## Full Ti-audio Dataset Composition

The following table summarizes the Tibetan datasets used in the Ti-audio work. This repository corresponds only to the **MUC-Tibetan-Speech-LLM** entry listed below.

Where a stable public dataset homepage is available, a direct clickable link is provided. For sources without a stable standalone dataset page, a reference page is provided instead.

| Task | Data Source | Hours | Samples |
| --- | --- | ---: | ---: |
| ASR / ST | [MUC-Tibetan-Speech-LLM](./data) | 305.7 | 162k+ |
| ASR / ST / GR | [M2ASR Tibetan (CSLT data index)](http://index.cslt.org/mediawiki/index.php/ASR-nsfc-data) | 72.3 | 58k+ |
| ASR | [TIBMD@MUC (OpenSLR SLR124)](https://www.openslr.org/124/) | 84.3 | 68k+ |
| ASR | [XBMU-AMDO31 (OpenSLR SLR133)](https://www.openslr.org/133/) | 31.0 | 22k+ |
| ASR | [MUC-greeting (OpenSLR SLR149)](https://www.openslr.org/149/) | 2.8 | 3k+ |
| ASR | [Tibetan SER(reference page)](https://drpress.org/ojs/index.php/fcis/article/view/23012) | 2.7 | 6k+ |
| Total | Ti-audio full Tibetan dataset collection | 498.8 | 321k+ |

## Statement

This dataset was organized and constructed by Professor Yue Zhao's research group at the School of Information Engineering, Minzu University of China. The current public release corresponds to the open test portion of the Ti-audio Tibetan speech large language model evaluation dataset, and is primarily intended to support experimental evaluation and model comparison for Tibetan automatic speech recognition, Tibetan-Chinese speech translation, and related tasks.

To protect the rights and interests of data contributors and ensure the reasonable use of the data, the contents of this repository are recommended for research, teaching, and non-commercial use only. If you intend to use the dataset for commercial purposes or for any use beyond reasonable academic scope, please contact the dataset construction team in advance for authorization.

## Repository Contents

The current public repository includes:

- `data/test_public.tsv`: the canonical TSV file for the public test set, with duplicate path entries removed
- `data/dialect_stats.tsv`: dialect-level statistics for the public test set
- `LICENSE`: dataset usage license

Among them, `data/test_public.tsv` is the core index file of the public test set and records sample paths together with the corresponding annotation information. `data/dialect_stats.tsv` describes the distribution of different dialects in terms of sample count, total duration, and data volume.

Audio files from the complete test-set release package are not stored directly in the repository code area. They are recommended to be downloaded through the corresponding GitHub Release archive.

## Data Scope

The full project includes both a training set and a test set. The current repository publicly releases only the  test portion corresponding to muc_tibetan_test.txt.

- Original number of entries in `muc_tibetan_test.txt`: `20120`
- Number of duplicate path entries removed: `4`
- Final number of public canonical entries: `20116`
- Included dialects: `Amdo`, `Kham`, ` Ü-Tsang`
- Total duration: approximately `36.5` hours
- Total audio size: approximately `1.96 GiB`

## Training Set Dialect Distribution

The following table shows the dialect distribution statistics of the training set:

| Dialect | Hours | Samples | Ratio |
| --- | ---: | ---: | ---: |
| Amdo | 52.9 | 32813 | 27.7% |
| Kham | 79.8 | 43814 | 37.0% |
| Ü-Tsang | 70.9 | 41927 | 35.4% |
| Total | 203.6 | 118554 | 100% |

## Test Set Dialect Distribution

| Dialect | Samples | Hours | Ratio |
| --- | ---: | ---: | ---: |
| Amdo | 5279 | 8.7 | 26.2% |
| Kham | 7037 | 13.9 | 35.0% |
| Ü-Tsang | 7800 | 13.9 | 38.8% |
| Total | 20116 | 36.5 | 100.0% |

More detailed numerical information for the public test set is recorded in `data/dialect_stats.tsv`.
## Benchmark Results on the Public Test Set

The following tables report the evaluation results of Ti-audio and several baseline models on this public test set. The results indicate that Ti-audio achieves favorable overall performance in comparison with the baseline systems, particularly on speech translation (ST) and automatic speech recognition (ASR) tasks. Results are reported for speech translation (ST), machine translation (MT), and automatic speech recognition (ASR). For ST and MT, higher BLEU is better. For ASR, lower WER/CER is better

### ST Results

| Model | Amdo | Kham | Ü-Tsang | Avg | Metric |
| --- | ---: | ---: | ---: | ---: | --- |
| Cascaded mHuBERT-DeepSeek V3.1 | 10.02 | 11.69 | 11.71 | 11.14 | BLEU |
| Cascaded mHuBERT-Hunyuan-MT-7B | 9.97 | 11.28 | 11.79 | 11.01 | BLEU |
| Cascaded mHuBERT-Gemini 3 Flash | 20.80 | 21.69 | 21.49 | 21.32 | BLEU |
| Cascaded mHuBERT-Monlam | 11.00 | 10.88 | 9.41 | 10.43 | BLEU |
| Gemini 3 Flash | 1.64 | 2.52 | 4.27 | 2.81 | BLEU |
| **Ti-audio** | **20.59** | **22.11** | **23.45** | **22.05** | BLEU |

### MT Results

| Model | Amdo | Kham | Ü-Tsang | Avg | Metric |
| --- | ---: | ---: | ---: | ---: | --- |
| DeepSeek V3.1 | 14.45 | 15.85 | 15.93 | 15.41 | BLEU |
| Hunyuan MT 7B | 13.23 | 12.51 | 13.83 | 13.19 | BLEU |
| Gemini 3 Flash | 25.03 | 26.53 | 26.42 | 25.99 | BLEU |
| Monlam | 15.66 | 15.58 | 13.23 | 14.82 | BLEU |

### ASR Results

| Model | Amdo | Kham | Ü-Tsang | Avg | Metric |
| --- | ---: | ---: | ---: | ---: | --- |
| mHuBERT (CTC) | 27.26 / 10.20 | 26.32 / 10.38 | 26.72 / 11.78 | 26.77 / 10.79 | WER / CER |
| Meta Omnilingual | 76.89 / 47.73 | 75.60 / 49.44 | 66.63 / 41.24 | 73.04 / 46.14 | WER / CER |
| **Ti-audio** | **14.25 / 9.57** | **14.15 / 9.60** | **14.99 / 10.31** | **14.46 / 9.83** | WER / CER |


## contact information
Email：zhaoyueso@muc.edu.cn
