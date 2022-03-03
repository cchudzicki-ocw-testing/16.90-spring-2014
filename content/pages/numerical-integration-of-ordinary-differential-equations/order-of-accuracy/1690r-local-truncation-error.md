---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.3 Order of Accuracy
parent_type: CourseSection
parent_uid: a3fbfbbd-e140-393b-aed5-af945a9316f9
title: 1.3 Order of Accuracy
uid: 6121a3ca-d8f1-c652-7821-6a952ea8ff2c
---

*   {{< resource_link a3fbfbbd-e140-393b-aed5-af945a9316f9 "\<Order of Accuracy" >}}
*   {{< resource_link a3fbfbbd-e140-393b-aed5-af945a9316f9 "1.3.1Errors" >}}
*   {{< resource_link 6121a3ca-d8f1-c652-7821-6a952ea8ff2c "1.3.2Local Truncation Error" >}}
*   {{< resource_link 09523d4b-aafc-8f4c-e9b7-d3d67ad30e7b "1.3.3Local Order of Accuracy" >}}
*   {{< resource_link 58553753-c9cc-c012-f030-d87844ae8db5 "1.3.4Definition of Multi-Step Methods" >}}
*   {{< resource_link ff3b4491-f1d1-d23e-2d3a-939de701c5c2 "1.3.5Example of Most Accurate Multi-Step Method" >}}
*   {{< resource_link 09523d4b-aafc-8f4c-e9b7-d3d67ad30e7b "\>Local Order of Accuracy" >}}

1.3.2 Local Truncation Error
----------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.5" "#anchorMO15" >}}

Global error measures the difference between the computed solution at a given time and the true solution of the initial value problem that we are trying to solve. Local error is the error made in one step of the numerical method. While we are generally interested in obtaining small global errors, local errors are the errors over which we have direct control. Both global and local accuracy are related to the behavior of the error as \\({\\Delta t}\\rightarrow 0\\). Convergence is related to global accuracy; for local accuracy we will see in {{< resource_link fab29380-eb66-91e4-e3ce-4dfce3f50fbe "1.5.1" >}} an important concept known as consistency.

If we can quantify how much the error changes in a single timestep, then we will have an indication of how much the error could change over a series of timesteps. Specifically, let's write the solution error, \\(e\\), at \\(t=T\\) as a sum of the change in error at each timestep,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[e(T) = u(T) - v^{T/{\\Delta t}} = \\sum \_{n=1}^{T/{\\Delta t}} \\Delta e^ n,\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.35)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\Delta e^ n\\) is the change in the error from iteration \\(n-1\\) to \\(n\\) (i.e. the local error). Suppose the local error is \\(O({\\Delta t}^{p+1})\\), then the global error might be expected to behave as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle e(T)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\sum \_{n=1}^{T/{\\Delta t}} \\Delta e^ n,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.36)
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
\\(\\displaystyle \\sum \_{n=1}^{T/{\\Delta t}} O({\\Delta t}^{p+1}),\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.37)
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
\\(\\displaystyle \\frac{T}{{\\Delta t}} O({\\Delta t}^{p+1})\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.38)
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
\\(\\displaystyle O({\\Delta t}^ p).\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.39)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the global error would decrease with \\({\\Delta t}\\) by one order less than the local error because the local errors sum for \\(T/{\\Delta t}\\) timesteps. However, we must be careful because the local errors do not have to sum this way, particularly if the numerical method is not stable. We will see in the next lecture that if a numerical method is both consistent and stable, this will be enough to guarantee convergence. For now, we concentrate on quantifying the local accuracy and leave the discussion of consistency and stability for another lecture.

The local error (usually called the local truncation error) is the difference between the approximate solution at step \\(n+1\\) and the solution at \\(t^{n+1}\\) of the ODE that passes through the previous computed point \\(v^ n\\). The local error can be evaluated by considering the difference between the approximate solution at step \\(n+1\\) computed using the exact solution for the required data and the exact solution at \\(t^{n+1}\\).

Example: Local error of the forward Euler method
------------------------------------------------

Let's consider the forward Euler method as an example. Recall, the forward Euler method is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} = v^ n + {\\Delta t}f(v^ n,t^ n).\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.40)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, for the forward Euler method, \\(v^{n+1} = v^{n+1}(v^ n,{\\Delta t},t^ n)\\). Then, if we substitute the exact solution into the right-hand side, we find,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1}(u^ n,{\\Delta t},t^ n) = u^ n + {\\Delta t}f(u^ n,t^ n).\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.41)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Recall our notation that \\(u\\) is the exact solution; in this discussion we use the superscript notation \\(u^ n = u(n{\\Delta t})\\) realizing that \\(u = u(t)\\). Therefore the equation above gives the value of \\(v^{n+1}\\) that would be computed if the exact solution were available at time \\(t^ n\\). The local truncation error for the forward Euler method is then,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mbox{Local truncation error} \\equiv v^{n+1}(u^ n,{\\Delta t},t^ n) - u^{n+1}. \\label{equ:local\_ error\_ fe}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.42)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Substitution gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mbox{Local truncation error} = u^ n + {\\Delta t}f(u^ n,t^ n) - u^{n+1}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.43)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The local order of accuracy is then found using a Taylor series expansion about \\(t = t^ n\\). Recall that \\(f(u^ n,t^ n) = u\_ t(t^ n)\\) and

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u(t^{n+1}) = u(t^ n) + {\\Delta t}u\_ t(t^ n) + \\frac{1}{2}{\\Delta t}^2 u\_{tt}(t^ n) + O({\\Delta t}^3).\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.44)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Substitution gives the local truncation error as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\mbox{Local truncation error}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle u^ n + {\\Delta t}f(u^ n,t^ n) - u^{n+1},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.45)
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
\\(\\displaystyle u(t^ n) + {\\Delta t}u\_ t(t^ n) - \\left\[u(t^ n) + {\\Delta t}u\_ t(t^ n) + \\frac{1}{2}{\\Delta t}^2 u\_{tt}(t^ n) + O({\\Delta t}^3)\\right\]\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.46)
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
\\(\\displaystyle -\\frac{1}{2}{\\Delta t}^2 u\_{tt}(t^ n) + O({\\Delta t}^3).\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.47)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the leading term of the local truncation error for the forward Euler method is \\(-\\frac{1}{2}{\\Delta t}^2 u\_{tt}(t^ n) = O({\\Delta t}^2)\\). Based on our previous argument, we expect that the global accuracy of the forward Euler method should be \\(O({\\Delta t})\\) (i.e. first order accuracy). This was in fact observed in Example {{< resource_link 513c00ff-c667-f8ca-ef14-9cb1db0b77a4 "1.5" >}}.

BackOrder of Accuracy ContinueLocal Order of Accuracy