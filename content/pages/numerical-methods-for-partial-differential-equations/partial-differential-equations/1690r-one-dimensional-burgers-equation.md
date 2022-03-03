---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.2 Partial Differential Equations
parent_type: CourseSection
parent_uid: 735249e6-5cf9-7136-d3a6-4f4d3458178c
title: 2.2 Partial Differential Equations
uid: 53d47d94-d1a2-5853-95d6-3d7a71ad1144
---

*   {{% resource_link 735249e6-5cf9-7136-d3a6-4f4d3458178c "\<Partial Differential Equations" %}}
*   {{% resource_link 735249e6-5cf9-7136-d3a6-4f4d3458178c "2.2.1Conservation Laws in Integral and Differential Form" %}}
*   {{% resource_link 53d47d94-d1a2-5853-95d6-3d7a71ad1144 "2.2.2One-Dimensional Burgers Equation" %}}
*   {{% resource_link 5b35a359-99c0-aad1-8b33-6126f6b0a143 "2.2.3Convection" %}}
*   {{% resource_link 24dc2345-7e49-426d-09d2-77e4cb2d00f0 "2.2.4Characteristics for One-Dimensional Burgers Equation" %}}
*   {{% resource_link 91200789-ca43-fa38-473a-bc690667c305 "2.2.5Diffusion" %}}
*   {{% resource_link e6408661-a4be-8cfb-3204-ee1581c8dff1 "2.2.6Convection-Diffusion" %}}
*   {{% resource_link d923673e-05c6-3f48-9244-d3fc50c46901 "2.2.7Linear Elasticity" %}}
*   {{% resource_link 5b35a359-99c0-aad1-8b33-6126f6b0a143 "\>Convection" %}}

2.2.2 One-Dimensional Burgers' Equation
---------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.1" "#anchorMO21" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.2" "#anchorMO22" %}} 

Burgers' equation is a fundamental partial differential equation from fluid mechanics. It occurs in various areas, such as modeling of gas dynamics and traffic flow. It is named for Johannes Martinus Burgers (1895-1981). The one-dimensional Burgers' equation is given in differential form as:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial u}{\\partial t} + u \\frac{\\partial u}{\\partial x} = 0 \\label{equ:burgers}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.17)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; \\(U=u, \\vec{F}=u\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(U=u, \\vec{F}=u^2\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(U=\\frac{1}{2}u, \\vec{F}=u^2\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; \\(U=u,\\vec{F}=\\frac{1}{2}u^2\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: This solution can be verified by plugging in \\(\\vec{F} =\\frac{1}{2} u^2\\) and noting that \\(\\frac{\\partial \\vec{f}}{\\partial x} = \\frac{\\partial \\vec{F}}{\\partial u}\\frac{\\partial u}{\\partial x}\\) and we arrive that the above differential form.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackPartial Differential Equations ContinueConvection