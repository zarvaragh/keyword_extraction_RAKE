# keyword_extraction_RAKE

Extract keywords from text using the **RAKE** (Rapid Automatic Keyword Extraction) algorithm.

## Requirements

```bash
pip install rake-nltk pandas
```

> **Note:** Uses [`rake-nltk`](https://pypi.org/project/rake-nltk/) — the actively maintained RAKE implementation.

## Dataset

Expects a CSV file named `Train.csv` with columns `Title` and `Body`.

## Usage

```bash
python rake.py
```

The script:
1. Loads the first 5000 rows of `Train.csv`
2. Concatenates `Title` + `Body` into a `Text` column
3. Cleans the text (lowercase, removes tags and special characters)
4. Runs RAKE on each row and stores the top keyword phrase in a `Keywords` column

## How RAKE works

RAKE identifies keyword phrases by finding co-occurring words that appear frequently together but rarely with stop words. It scores phrases based on word frequency and degree (co-occurrence count).