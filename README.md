# ADSLD: A General Framework for Solving Large-Scale Linear Programming Problems in Multi-Order Fulfillment Scenarios

## Overview

This repository contains the implementation of the Arbitrary Decomposition Supergradient Method based on Lagrangian Relaxation and Duality (ADSLD). This novel framework aims to tackle the challenges of large-scale linear programming in multi-order fulfillment scenarios. The ADSL framework effectively decomposes complex problems into manageable subproblems, enhancing scalability and practical applicability through Lagrangian relaxation, duality principles, and arbitrary decomposition.

In recent years, the rapid growth of e-commerce has transformed the retail industry, presenting significant challenges for online retailers to efficiently process a vast number of orders. Retailers typically need to handle tens of millions of orders daily and ship over a million different products, heavily relying on linear programming solutions. Due to the enormous scale of the problem, solving large-scale linear programming problems is highly challenging. Many online fulfillment scenarios depend on optimal offline decisions to guide real-time online decisions, increasing practical difficulties. This study extends previous work by developing a general framework suitable for multi-order offline fulfillment scenarios, improving the Completely Decomposed Supergradient Method based on Lagrangian Relaxation and Duality (CDSLD) through the creation of an Arbitrary Decomposition Supergradient Method.

## Algorithm Features

- **Lagrangian Relaxation**: Introduces Lagrangian multipliers to relax constraints, transforming complex optimization problems into manageable subproblems.
- **Duality Principle**: Utilizes dual optimization techniques to enhance computational efficiency.
- **Arbitrary Decomposition**: Flexibly decomposes the problem space, balancing time and space complexity.

## Code Description

The main parts of the code include: 1. Random data initialization; 2. Definition and solution of the Lagrangian relaxation problem; 3. Updating Lagrangian multipliers using the supergradient method; 4. Calculating and evaluating performance.

For the random data initialization part, we simulate a multi-order fulfillment scenario. Due to the massive scale of the problem, variables can exceed tens of millions with sufficient orders, and the size of intermediate computation matrices can surpass hundreds of billions. We simulate an implementation of a lightweight scenario, and it is important to note that we configure CPLEX as the solver and use Pulp for constructing mathematical programs. For conventional calculations, CPLEX is sufficiently fast. However, for larger-scale problem scenarios, distributed computing is generally strongly relied upon, and actual performance also depends on multi-node communication overhead.

In the process of solving using the supergradient method, our main ideas include: 1. Trading space for time to obtain an approximate solution to the original large-scale problem within a limited time; 2. Sacrificing time to update the solution through multiple iterations to obtain a near-optimal feasible solution. The ADSL method can dynamically utilize computational resources based on the actual situation. (Although there is no distributed computing code, it is evident that this framework can fully allocate resources based on communication overhead after reasonable deployment).
