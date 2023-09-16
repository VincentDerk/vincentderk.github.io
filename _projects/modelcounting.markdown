---
layout: page
title: Faster knowledge compilation and model counting
description: While these problems are \#P-complete, many instances are solvable in practice by exploiting the instance's structure. This project investigates further improvements.
---

Iterating over all possible models one by one, and computing their (weighted) model count, quickly becomes infeasible as the number of variables increases. From a mathematical perspective, this process can be improved by exploiting distributivity, commutativity and associativity. Since the models are defined by a logical formula, counting and compilation approaches take instead a similar but more logical perspective.


# Exploiting structural symmetry
In our conference publication, [Symmetric Component Caching for Model Counting on Combinatorial Instances](https://ojs.aaai.org/index.php/AAAI/article/view/16511), we exploit the fact that the (unweighted) model count of isomorphic components is equivalent. For example, the unweighted model count of 'A or not B or C' is equivalent to the model count of 'C or not D or not A'. Indeed the model count of a formula remains equivalent under the following transformations:
* reordering the literals within disjunction, i.e., applying commutativity and associativity on a clause does not change its model count.
* reorder the clauses within a CNF formula, i.e., applying commutativity and associativity on a conjunction of clauses does not change its model count.
* relabeling variables, e.g., changing every occurance of A and not A to a fresh symbol X and not X respectively does not change the model count.

This can easily be exploited during the DPLL algorithm (a model counting algorithm) by modifying the caching mechanism to detect these symmetries and reuse previously model counts of symmetic components.

```
{% raw %}
@inproceedings{BremenD0RM21,
  author       = {Timothy {van Bremen} and
                  Vincent Derkinderen and
                  Shubham Sharma and
                  Subhajit Roy and
                  Kuldeep {S. Meel}},
  title        = {Symmetric Component Caching for Model Counting on Combinatorial Instances},
  booktitle    = {{AAAI}},
  pages        = {3922--3930},
  publisher    = {{AAAI} Press},
  year         = {2021}
}
{% endraw %}
```

