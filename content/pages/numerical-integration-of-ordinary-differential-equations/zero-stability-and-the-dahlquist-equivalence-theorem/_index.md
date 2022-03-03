---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 1: Numerical Integration of Ordinary Differential Equations'
parent_type: CourseSection
parent_uid: 5cae4847-c59a-a247-c767-3c0c6b0abef1
title: 1.5 Zero Stability and the Dahlquist Equivalence Theorem
uid: fab29380-eb66-91e4-e3ce-4dfce3f50fbe
---

*   {{< resource_link bc0d43fe-1169-e2be-34aa-cfba7fd50607 "\<Rate of Convergence Global Order of Accuracy" >}}
*   {{< resource_link fab29380-eb66-91e4-e3ce-4dfce3f50fbe "1.5.1Consistency" >}}
*   {{< resource_link 69a13333-afb5-90ee-d339-c7fba31529fd "1.5.2Stability" >}}
*   {{< resource_link e726e961-fd26-9620-907a-1248b173744d "1.5.3Dahlquist Equivalence Theorem" >}}
*   {{< resource_link 69a13333-afb5-90ee-d339-c7fba31529fd "\>Stability" >}}

1.5.1 Consistency
-----------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.8" "#anchorMO18" >}}

As given in Section {{< resource_link 58553753-c9cc-c012-f030-d87844ae8db5 "1.3.4" >}}, an \\(s\\)-step multi-step method can be written as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} + \\sum \_{i=1}^ s \\alpha \_ i v^{n+1-i} - {\\Delta t}\\sum \_{i=0}^ s \\beta \_ i f^{n+1-i} = 0,\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.67)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where the forcing terms have been moved to the left-hand side. Substituting the exact solution, \\(u(t)\\), into the left-hand side will produce a remainder which is in fact the opposite of the truncation error (see Equation [1.49](javascript: void(0))),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u^{n+1} + \\sum \_{i=1}^ s \\alpha \_ i u^{n+1-i} - {\\Delta t}\\sum \_{i=0}^ s \\beta \_ i f^{n+1-i} = u^{n+1} - N(u^{n+1},u^ n, \\ldots , {\\Delta t}) = -\\tau \\label{equ:lte\_ consistency}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.68)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

If we only require that \\(\\tau \\rightarrow 0\\) (i.e. \\(\\tau = O({\\Delta t})\\)) as \\({\\Delta t}\\rightarrow 0\\), the method will not generally be consistent with the ODE. To see why, note that in the limit of \\({\\Delta t}\\rightarrow 0\\), the forcing terms will vanish since they are scaled by \\({\\Delta t}\\). Thus, \\(\\tau \\rightarrow 0\\) would place a constraint only on the \\(\\alpha\\)'s. Let's look at that constraint on the \\(\\alpha\\)'s to build some insight. Substituting Taylor series about \\(t=t^ n\\) for the values of \\(u\\) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u^{n+1} + \\sum \_{i=1}^ s \\alpha \_ i u^{n+1-i} = \\left(1 + \\sum \_{i=1}^ s \\alpha \_ i\\right)u^ n + O({\\Delta t}).\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.69)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, for \\(\\tau \\rightarrow 0\\) as \\({\\Delta t}\\rightarrow 0\\) requires,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[1 + \\sum \_{i=1}^ s \\alpha \_ i = 0. \\label{equ:consistency\_ con1}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.70)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This constraint can be interpreted as requiring a constant solution, i.e. \\(u(t) =\\) constant, to be a valid solution of the multi-step method. Clearly, this is not enough to guarantee consistency with the ODE since the ODE requires \\(u\_ t = f(u,t)\\).

To achieve a consistent discretization, we force \\(\\tau /{\\Delta t}\\rightarrow 0\\) (i.e. \\(\\tau = O({\\Delta t}^2)\\)). This stronger constraint can be shown to enforce that the ODE is satisfied in the limit of \\({\\Delta t}\\rightarrow 0\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{\\tau }{{\\Delta t}}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{N(u^{n+1},u^ n, \\ldots , {\\Delta t}) - u^{n+1}}{{\\Delta t}}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.71)
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
\\(\\displaystyle \\frac{N(u^{n+1},u^ n, \\ldots , {\\Delta t}) - \\left(u^ n + {\\Delta t}u\_ t^ n + O({\\Delta t}^2)\\right)}{{\\Delta t}}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.72)
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
\\(\\displaystyle \\frac{N(u^{n+1},u^ n, \\ldots , {\\Delta t}) - u^ n}{{\\Delta t}} - u\_ t^ n + O({\\Delta t})\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.73)
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
\\(\\displaystyle \\frac{N(u^{n+1},u^ n, \\ldots , {\\Delta t}) - u^ n}{{\\Delta t}} - f(u^ n,t^ n) + O({\\Delta t})\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.74)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, in the limit as \\({\\Delta t}\\rightarrow 0\\), to obtain \\(\\tau /{\\Delta t}\\rightarrow 0\\) then the slope of the numerical method (i.e. the first term) must be equal to the forcing at \\(t^ n\\). In other words, the multi-step discretization would satisfy the governing equation in the limit. An equivalent way to write this consistency constraint is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\lim \_{{\\Delta t}\\rightarrow 0} \\frac{1}{{\\Delta t}}\\left\[ u^{n+1} + \\sum \_{i=1}^ s \\alpha \_ i u^{n+1-i}\\right\] - \\sum \_{i=0}^ s \\beta \_ i f^{n+1-i} = u\_ t(t^ n) - f(u(t^ n),t^ n) = 0. \\label{equ:consistency\_ constraint}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.75)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In terms of the local accuracy, consistency requires that the multi-step method be at least first-order \\((p=1)\\) since \\(\\tau = O({\\Delta t}^{p+1})\\) and consistency requires that \\(\\tau /{\\Delta t}= O({\\Delta t}^ p)\\) must go to zero (i.e. \\(p \\geq 1\\)).

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp; \\(v^{n+1}=v^ n + \\Delta t f^{n+1}\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(v^{n+1} = v^ n + \\frac{1}{2} \\Delta t f^{n+1}\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(v^{n+1} = v^ n + \\frac{1}{2}\\Delta t f^ n\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(v^{n+1} = v^{n-1}\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: This is the backward Euler Method{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackRate of Convergence Global Order of Accuracy ContinueStability