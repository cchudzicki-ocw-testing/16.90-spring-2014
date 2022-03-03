---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 3.6 Introduction to Design Optimization
parent_type: CourseSection
parent_uid: 6f317b0d-95c1-d32c-f178-c9fdbae632d2
title: 3.6 Introduction to Design Optimization
uid: c0e755e7-48fd-33db-4782-88b736e0381c
---

*   {{% resource_link da1cf617-8af1-53b1-4d4a-177f24979948 "\<Unconstrained Gradient-Based Optimization Methods" %}}
*   {{% resource_link 6f317b0d-95c1-d32c-f178-c9fdbae632d2 "3.6.1Design Optimization" %}}
*   {{% resource_link 1d39506a-8ae7-400e-107d-fe048008e5c2 "3.6.2Gradient Based Optimization" %}}
*   {{% resource_link da1cf617-8af1-53b1-4d4a-177f24979948 "3.6.3Unconstrained Gradient-Based Optimization Methods" %}}
*   {{% resource_link c0e755e7-48fd-33db-4782-88b736e0381c "3.6.4Finite Difference Methods" %}}
*   {{% resource_link 3cde12b3-c306-b87c-973f-5af561f4875f "3.6.5The 1d Search" %}}
*   {{% resource_link 3cde12b3-c306-b87c-973f-5af561f4875f "\>The 1d Search" %}}

3.6.4 Finite Difference Method Applied to 1D Convection
-------------------------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.19" "#anchorMO319" %}}

Generally the objective function and constraints are complex, nonlinear functions of the design variables which are not known analytically. We therefore cannot compute analytic derivatives for the required gradients and Hessian information. However, it is still possible to estimate the gradient and Hessian using other methods. The simplest approach is to use finite differences.

A one-sided finite difference requires \\(n+1\\) function evaluations. The gradient is estimated as

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial J}{\\partial x\_ j} \\approx \\frac{J(x\_1,x\_2,\\ldots ,x\_ j+\\Delta x\_ j, x\_{j+1},\\ldots ,x\_ n)-J(x\_1,x\_2,\\ldots ,x\_ j,x\_{j+1},\\ldots ,x\_ n)}{\\Delta x\_ j}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.75)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This approximation is first-order accurate: reducing \\(\\Delta x\_ j\\) by a factor of 2 reduces the error in the gradient by a factor of 2.

A more accurate estimate can be computed using a central difference, which requires \\(2n\\) function evaluations:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial J}{\\partial x\_ j} \\approx \\frac{J(x\_1,x\_2,\\ldots ,x\_ j+\\Delta x\_ j, x\_{j+1},\\ldots ,x\_ n)-J(x\_1,x\_2,\\ldots ,x\_ j-\\Delta x\_ j,x\_{j+1},\\ldots ,x\_ n)}{2\\Delta x\_ j}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.76)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This approximation is second-order accurate: reducing \\(\\Delta x\_ j\\) by a factor of 2 reduces the error in the gradient by a factor of 4.

The Hessian matrix can also be estimated using finite differences. A second-order central approximation of the \\((i,j)\\) entry of the Hessian matrix is given by:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial ^2 J}{\\partial x\_ i \\partial x\_ j} \\approx \\frac{J(x\_1,x\_2,\\ldots ,x\_ i+\\Delta x\_ i,\\ldots ,x\_ j+\\Delta x\_ j, x\_{j+1},\\ldots ,x\_ n)}{4\\Delta x\_ i\\Delta x\_ j} \\\\ + \\frac{J(x\_1,x\_2,\\ldots ,x\_ i-\\Delta x\_ i,\\ldots ,x\_ j-\\Delta x\_ j, x\_{j+1},\\ldots ,x\_ n)}{4\\Delta x\_ i\\Delta x\_ j} \\\\ - \\frac{J(x\_1,x\_2,\\ldots ,x\_ i-\\Delta x\_ i,\\ldots ,x\_ j+\\Delta x\_ j, x\_{j+1},\\ldots ,x\_ n)}{4\\Delta x\_ i\\Delta x\_ j} \\\\ - \\frac{J(x\_1,x\_2,\\ldots ,x\_ i+\\Delta x\_ i,\\ldots ,x\_ j-\\Delta x\_ j, x\_{j+1},\\ldots ,x\_ n)}{4\\Delta x\_ i\\Delta x\_ j}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.77)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

BackUnconstrained Gradient-Based Optimization Methods ContinueThe 1d Search