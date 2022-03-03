---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.2 Partial Differential Equations
parent_type: CourseSection
parent_uid: 735249e6-5cf9-7136-d3a6-4f4d3458178c
title: 2.2 Partial Differential Equations
uid: d923673e-05c6-3f48-9244-d3fc50c46901
---

*   {{% resource_link e6408661-a4be-8cfb-3204-ee1581c8dff1 "\<Convection-Diffusion" %}}
*   {{% resource_link 735249e6-5cf9-7136-d3a6-4f4d3458178c "2.2.1Conservation Laws in Integral and Differential Form" %}}
*   {{% resource_link 53d47d94-d1a2-5853-95d6-3d7a71ad1144 "2.2.2One-Dimensional Burgers Equation" %}}
*   {{% resource_link 5b35a359-99c0-aad1-8b33-6126f6b0a143 "2.2.3Convection" %}}
*   {{% resource_link 24dc2345-7e49-426d-09d2-77e4cb2d00f0 "2.2.4Characteristics for One-Dimensional Burgers Equation" %}}
*   {{% resource_link 91200789-ca43-fa38-473a-bc690667c305 "2.2.5Diffusion" %}}
*   {{% resource_link e6408661-a4be-8cfb-3204-ee1581c8dff1 "2.2.6Convection-Diffusion" %}}
*   {{% resource_link d923673e-05c6-3f48-9244-d3fc50c46901 "2.2.7Linear Elasticity" %}}
*   {{% resource_link 02467893-75dd-44cc-fcac-58f1a4ee9702 "\>Introduction to Finite Difference Methods" %}}

2.2.7 Linear Elasticity
-----------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.2" "#anchorMO22" %}}

In addition to fluid dynamics and heat transfer, structural mechanics is a key field in aerospace engineering. In this class, we will utilize forms of the linear elasticity equations as examples. These equations are commonly derived through application of Newton's Law to an elastic solid. The resulting partial differential equations are frequently written in indicial notation as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\rho \\dfrac {\\partial ^2 u\_ i}{\\partial t^2} = \\dfrac {\\partial \\sigma \_{ji}}{\\partial x\_ j} + f\_ i\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.38)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}
{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\epsilon \_{ij} = \\frac{1}{2}\\left(\\dfrac {\\partial u\_ i}{\\partial x\_ j} + \\dfrac {\\partial u\_ j}{\\partial x\_ i}\\right)\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.39)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}
{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\sigma \_{ij} = C\_{ijkl}\\epsilon \_{kl}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.40)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\rho\\) is the density of the material, \\(u\_ i(\\vec{x},t)\\) is the displacement in the \\(i-\\)th coordinate direction, \\(\\sigma \_{ij}\\) is the stress in the \\(i\\) direction acting on a plane with normal in the \\(j-\\)direction, \\(f\_ i\\) is the body force in the \\(i-\\)direction and \\(\\epsilon \_{ij}\\) is the strain. The stress and strains are related through the generalized Hooke's Law.

Hooke's Law for Isotropic Materials
-----------------------------------

For isotropic materials, i.e. materials in which the stress-strain relationship is the same independent of orientation of the material, Hooke's Law can be reduced to the following form,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[\\begin{array}{c} \\sigma \_{11} \\\\ \\sigma \_{22} \\\\ \\sigma \_{33} \\\\ \\sigma \_{23} \\\\ \\sigma \_{13} \\\\ \\sigma \_{12} \\end{array}\\right\] = \\left\[\\begin{array}{cccccc} \\lambda + 2\\mu & \\lambda & \\lambda & 0 & 0 & 0 \\\\ \\lambda & \\lambda + 2\\mu & \\lambda & 0 & 0 & 0 \\\\ \\lambda & \\lambda & \\lambda + 2\\mu & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 2\\mu & 0 & 0 \\\\ 0 & 0 & 0 & 0 & 2\\mu & 0 \\\\ 0 & 0 & 0 & 0 & 0 & 2\\mu \\end{array}\\right\] \\left\[\\begin{array}{c} \\epsilon \_{11} \\\\ \\epsilon \_{22} \\\\ \\epsilon \_{33} \\\\ \\epsilon \_{23} \\\\ \\epsilon \_{13} \\\\ \\epsilon \_{12} \\end{array}\\right\]\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.41)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The constants \\(\\lambda\\) and \\(\\mu\\) are often expressed in terms of the Young's Modulus \\((E)\\) and Poissons ration \\((\\nu )\\) as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\lambda = \\frac{E\\nu }{(1+\\nu )(1-2\\nu )}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.42)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}
{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mu = \\frac{E}{2(1+\\nu )}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.43)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This Hooke's Law relationship can also be written compactly using indicial notation as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\sigma \_{ij} = 2\\mu \\epsilon \_{ij} + \\delta \_{ij} \\lambda \\epsilon \_{kk}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.44)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\delta \_{ij}\\) is the Kronecker delta function.

BackConvection-Diffusion ContinueIntroduction to Finite Difference Methods