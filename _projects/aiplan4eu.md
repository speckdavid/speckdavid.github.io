---
layout: page
title: <h3>Symbolic Search for Diverse Plans and Maximum Utility</h3>
description: 
img: assets/img/aiplan4eu.png
importance: 1
category: work
---

The objective in AI planning is to find a solution for a given planning task, i.e., a single (possibly optimal) plan that solves the task. In academic research, one of the most common planning variants is classical planning, which can be used to solve a variety of sequential decision making problems and is captured by solvers such as Fast Downward and Pyperplan in the Unified Planning Framework (UPF). In practice, however, classical planning is often too restricted to model and solve real-world planning tasks. We will enhance the UPF with the following four expressive extensions to the traditional classical planning formalism:

 - multiple diverse solutions instead of a single solution,
 - soft and oversubscribed goal description instead of a fixed description
 - state-dependent action costs instead of constant action costs, and
 - complex state description with derived predicates and axioms instead of basic variables.

For this, we will use the symbolic search planner we developed, [SymK](https://github.com/speckdavid/symk), as the underlying planning engine to add these four expressive extensions to the UPF. Not only is SymK one of the few planners that supports these extensions, it is also among the state of the art for the traditional setting of optimal classical planning.

This project is funded by the [AIPlan4EU project](https://www.aiplan4eu-project.eu).

{% include figure.html path="assets/img/aiplan4eu.png" title="aiplan4eu.png" class="img-fluid rounded z-depth-1" %}