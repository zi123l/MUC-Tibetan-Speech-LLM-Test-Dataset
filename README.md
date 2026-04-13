# MUC Tibetan Speech LLM Test Dataset Public Release

This repository releases the dataset resources used by Professor Yue Zhao's research group at the School of Information Engineering, Minzu University of China, for evaluating the Tibetan speech large language model Ti-audio. The dataset can be used to evaluate tasks such as Tibetan automatic speech recognition and Tibetan-Chinese speech translation.

The full dataset constructed for the Ti-audio Tibetan speech large language model consists of both a training set and a test set. At present, only the test set is publicly released. Aggregate statistics of the training set are provided for reference, and further release details may be announced in the future if conditions permit.

Paper URL: `XXXXX`

## Statement

This dataset was organized and constructed by Professor Yue Zhao's research group at the School of Information Engineering, Minzu University of China. The current public release corresponds to the open test portion of the Ti-audio Tibetan speech large language model evaluation dataset, and is primarily intended to support academic research and experimental reproduction for Tibetan automatic speech recognition, Tibetan-Chinese speech translation, and related tasks.

To protect the rights and interests of data contributors and ensure the reasonable use of the data, the contents of this repository are recommended for research, teaching, and non-commercial use only. If you intend to use the dataset for commercial purposes or for any use beyond reasonable academic scope, please contact the dataset construction team in advance for authorization.

## Repository Contents

The current public repository includes:

- `data/test_public.tsv`: the canonical TSV file for the public test set, with duplicate path entries removed
- `data/dialect_stats.tsv`: dialect-level statistics for the public test set
- `LICENSE`: dataset usage license

Among them, `data/test_public.tsv` is the core index file of the public test set and records sample paths together with the corresponding annotation information. `data/dialect_stats.tsv` describes the distribution of different dialects in terms of sample count, total duration, and data volume.

Audio files from the complete test-set release package are not stored directly in the repository code area. They are recommended to be downloaded through the corresponding GitHub Release archive.

## Data Scope

The full project includes both a training set and a test set. The current repository publicly releases only the speech translation test portion corresponding to `test_final.txt`.

- Original number of entries in `test_final.txt`: `20120`
- Number of duplicate path entries removed: `4`
- Final number of public canonical entries: `20116`
- Included dialects: `Amdo`, `Kham`, `Tsang`
- Total duration: approximately `36.5` hours
- Total audio size: approximately `1.96 GiB`

## Training Set Dialect Distribution

The following table shows the dialect distribution statistics of the training set:

| Dialect | Hours | Samples | Ratio |
| --- | ---: | ---: | ---: |
| Amdo | 52.9 | 32813 | 27.7% |
| Kham | 79.8 | 43814 | 37.0% |
| Tsang | 70.9 | 41927 | 35.4% |
| Total | 203.6 | 118554 | 100% |

## Test Set Dialect Distribution

| Dialect | Samples | Hours | Ratio |
| --- | ---: | ---: | ---: |
| Amdo | 5279 | 8.7 | 26.2% |
| Kham | 7037 | 13.9 | 35.0% |
| Tsang | 7800 | 13.9 | 38.8% |
| Total | 20116 | 36.5 | 100.0% |

More detailed numerical information for the public test set is recorded in `data/dialect_stats.tsv`.

## contact information
Email：zhaoyueso@muc.edu.cn
