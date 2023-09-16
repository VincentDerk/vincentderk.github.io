---
layout: page
title: Modulo theory knowledge compilation
description: Knowledge compilation studies the transformation of knowledge into representations more suitable for (AI) inference tasks. This project focusses on compilation with background theories, which, for example, automatically realises that (x > 0) and (y > 0) together imply (x + y > 0).
---

Many of the existing knowledge compilation tools focus on the purely propositional logic setting. These propositional tools are also usable for applications that involve a background theory. For instance, weighted model integration (WMI) is a task that may involve linear real arithmetic formulas such as (x + y > 2).


## Variable Ordering heuristics
The variable ordering heuristics used within knowledge compilers typically focus on obtaining succinct representations. When these compilers are used within the WMI application however, the goals are different due to the integration operation. We studied this in our conference publication [Ordering Variables for Weighted Model Integration](http://proceedings.mlr.press/v124/derkinderen20a/derkinderen20a.pdf), and proposed several new heuristics that significantly improve the run time required for solving WMI tasks. You can find relevant code at the [pywmi](https://github.com/weighted-model-integration/pywmi) and [BU-MiF](https://github.com/VincentDerk/BU-MiF) repositories.

```
{% raw %}
@inproceedings{Derkinderen2020order,
  author       = {Vincent Derkinderen and
                  Evert Heylen and
                  Pedro {Zuidberg Dos Martires} and
                  Samuel Kolb and
                  Luc {De Raedt}},
  title        = {Ordering Variables for Weighted Model Integration},
  booktitle    = {{UAI}},
  series       = {Proceedings of Machine Learning Research},
  volume       = {124},
  pages        = {879--888},
  publisher    = {{AUAI} Press},
  year         = {2020}
}
{% endraw %}
```

## Theory aware knowledge compilation

The use of purely propositional tools for tasks that involve background theories introduces inefficiencies. For example, the propositional tools might not realise that (x < 0) and (x > 1) are mutually exclusive constraints, unless the user explicitly encodes this information and passes it to the tool.

We therefore investigated several approaches to knowledge compilation that is theory aware, and specifically advocate for a top-down compiler based on the traces of exchaustive DPLL(T) search. More information on this is provided in our article [Top-Down Knowledge Compilation for Counting Modulo Theories](https://arxiv.org/abs/2306.04541)

```
{% raw %}
@article{Derkinderen2023modcomp,
  author       = {Vincent Derkinderen and
                  Pedro {Zuidberg Dos Martires} and
                  Samuel Kolb and
                  Paolo Morettin},
  title        = {Top-Down Knowledge Compilation for Counting Modulo Theories},
  journal      = {CoRR},
  volume       = {abs/2306.04541},
  year         = {2023}
}
{% endraw %}
```

