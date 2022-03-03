---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.4 Analysis of Finite Difference Methods
parent_type: CourseSection
parent_uid: c9ae23f7-07d4-0d5c-c85b-b19ebf476df0
title: 2.4 Analysis of Finite Difference Methods
uid: ba32080c-16da-eb92-bc6f-615dc10a7e31
---

*   {{< resource_link 9064faf9-febc-8ca2-e94e-1b057fcc34be "\<Truncation Error of Central Difference Approximation" >}}
*   {{< resource_link c9ae23f7-07d4-0d5c-c85b-b19ebf476df0 "2.4.1Local Truncation Error for a Derivative Approximation" >}}
*   {{< resource_link 9064faf9-febc-8ca2-e94e-1b057fcc34be "2.4.2Truncation Error of Central Difference Approximation" >}}
*   {{< resource_link ba32080c-16da-eb92-bc6f-615dc10a7e31 "2.4.3Truncation Error for a PDE" >}}
*   {{< resource_link 404d1192-4d4a-07bb-c158-0c3605807e8e "2.4.4Finite Difference Methods in Matrix Form" >}}
*   {{< resource_link 7e5587c8-fac2-cbac-56c4-7e6cdfc52004 "2.4.5General Finite Difference Approximations" >}}
*   {{< resource_link 7d8e6a54-9392-cde6-ff4d-914e606da194 "2.4.6Boundary Conditions for Finite Differences" >}}
*   {{< resource_link 404d1192-4d4a-07bb-c158-0c3605807e8e "\>Finite Difference Methods in Matrix Form" >}}

2.4.3 Truncation Error for a PDE
--------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.8" "#anchorMO28" >}}

In the discussion of ODE integration, we used the ideas of consistency and stability to prove convergence through the Dahlquist Equivalence Theorem. Similar concepts also exist for PDE discretizations, however, we cannot cover these here. We will briefly look at the truncation error for a partial differential equation. We have already discussed the local truncation error for finite difference approximation of derivatives.

Similar to the ODE case, the truncation error is **defined as the remainder after an exact solution to the governing equation is substituted into the finite difference approximation**. For example, suppose we are using the FTCS algorithm in Equation ([2.57](javascript: void(0))) to approximate the one-dimensional convection-diffusion equation. Then the local truncation error for the PDE approximation is defined as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tau \\equiv \\frac{U\_ i^{n+1}-U\_ i^ n}{{\\Delta t}} + u\_{i}^ n\\delta \_{2x} U^ n\_{i} - \\mu \\delta ^2\_ x U^ n\_{i}, \\label{equ:lte\_ ftcs}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.65)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(U(x,t)\\) is an exact solution to Equation ([2.55](javascript: void(0))).

Note that the truncation error defined here for PDE's is not quite a direct analogy with the standard definition of local truncation error used in ODE integration, specifically in Equation ([1.49](javascript: void(0))). In particular, in the ODE case, the truncation error is defined as the difference between the numerical solution and the exact solution after one step of the method (starting from exact values). However, in the PDE case, we have defined the truncation error as the remainder after an exact solution is substituted into the numerical method when the numerical method is written in a form that approximates the governing PDE.

Except for this difference in the definition, the calculation of the local truncation follows the same procedure as in the ODE case in which Taylor series substitutions are used to expand the error in powers of \\({\\Delta t}\\). Continuing on with our example, we use Taylor series of \\(U\\) about \\(t=t^ n\\) and \\(x=x\_ i\\). However, we can use our previous results from the analysis of the truncation error of spatial derivatives. Specifically, we showed in during in-class discussions that,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\delta \_{2x} U\_ i\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {U\_ x}\_ i + \\frac{1}{6} {\\scriptstyle \\Delta } x^2 {U\_{xxx}}\_ i + O({\\scriptstyle \\Delta } x^4)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.66)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\delta \_{x}^{2} U\_ i\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {U\_{xx}}\_ i + \\frac{1}{12}{\\scriptstyle \\Delta } x^2 {U\_{xxxx}}\_ i + O({\\scriptstyle \\Delta } x^4)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.67)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Using these results,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tau = \\frac{U\_ i^{n+1}-U\_ i^ n}{{\\Delta t}} + u\_{i}^ n\\left\[{U\_ x}\_ i^ n + \\frac{1}{6}{\\scriptstyle \\Delta } x^2 {U\_{xxx}}\_ i^ n + O({\\scriptstyle \\Delta } x^4) \\right\] - \\mu \\left\[{U\_{xx}}\_ i^ n + \\frac{1}{12}{\\scriptstyle \\Delta } x^2 {U\_{xxxx}}\_ i^ n + O({\\scriptstyle \\Delta } x^4) \\right\]\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.68)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, performing a similar Taylor series of the time derivative approximation gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{U^{n+1} - U^ n}{{\\Delta t}} = {U\_ t}^ n + \\frac{1}{2}{\\Delta t}{U\_{tt}}^ n + O({\\Delta t}^2).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.69)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Substituting this into \\(\\tau\\) and collecting terms in powers of \\({\\Delta t}\\) and \\({\\scriptstyle \\Delta } x\\) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\tau\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {U\_ t}^ n\_ i + u\_{i}^ n {U\_ x}\_ i^ n - \\mu {U\_{xx}}\_ i^ n +\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.70)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{1}{2}{\\Delta t}{U\_{tt}}^ n\_ i + O({\\Delta t}^2) +\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.71)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{1}{6}{\\scriptstyle \\Delta } x^2 u\_{i}^ n {U\_{xxx}}\_ i^ n - \\frac{1}{12}{\\scriptstyle \\Delta } x^2 \\mu {U\_{xxxx}}\_ i^ n + O({\\scriptstyle \\Delta } x^4)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.72)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The first line of this equation is actually just the PDE, evaluated at \\(t=t^ n\\) and \\(x=x\_ i\\). Since \\(U\\) is an exact solution to the PDE, this is zero. The second line shows that the time discretization introduces an \\(O({\\Delta t})\\). The third line shows that the spatial discretization introduces an \\(O({\\scriptstyle \\Delta } x^2)\\) error. Thus, this numerical method is first-order accurate in time and second-order accurate in space.

**Summary** The truncation error is defined as the remainder after an exact solution to the governing equation is substituted into the finite difference approximation, and is computed using Taylor series expansions to expand the error in terms of \\({\\Delta t}.\\)

Exercise
--------

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp; First-order accurate &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; Second-order accurate &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; Third-order accurate &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; None of the above &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: Since the backwards difference is first-order accurate, the accuracy of the entire approximation is first-order.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackTruncation Error of Central Difference Approximation ContinueFinite Difference Methods in Matrix Form