---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 2: Numerical Methods for Partial Differential Equations'
parent_type: CourseSection
parent_uid: 125c58ac-6a34-5a7c-bba8-de2d3160cb8b
title: 2.11 The Finite Element Method for Two-Dimensional Diffusion
uid: c782bcc9-abb3-f6bc-c638-027dfffdc386
---

*   {{% resource_link 365c70a7-4666-ed1c-d140-8aeb96bff4a6 "\<Boundary Conditions for Finite Elements" %}}
*   {{% resource_link c782bcc9-abb3-f6bc-c638-027dfffdc386 "2.11.1Overview" %}}
*   {{% resource_link 16176028-e869-5612-f636-568d503833fc "2.11.2Reference Element and Linear Elements" %}}
*   {{% resource_link 6075ecc5-d133-cbcb-277c-06977e6970ea "2.11.3Differentiation using the Reference Element" %}}
*   {{% resource_link d29ce1ed-3626-60b8-be9b-f2741bbc6ee9 "2.11.4Construction of the Stiffness Matrix" %}}
*   {{% resource_link cd2d971f-e847-d266-f0b1-555caab639d4 "2.11.5Integration in the Reference Element" %}}
*   {{% resource_link 16176028-e869-5612-f636-568d503833fc "\>Reference Element and Linear Elements" %}}

2.11.1 Overview
---------------

In this lecture, we will consider the finite element approximation of the two-dimensional diffusion problem,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\nabla \\cdot \\left(k \\nabla T\\right) + f = 0. \\label{equ:dif2d}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.259)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

As in the previous discussion of the method of weighted residuals and the finite element method, the approximate solution will have the form

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tilde{T}(x,y) = \\sum \_{j=1}^{N} a\_ j \\phi \_ j(x,y),\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.260)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\phi \_ j(x,y)\\) are the known basis functions and the \\(a\_ j\\) are the unknown coefficients to be determined for the specific problem. Following the Galerkin method of weighted residuals, we will weight Equation ([2.259](javascript: void(0))) by one of the basis functions and integrate the diffusion term by parts to give the following weighted residual:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[R\_ i \\equiv \\int \_{\\delta \\Omega } \\phi \_ i\\, k\\nabla \\tilde{T}\\cdot \\vec{n}\\, ds - \\int \_{\\Omega } \\nabla \\phi \_ i \\cdot \\left(k\\nabla \\tilde{T}\\right)\\, dA + \\int \_{\\Omega } \\phi \_ i f\\, dA = 0. \\label{equ:mwr\_ dif2d}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.261)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

BackBoundary Conditions for Finite Elements ContinueReference Element and Linear Elements