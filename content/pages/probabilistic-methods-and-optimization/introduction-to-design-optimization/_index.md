---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 3: Probabilistic Methods and Optimization'
parent_type: CourseSection
parent_uid: 487c3b15-ab67-d7c9-5cff-a6b147049d0c
title: 3.6 Introduction to Design Optimization
uid: 6f317b0d-95c1-d32c-f178-c9fdbae632d2
---

*   {{% resource_link bb1256bc-6917-d853-f4c6-36ce5943967f "\<Importance Sampling" %}}
*   {{% resource_link 6f317b0d-95c1-d32c-f178-c9fdbae632d2 "3.6.1Design Optimization" %}}
*   {{% resource_link 1d39506a-8ae7-400e-107d-fe048008e5c2 "3.6.2Gradient Based Optimization" %}}
*   {{% resource_link da1cf617-8af1-53b1-4d4a-177f24979948 "3.6.3Unconstrained Gradient-Based Optimization Methods" %}}
*   {{% resource_link c0e755e7-48fd-33db-4782-88b736e0381c "3.6.4Finite Difference Methods" %}}
*   {{% resource_link 3cde12b3-c306-b87c-973f-5af561f4875f "3.6.5The 1d Search" %}}
*   {{% resource_link 1d39506a-8ae7-400e-107d-fe048008e5c2 "\>Gradient Based Optimization" %}}

3.6.1 Design Optimization
-------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.17" "#anchorMO317" %}}

Engineers are often interested in solving design problems where the best possible design is selected from all possible alternatives. A design problem can be written as an optimization problem, with a set of design variables, objective functions and constraints, defined below.

**Design variables:** Design vector \\(x\\) contains \\(n\\) variables that form the design space. During design space exploration or optimization we change the entries of \\(x\\) in some rational fashion to achieve a desired effect. e.g. , design variables might be wing span, number of engines, airfoil geometries, etc.

**Objective Functions:** The objective can be a vector \\(J\\) of \\(z\\) system responses or characteristics we are trying to maximize or minimize, \\(J = \[ J\_1 J\_2 \\ldots J\_ z \]^ T\\). In many cases the objective is a scalar function, but for real systems often we attempt multi-objective optimization. Here we will consider only a scalar objective, \\(J\\).

**Constraints:** Constraints act as boundaries of the design space and typically occur due to finiteness of resources or technological limitations of some design variables. Often, but not always, optimal designs lie at the intersection of several active constraints.

We will write our optimization problem as follows:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\min \_ x J(x) \\\\ s.t. c(x) = 0 \\\\ g(x) \\leq 0 \\\\ x\_{i}^{l} \\leq x\_ i \\leq x\_{i}^{u}, i = 1, \\ldots , n.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.66)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Here, \\(x \\in \\mathbb {R}^ n\\) is the vector of \\(n\\) design variables, \\(J(x):\\mathbb {R}^ n \\to \\mathbb {R}\\) is the scalar objective function, \\(c(x):\\mathbb {R}^ n \\to \\mathbb {R}^{m\_1}\\) is a vector that defines the \\(m\_1\\) equality constraints, and \\(g(x):\\mathbb {R}^ n \\to \\mathbb {R}^{m\_2}\\) is a vector that defines the \\(m\_2\\) inequality constraints. \\(x\_{i}^{l} \\in \\mathbb {R}^ n\\) and \\(x\_{i}^{u} \\in \\mathbb {R}^ n\\) define lower and upper bounds, respectively, for the \\(i\\)th design variable \\(x\_ i\\).

The resulting optimization problem is typically solved using numerical optimization methods. In this section, we will discuss some basic approaches to solving optimization problems.

BackImportance Sampling ContinueGradient Based Optimization