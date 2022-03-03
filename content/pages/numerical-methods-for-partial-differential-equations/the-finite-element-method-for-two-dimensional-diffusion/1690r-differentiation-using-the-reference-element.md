---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.11 The Finite Element Method for Two-Dimensional Diffusion
parent_type: CourseSection
parent_uid: c782bcc9-abb3-f6bc-c638-027dfffdc386
title: 2.11 The Finite Element Method for Two-Dimensional Diffusion
uid: 6075ecc5-d133-cbcb-277c-06977e6970ea
---

*   {{% resource_link 16176028-e869-5612-f636-568d503833fc "\<Reference Element and Linear Elements" %}}
*   {{% resource_link c782bcc9-abb3-f6bc-c638-027dfffdc386 "2.11.1Overview" %}}
*   {{% resource_link 16176028-e869-5612-f636-568d503833fc "2.11.2Reference Element and Linear Elements" %}}
*   {{% resource_link 6075ecc5-d133-cbcb-277c-06977e6970ea "2.11.3Differentiation using the Reference Element" %}}
*   {{% resource_link d29ce1ed-3626-60b8-be9b-f2741bbc6ee9 "2.11.4Construction of the Stiffness Matrix" %}}
*   {{% resource_link cd2d971f-e847-d266-f0b1-555caab639d4 "2.11.5Integration in the Reference Element" %}}
*   {{% resource_link d29ce1ed-3626-60b8-be9b-f2741bbc6ee9 "\>Construction of the Stiffness Matrix" %}}

2.11.3 Differentiation using the Reference Element
--------------------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.17" "#anchorMO217" %}}

To find the derivative of \\(\\tilde{T}\\) with respect to \\(x\\) (or similarly \\(y\\)) within an element, we differentiate the three nodal basis functions within the element:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\tilde{T}\_ x\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{\\partial }{\\partial x}\\left(\\sum \_{j=1}^{3} a\_ j\\phi \_ j\\right),\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.271)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\sum \_{j=1}^{3} a\_ j\\frac{\\partial \\phi \_ j}{\\partial x}.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.272)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

To find the \\(x\\)-derivatives of each of the \\(\\phi \_ j\\)'s, the chain rule is applied:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial \\phi \_ j}{\\partial x} = \\frac{\\partial \\phi \_ j}{\\partial \\xi \_1}\\frac{\\partial \\xi \_1}{\\partial x} + \\frac{\\partial \\phi \_ j}{\\partial \\xi \_2}\\frac{\\partial \\xi \_2}{\\partial x}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.273)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Similarly, to find the derivatives with respect to \\(y\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial \\phi \_ j}{\\partial y} = \\frac{\\partial \\phi \_ j}{\\partial \\xi \_1}\\frac{\\partial \\xi \_1}{\\partial y} + \\frac{\\partial \\phi \_ j}{\\partial \\xi \_2}\\frac{\\partial \\xi \_2}{\\partial y}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.274)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The calculation of the derivatives of \\(\\phi \_ j\\) with respect to the \\(\\xi\\) variables gives:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{\\partial \\phi \_1}{\\partial \\xi \_1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -1, \\qquad \\frac{\\partial \\phi \_1}{\\partial \\xi \_2} = -1,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.275)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{\\partial \\phi \_2}{\\partial \\xi \_1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 1, \\qquad \\frac{\\partial \\phi \_2}{\\partial \\xi \_2} = 0,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.276)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{\\partial \\phi \_3}{\\partial \\xi \_1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0, \\qquad \\frac{\\partial \\phi \_3}{\\partial \\xi \_2} = 1.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.277)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The only remaining terms are the calculation of \\(\\frac{\\partial \\xi \_1}{\\partial x}\\), \\(\\frac{\\partial \\xi \_2}{\\partial x}\\), etc. which can be found by differentiating Equation ([2.270](javascript: void(0))),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{\\partial \\vec{\\xi }}{\\partial \\vec{x}}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left(\\begin{array}{cc} x\_2-x\_1 & x\_3-x\_1 \\\\ y\_2-y\_1 & y\_3-y\_1\\end{array}\\right)^{-1},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.278)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{1}{J} \\left(\\begin{array}{cc} y\_3-y\_1 & -(x\_3-x\_1) \\\\ -(y\_2-y\_1) & x\_2-x\_1\\end{array}\\right),\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.279)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[J = (x\_2-x\_1)(y\_3-y\_1) - (x\_3-x\_1)(y\_2-y\_1).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.280)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note that the Jacobian, \\(J\\), is equal to twice the area of the triangular element.

BackReference Element and Linear Elements ContinueConstruction of the Stiffness Matrix