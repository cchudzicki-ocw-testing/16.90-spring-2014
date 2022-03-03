---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.2 Partial Differential Equations
parent_type: CourseSection
parent_uid: 735249e6-5cf9-7136-d3a6-4f4d3458178c
title: 2.2 Partial Differential Equations
uid: e6408661-a4be-8cfb-3204-ee1581c8dff1
---

*   {{< resource_link 91200789-ca43-fa38-473a-bc690667c305 "\<Diffusion" >}}
*   {{< resource_link 735249e6-5cf9-7136-d3a6-4f4d3458178c "2.2.1Conservation Laws in Integral and Differential Form" >}}
*   {{< resource_link 53d47d94-d1a2-5853-95d6-3d7a71ad1144 "2.2.2One-Dimensional Burgers Equation" >}}
*   {{< resource_link 5b35a359-99c0-aad1-8b33-6126f6b0a143 "2.2.3Convection" >}}
*   {{< resource_link 24dc2345-7e49-426d-09d2-77e4cb2d00f0 "2.2.4Characteristics for One-Dimensional Burgers Equation" >}}
*   {{< resource_link 91200789-ca43-fa38-473a-bc690667c305 "2.2.5Diffusion" >}}
*   {{< resource_link e6408661-a4be-8cfb-3204-ee1581c8dff1 "2.2.6Convection-Diffusion" >}}
*   {{< resource_link d923673e-05c6-3f48-9244-d3fc50c46901 "2.2.7Linear Elasticity" >}}
*   {{< resource_link d923673e-05c6-3f48-9244-d3fc50c46901 "\>Linear Elasticity" >}}

2.2.6 Convection-Diffusion
--------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.1" "#anchorMO21" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.2" "#anchorMO22" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.5" "#anchorMO25" >}}

In practice, both convection and diffusion are important phenomenon governing fluid dynamics. While convection may be the dominant transport mechanism in most of a flow, accounting for diffusion near solid boundaries may be essential for accurately computing engineering quantities such as drag or heat transfer. The convection-diffusion equation is derived from a general conservation law including both convective and diffusive fluxes. In differential form, the convection-diffusion equation is

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\dfrac {\\partial U}{\\partial t} + \\vec{v} \\cdot \\nabla U - \\nabla \\cdot ( \\mu \\nabla U ) = S.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.36)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The convection-diffusion equation arises in many engineering applications ranging from heat transfer to statistical mechanics (and even in finance!). Solutions of the convection-diffusion equation exhibit behavior which is the combined effect of both convection and diffusion. A key question which naturally arises is how significant are the relative effects of convection and diffusion. This is governed by the non-dimensional Peclet number (in aerodynamics applications, the Reynolds number is equivalent).

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[Pe = \\frac{|\\vec{v}| L}{\\mu }\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.37)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(L\\) is a characteristic length scale for the problem of interest. When \\(Pe \\ll 1\\) diffusion effects are dominant, and convection plays a relatively small role. On the other hand, when \\(Pe \\gg 1\\) convection is the dominant transport mechanism. Figures {{< resource_link 4bb6da2b-f7f7-caf5-3f5f-5dab915d31f7 "2.5" >}}, {{< resource_link 15190016-438f-73a0-a57e-dc9c90a9cc06 "2.6" >}}, {{< resource_link d3353a2e-60cc-ec44-4c2d-08541d8ebd5a "2.7" >}} show solutions for the one-dimensional convection-diffusion problem with Peclet numbers \\(10, 100\\) and \\(1000\\) (\\(\\vec{v}=1\\) is fixed). As the Peclet number increases the solution of the convection-diffusion problem approaches that of the pure convection problem.

{{< resource 4bb6da2b-f7f7-caf5-3f5f-5dab915d31f7 >}}

**Figure 2.5**: One-dimensional convection-diffusion problem, \\(Pe=10\\)

{{< resource 15190016-438f-73a0-a57e-dc9c90a9cc06 >}}

**Figure 2.6**: One-dimensional convection-diffusion problem, \\(Pe=100\\)

{{< resource d3353a2e-60cc-ec44-4c2d-08541d8ebd5a >}}

**Figure 2.7**: One-dimensional convection-diffusion problem, \\(Pe=1000\\)

BackDiffusion ContinueLinear Elasticity