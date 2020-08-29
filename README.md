# Gender bias in BERT
This repository holds the code for my master thesis entitles "The Association of Gender Bias with BERT - Measuring, Mitigating and Cross-lingual portability", written at the University of Groningen and the University of Malta. The thesis was supervised by Malvina Nissim and Albert Gatt. 

## BEC-Pro

We created the **Bias Evaluation Corpus with Professions (BEC-Pro)**. This corpus is designed to measure gender bias for different groups of professions and contains English and German sentences built from templates. The corpus files are `BEC-Pro_EN.tsv` for English and `BEC-Pro_DE.tsv` for German.

## Research on gender bias in BERT

In the code folder, run `main.py`, which requires the following arguments:
```
usage: main.py [-h] --lang LANG --eval EVAL [--tune TUNE] --out OUT [--model MODEL] [--batch BATCH]
               [--seed SEED]

  -h, --help     show this help message and exit
  --lang LANG    provide language, either EN or DE
  --eval EVAL    .tsv file with sentences for bias evaluation (BEC-Pro or transformed EEC)
  --tune TUNE    .tsv file with sentences for fine-tuning (GAP flipped)
  --out OUT      output directory and start of filename
  --model MODEL  which BERT model to use 
  --batch BATCH  fix batch-size for fine-tuning 
  --seed SEED
```

For English, run:
```
python3 main.py --lang EN --eval ../BEC-Pro/BEC-Pro_EN.tsv --tune ../data/gap_flipped.tsv --out ../data/results
```
For German, run:
```
python3 main.py --lang DE --eval ../BEC-Pro/BEC-Pro_DE.tsv --out ../data/results
```
