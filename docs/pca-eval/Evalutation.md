---
layout: default
title: Run Evaluation
nav_order: 3
description: "How to run PCA-EVAL"
---

Run Evaluation
{: .fs-9 }



```bash
git clone https://github.com/pkunlp-icler/PCA-EVAL.git
cd PCA-EVAL
```

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}




## End2End Method

In the End2End method, the prompt utilized for each instance, along with its corresponding image name, is provided in JSON format within the data directory specific to each domain. For example:

```bash
pca-eval/data/v1.0/Autonomous Driving/end2end_prompts.json
pca-eval/data/v1.0/Domestic Robot/end2end_prompts.json
pca-eval/data/v1.0/Open-World Game/end2end_prompts.json
```

You can seamlessly pass both the image and the prompt to your multimodal model to obtain results.

The output for each instance should be saved in json file, in the format of
```json
[
    {"index":0,"model_output":"xxxxx"},
    {"index":1,"model_output":"xxxxx"}, 
]
```


## HOLMES Method

For HOLMES method using LLM, we provide jupyter notebooks for OPENAI model tested in our paper. By changing the openai key and data path, you could reproduce the results easily.

```bash
pca-eval/evaluation/HOLMES_Autonomous_Driving.ipynb
pca-eval/evaluation/HOLMES_Domestic_Robot.ipynb
pca-eval/evaluation/HOLMES_Game.ipynb
```




The output for each instance should be saved in json file, in the format of
```json
[
    {"index":0,"model_output":"xxxxx"},
    {"index":1,"model_output":"xxxxx"},
]
```

## Automatic Scoring

We utilize the semantic parsing ability of powerful LLM like ChatGPT to conduct automatic scoring for perception, cognition and action scores.

```bash
python pca-eval/pca_auto_scoring.py \ 
    --meta_data  pca-eval/data/v1.0/Open-World Game/meta_data.json \  # path to the meta data
    --model_output chatgpt_output.json \  # model output file in json format
    --openai_key sk-xxxxxxxxxx \  # your openai key
    --output_path  chatgpt_result.json \  # path to save the result
```
