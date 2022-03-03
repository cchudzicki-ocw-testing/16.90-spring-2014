---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.2 Partial Differential Equations
parent_type: CourseSection
parent_uid: 735249e6-5cf9-7136-d3a6-4f4d3458178c
title: 2.2 Partial Differential Equations
uid: 91200789-ca43-fa38-473a-bc690667c305
---

*   {{% resource_link 24dc2345-7e49-426d-09d2-77e4cb2d00f0 "\<Characteristics for One-Dimensional Burgers Equation" %}}
*   {{% resource_link 735249e6-5cf9-7136-d3a6-4f4d3458178c "2.2.1Conservation Laws in Integral and Differential Form" %}}
*   {{% resource_link 53d47d94-d1a2-5853-95d6-3d7a71ad1144 "2.2.2One-Dimensional Burgers Equation" %}}
*   {{% resource_link 5b35a359-99c0-aad1-8b33-6126f6b0a143 "2.2.3Convection" %}}
*   {{% resource_link 24dc2345-7e49-426d-09d2-77e4cb2d00f0 "2.2.4Characteristics for One-Dimensional Burgers Equation" %}}
*   {{% resource_link 91200789-ca43-fa38-473a-bc690667c305 "2.2.5Diffusion" %}}
*   {{% resource_link e6408661-a4be-8cfb-3204-ee1581c8dff1 "2.2.6Convection-Diffusion" %}}
*   {{% resource_link d923673e-05c6-3f48-9244-d3fc50c46901 "2.2.7Linear Elasticity" %}}
*   {{% resource_link e6408661-a4be-8cfb-3204-ee1581c8dff1 "\>Convection-Diffusion" %}}

2.2.5 Diffusion
---------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.2" "#anchorMO22" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.5" "#anchorMO25" %}}

In many engineering applications the dominant physical transport phenomenon is modeled as [**diffusion**](http://en.wikipedia.org/wiki/Diffusion). A distinguishing feature of diffusion is that it results in mixing or mass transport, without requiring bulk motion. Thus, diffusion should not be confused with convection, which is a transport mechanism that utilize bulk motion to move particles from one place to another. In Latin, "diffundere" means "to spread out". In 1831, Thomas Graham studied diffusion in gases, and the main phenomenon was described by him:

"...gases of different nature, when brought into contact, do not arrange themselves according to their density, the heaviest undermost, and the lighter uppermost, but they spontaneously diffuse, mutually and equally, through each other, and so remain in the intimate state of mixture for any length of time."

Heat conduction is another example of diffusion, the diffusion of thermal energy. This section presents the conservation law for diffusion in differential form and discuss the behavior of problems modeled with diffusion. Diffusion is characterized by a flux,\\(\\vec{F}\\) , of the form:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\vec{F} = -\\mu \\nabla U,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.32)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\mu\\) is the diffusion coefficient and \\(U\\) is the state. The differential form of the conservation law for the diffusion is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\dfrac {\\partial U}{\\partial t} - \\nabla \\cdot (\\mu \\nabla U) = S \\label{equ:diffconserv}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.33)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Equation [2.33](javascript: void(0)) is a second-order partial differential equation often called the diffusion equation or heat equation. Partial differential equations of this form arise in many applications including molecular diffusion and heat conduction.

One-dimensional Diffusion
-------------------------

We now illustrate the behavior of the diffusion equation considering a simple one-dimensional model problem. Consider the one-dimensional diffusion equation with constant \\(\\mu\\). The diffusion equation simplifies to

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\dfrac {\\partial U}{\\partial t} - \\mu \\dfrac {\\partial ^2 U}{\\partial x^2} = 0 \\label{equ:oneddiff}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.34)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Figure {{% resource_link 75ffae2c-9b44-67ac-9c7b-918a809c7347 "2.3" %}} shows the initial condition

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U\_0(x) = 0.75 e^{-(\\frac{x-0.5}{0.1})^2},\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.35)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

as well as the solution after a short time \\(t=0.05\\). The behavior of the diffusion equation is markedly different from what we have seen for the convection equation. The effect of the diffusion equation is to "smooth" out the conserved state in regions of steep gradients.

{{< resource 75ffae2c-9b44-67ac-9c7b-918a809c7347 >}}

**Figure 2.3**: One-dimensional diffusion problem, \\(\\mu =1\\)

Unlike in the case of convection, (where the domain of dependence is along characteristics), the solution at any point \\((\\vec{x},t)\\) for the diffusion equation depends on the solution everywhere else in the domain. Thus the domain of dependence at any point \\((\\vec{x}, t)\\) is the entire domain at all previous time.

{{< resource 2ecb26a0-1f93-3580-ad6a-2492f2aa7bf9 >}}

**Figure 2.4**: Another one-dimensional diffusion problem

BackCharacteristics for One-Dimensional Burgers Equation ContinueConvection-Diffusion