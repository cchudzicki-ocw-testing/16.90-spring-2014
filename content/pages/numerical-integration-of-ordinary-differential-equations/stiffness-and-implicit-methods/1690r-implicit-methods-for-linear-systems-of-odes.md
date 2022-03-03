---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.7 Stiffness and Implicit Methods
parent_type: CourseSection
parent_uid: 935324e3-1ab2-cb57-9059-0ba1f034fcd5
title: 1.7 Stiffness and Implicit Methods
uid: 543e8406-3445-482c-0202-05c77ce31e71
---

*   {{% resource_link 900cc931-acfb-c435-72d7-f303ce81ef83 "\<Spectral Condition Number" %}}
*   {{% resource_link 935324e3-1ab2-cb57-9059-0ba1f034fcd5 "1.7.1Stiffness" %}}
*   {{% resource_link 900cc931-acfb-c435-72d7-f303ce81ef83 "1.7.2Spectral Condition Number" %}}
*   {{% resource_link 543e8406-3445-482c-0202-05c77ce31e71 "1.7.3Implicit Methods for Linear Systems of ODEs" %}}
*   {{% resource_link b363c2d0-1814-cf4c-0cb3-6fe540840d02 "1.7.4Newton-Raphson Implement Implicit Methods on Nonlinear Problems" %}}
*   {{% resource_link 84564160-240c-f3be-e329-df42818d2eaa "1.7.5Apply Newton-Rhapson" %}}
*   {{% resource_link b363c2d0-1814-cf4c-0cb3-6fe540840d02 "\>Newton-Raphson Implement Implicit Methods on Nonlinear Problems" %}}

1.7.3 Implicit Methods for Linear Systems of ODE's
--------------------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.9" "#anchorMO19" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.11" "#anchorMO111" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.12" "#anchorMO112" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.13" "#anchorMO113" %}}

While implicit methods can allow significantly larger timesteps, they do involve more work than explicit methods. Consider the forward method applied to \\(u\_ t = Au\\) where \\(A\\) is a \\(d \\times d\\) matrix.

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} = v^ n + {\\Delta t}A v^ n.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.122)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In this explicit algorithm, the largest computational cost is the matrix vector multiply, \\(A v^ n\\) which is an \\(O(d^2)\\) operation. Now, for backward Euler,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} = v^ n + {\\Delta t}A v^{n+1}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.123)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Re-arranging to solve for \\(v^{n+1}\\) gives:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^{n+1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^ n + {\\Delta t}A v^{n+1},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.124)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^{n+1} - {\\Delta t}A v^{n+1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^ n,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.125)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left(I - {\\Delta t}A\\right)v^{n+1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^ n,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.126)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, to find \\(v^{n+1}\\) requires the solution of a \\(d \\times d\\) system of equations which is an \\(O(d^3)\\) cost. As a result, for large systems, the cost of the \\(O(d^3)\\) linear solution may begin to outweigh the benefits of the larger timesteps that are possible when using implicit methods.

BackSpectral Condition Number ContinueNewton-Raphson Implement Implicit Methods on Nonlinear Problems