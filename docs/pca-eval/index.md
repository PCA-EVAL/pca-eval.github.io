---
layout: default
title: What is PCA-EVAL?
nav_order: 1
description: "PCA-EVAL Evaluates Embodied Decision Making from Perception, Cognition and Action"
permalink: /
---



**PCA-EVAL** is an innovative benchmark for evaluating multi-domain embodied decision-making, specifically focusing on the performance in perception, cognition, and action. It is proposed in paper "[Towards End-to-End Embodied Decision Making via Multi-modal Large Language Model: Explorations with GPT4-Vision and Beyond](https://arxiv.org/abs/2310.02071)".
{: .fs-5.5 .fw-600 }

<center>Liang Chen<sup>1</sup>, Yichi Zhang<sup>1</sup>, Shuhuai Ren<sup>1</sup>, Haozhe Zhao<sup>1</sup>, Zefan Cai<sup>1</sup>, Yuchi Wang<sup>1</sup>, <br>Peiyi Wang<sup>1</sup>, Tianyu Liu<sup>2</sup>, Baobao Chang<sup>1</sup> <br> <sup>1</sup>Peking University, <sup>2</sup>Tencent Cloud AI</center>
{: .fs-5 .fw-600 }

<br>

<video id="v0" width="100%" playsinline muted loop autoplay onclick="setAttribute('controls', 'true');">
<source src="/assets/video/Embodied Decision Making.mp4" type="video/mp4">
 </video>	





## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---







## Domains and Examples

Initially, PCA-EVAL benchmarks three domains to evaluate the general embodied decision-making capabilities of agents. As shown below, these domains include Autonomous Driving, Domestic Robot and Open-World Game.

<center><img src="/assets/images/sun.jpg" alt="HOLMES Example" style="width: 350px;"><br>Domain and required ability distribution of PCA-EVAL.</center>

For each domain, we give three examples below.

- Autonomous Driving Domain
<center><img src="/assets/images/traffic_example.png" alt="traffic Example" style="width: 80%;"></center>

- Domestic Robot Domain
<center><img src="/assets/images/alfred_example.png" alt="alfred Example" style="width: 80%;"></center>

- Open-World Game Domain
<center><img src="/assets/images/mc_example.png" alt="mc Example" style="width: 80%;"></center>







## Metrics

- Perception-Score: Evaluate whether the agent captures the key concepts related to the question in the observation.
- Cognition-Score: Evaluate whether the agent makes correct deduction with perception and world knowledge to the final action.
- Action-Score: Evaluate whether the agent chooses the correct action.

Each score is either 0 or 1 for an agent's response to a question. The scores of all instances are averaged to get the final performance.


## Methods

We evaluate two methods with different models on our PCA-EVAL benchmark. We provide evaluation guidelines in [Run Evaluation]({{site.baseurl}}/docs/pca-eval/Evalutation/).


### End2End


End2End embodied decision making is straightforward since we can directly feed the visual observation and the textual question to the multi-modal agent. As illustrated in the figure below, the agent is prompted to output the image description and reasoning process before giving the final action. 

<center><img src="/assets/images/end2end_example.png" alt="End2End Example" style="width: 250px;"><br>Example of End2End Decision Making</center>


### HOLMES 

Within HOLMES, we prompt large language models like ChatGPT-3.5, GPT4 to call different visual models or APIs to gather information about the environment. In our evaluation toolkit, the results of all API calling are cached so the users do not need to implement the API themselves.

<center><img src="/assets/images/holems_example.png" alt="HOLMES Example" style="width: 250px;"><br>Example of HOLMES</center>


## Results

<center><img src="/assets/images/results.png" alt="results" style="width: 100%;"></center>



<!-- ## Acknowledgements -->

---

## Citation
```bib
@article{chen2023endtoend,
      title={Towards End-to-End Embodied Decision Making via Multi-modal Large Language Model: Explorations with GPT4-Vision and Beyond}, 
      author={Liang Chen and Yichi Zhang and Shuhuai Ren and Haozhe Zhao and Zefan Cai and Yuchi Wang and Peiyi Wang and Tianyu Liu and Baobao Chang},
      year={2023},
      journal={ArXiv},
}
```

