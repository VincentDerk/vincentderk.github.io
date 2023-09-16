---
layout: page
title: Probabilistic logic programming, ProbLog
description: ProbLog is a probabilistic logic programming language with state-of-the-art inference technqiues based on knowledge compilation and algebraic model counting. The generality of its algebraic framework has allowed the language to easily be extended to solve other tasks.
---

[ProbLog](https://dtai.cs.kuleuven.be/problog/) is a probabilistic logic programming language developed within the DTAI research group. It extends the Prolog programming language with probabilities, using a clearly defined semantics. In the backend, to perform exact inference, ProbLog casts it into a weighted model counting task which is solved efficiently through existing knowledge compilation tools.

I have helped maintain and improve the codebase, which is publicly available on [Github](https://github.com/ML-KULeuven/problog). The language has also been extended several times to support for additional concepts. For example, [DeepProbLog](https://doi.org/10.1016/j.artint.2021.103504) and [DeepStochlog](https://ojs.aaai.org/index.php/AAAI/article/view/21248/20997) are both extensions that have added support for neural networks. That is, the probabilities defined over facts can originate from a neural network.


# Decision making under uncertainty

The [DTProbLog](https://ojs.aaai.org/index.php/AAAI/article/view/7755/7615) language is an extension of ProbLog that adds support for decision making: some facts are decisions, and some are associated with a utility (e.g., a reward). The primary inference task in this setting is to compute the decisions that maxises the expected utility.

In our publication titled, [Algebraic Circuits for Decision Theoretic Inference and Learning](https://doi.org/10.3233/FAIA200392), we showed how this task can also be solved using the help of existing algebraic model counting techniques, confirming the flexiblity of this algebraic framework. In addition to performing a decision maximisation task, we also explored a utility parameter learning setting within the same framework.


```
{% raw %}
@inproceedings{Derkinderen2020algebraic,
  author       = {Vincent Derkinderen and
                  Luc {De Raedt}},
  title        = {Algebraic Circuits for Decision Theoretic Inference and Learning},
  booktitle    = {{ECAI}},
  series       = {Frontiers in Artificial Intelligence and Applications},
  volume       = {325},
  pages        = {2569--2576},
  publisher    = {{IOS} Press},
  year         = {2020}
}
{% endraw %}
```


We have also started exploring the dynamic setting, where multiple decisions have to be taken sequentially over time. More information can be found in our workshop paper [Towards Tractable Dynamic Decision Making With Circuits](https://lirias.kuleuven.be/retrieve/674104).


```
{% raw %}
@inproceedings{Venturato2022towards,
  author       = {Gabriele Venturato and
                  Vincent Derkinderen and
                  Pedro {Zuidberg Dos Martires} and	
                  Luc {De Raedt}},
  title        = {Towards Tractable Dynamic Decision Making With Circuits},
  booktitle    = {5th Workshop on Tractable Probabilistic Modeling},
  year         = {2022}
}
{% endraw %}
```


# Modelling and inference with Epistemic uncertainty.

A ProbLog program models a probability distribution. In order to also model the uncertainty over the modelled distribution, that is, the epistemic uncertainty, we introduced the *BetaProbLog* language. In this language, a probability is replaced with a beta distribution that models the uncertainty over the possible probability values. 

For example, imagine a biased coin being flipped. After observing two coin tosses, you can not be certain of the correct probability (due to the epistemic uncertainty). As we observe more coin tosses, the beta distribution representing the uncertainty changes to a more certain one.

BetaProbLog has sound semantics and an effective inference algorithm that combines Monte Carlo techniques with knowledge compilation. More information is available in our publication titled [Inference and Learning with Model Uncertainty in Probabilistic Logic Programs](https://doi.org/10.1609/aaai.v36i9.21245), and the [shorter version](https://lirias.kuleuven.be/retrieve/682658) accepted at the ICLP Recently Published Papers track.

```
{% raw %}
@inproceedings{Verreet2022beta,
  author       = {Victor Verreet and
                  Vincent Derkinderen and
                  Pedro {Zuidberg Dos Martires} and
                  Luc {De Raedt}},
  title        = {Inference and Learning with Model Uncertainty in Probabilistic Logic Programs},
  booktitle    = {{AAAI}},
  pages        = {10060--10069},
  publisher    = {{AAAI} Press},
  year         = {2022}
}
{% endraw %}
```




