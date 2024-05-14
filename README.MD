Fair Evaluation in Concept Normalization: a Large-scale Comparative Analysis for BERT-based Models
---

This Readme is for the fork.

## Requirements
```bash
$ pip install -r requirements.txt
```

## Resources

### Pretrained Model
We use the [Huggingface](https://github.com/huggingface/transformers) version of [BioBERT v1.1](https://github.com/dmis-lab/biobert) so that the pretrained model can be run on the pytorch framework.

- [biobert v1.1 (pytorch)](https://huggingface.co/dmis-lab/biobert-v1.1)

### Datasets

Datasets and the preprocessing procedures are used the same as in [BioSyn](https://github.com/dmis-lab/BioSyn). The NCBI dataset is already present in the repository here.


## Preprocess

To get a refined test set from the test set simply run:

```bash
$ python process_data.py --train_data_folder data/ncbi/processed_train \
                         --test_data_folder data/ncbi/processed_test \
                         --save_to data/ncbi/processed_test_refined

```

## Train

To train the BioSyn models follow the [instructions](https://github.com/dmis-lab/BioSyn). BERT ranking doesn't require any training procedure.
## Evaluation

To eval BioSyn trained models follow the [instructions](https://github.com/dmis-lab/BioSyn). 
To eval the BERT ranking run the command:

```bash
$ python eval_bert_ranking.py --model_dir data/DIRECTORY_WHERE_MODEL_WAS_DOWNLOADED \
                         --data_folder data/ncbi/processed_test \
                         --vocab data/ncbi/test_dictionary.txt

```

## Citing & Authors
Tutubalina E., Kadurin A., Miftahutdinov Z. Fair Evaluation in Concept Normalization: a Large-scale Comparative Analysis for BERT-based Models 
//Proceedings of the 28th International Conference on Computational Linguistics. – 2020. – С. 6710-6716.[link](https://www.aclweb.org/anthology/2020.coling-main.588/)


BibTex

```
@inproceedings{tutubalina-etal-2020-fair,
    title = "Fair Evaluation in Concept Normalization: a Large-scale Comparative Analysis for {BERT}-based Models",
    author = "Tutubalina, Elena  and
      Kadurin, Artur  and
      Miftahutdinov, Zulfat",
    booktitle = "Proceedings of the 28th International Conference on Computational Linguistics",
    month = dec,
    year = "2020",
    address = "Barcelona, Spain (Online)",
    publisher = "International Committee on Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2020.coling-main.588",
    pages = "6710--6716",
 }
```
