---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 3.6 Introduction to Design Optimization
parent_type: CourseSection
parent_uid: 6f317b0d-95c1-d32c-f178-c9fdbae632d2
title: 3.6 Introduction to Design Optimization
uid: 1d39506a-8ae7-400e-107d-fe048008e5c2
---

*   {{% resource_link 6f317b0d-95c1-d32c-f178-c9fdbae632d2 "\<Introduction to Design Optimization" %}}
*   {{% resource_link 6f317b0d-95c1-d32c-f178-c9fdbae632d2 "3.6.1Design Optimization" %}}
*   {{% resource_link 1d39506a-8ae7-400e-107d-fe048008e5c2 "3.6.2Gradient Based Optimization" %}}
*   {{% resource_link da1cf617-8af1-53b1-4d4a-177f24979948 "3.6.3Unconstrained Gradient-Based Optimization Methods" %}}
*   {{% resource_link c0e755e7-48fd-33db-4782-88b736e0381c "3.6.4Finite Difference Methods" %}}
*   {{% resource_link 3cde12b3-c306-b87c-973f-5af561f4875f "3.6.5The 1d Search" %}}
*   {{% resource_link da1cf617-8af1-53b1-4d4a-177f24979948 "\>Unconstrained Gradient-Based Optimization Methods" %}}

3.6.2 Gradient Based Optimization
---------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.17" "#anchorMO317" %}}

Most optimization algorithms are iterative. We begin with an initial guess for our design variables, denoted \\(x^0\\). We then iteratively update this guess until the optimal design is achieved.

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[x^ q = x^{q-1} + \\alpha ^ q S^ q, \\; q = 1,2, \\ldots\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.67)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where

\\(q\\)=iteration number

\\(x^ q\\) is our guess for \\(x\\) at iteration \\(q\\)

\\(S^ q \\in \\mathbb {R}^ n\\) is our vector search direction at iteration \\(q\\)

\\(\\alpha ^ q\\) is the scalar step length at iteration \\(q\\)

\\(x^0\\) is given initial guess.

At each iteration we have two decisions to make: in which direction to move (i.e., what \\(S^ q\\) to choose, and how far to move along that direction (i.e., how large should \\(\\alpha ^ q\\) be). Optimization algorithms determine the search direction \\(S^ q\\) according to some criteria. Gradient-based algorithms use gradient information to compute the search direction.

For \\(J(x)\\) a scalar objective function that depends on \\(n\\) design variables, the gradient of \\(J\\) with respect to \\(x=\[x\_1 x\_2 \\ldots x\_ n\]^ T\\) is a vector of length \\(n\\). In general, we need the gradient evaluated at some point \\(x^ k\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\nabla J(x^ k) = \[ \\frac{\\partial J}{\\partial x\_1}(x^ k) \\ \\ldots \\frac{\\partial J}{\\partial x\_ n}(x^ k) \]\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.68)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The second derivative of \\(J\\) with respect to \\(x\\) is a matrix, called the Hessian matrix, of dimension \\(n \\times n\\). In general, we need the Hessian evaluated at some point \\(x^ k\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\nabla ^2 J(x^ k) = \[ \\frac{\\partial ^2 J}{\\partial x\_1^2}(x^ k) \\ \\ldots \\frac{\\partial ^2 J}{\\partial x\_1 \\partial x\_ n}(x^ k) \\\\ \\frac{\\partial ^2 J}{\\partial x\_1 \\partial x\_ n}(x^ k) \\ \\ldots \\frac{\\partial ^2 J}{\\partial x\_ n^2}(x^ k)\]\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.69)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In other words, the \\((i,j)\\) entry of the Hessian is given by,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\nabla ^2 J(x^ k)\_{i,j} = \\frac{\\partial ^2 J}{\\partial x\_ i \\partial x\_ j}(x^ k)\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.70)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Consider the function \\(J(x)=3x\_1 + x\_1 x\_2 + x\_3^{2} + 6x\_2^{3} x\_3\\).

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\((4, 7, 9)\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\((5, 19, 3)\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} \\((4, 19, 8)\\){{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\((3, 18, 2)\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} \\((0, 18, 2)\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\((0, 16, 2)\\){{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackIntroduction to Design Optimization ContinueUnconstrained Gradient-Based Optimization Methods