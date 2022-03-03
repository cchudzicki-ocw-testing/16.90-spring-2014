---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 2: Numerical Methods for Partial Differential Equations'
parent_type: CourseSection
parent_uid: 125c58ac-6a34-5a7c-bba8-de2d3160cb8b
title: 2.4 Analysis of Finite Difference Methods
uid: c9ae23f7-07d4-0d5c-c85b-b19ebf476df0
---

*   {{< resource_link 31ee5fcb-1e6b-78ca-5cb4-d3cb7c073c22 "\<Forward Time-Backward Space FTBS" >}}
*   {{< resource_link c9ae23f7-07d4-0d5c-c85b-b19ebf476df0 "2.4.1Local Truncation Error for a Derivative Approximation" >}}
*   {{< resource_link 9064faf9-febc-8ca2-e94e-1b057fcc34be "2.4.2Truncation Error of Central Difference Approximation" >}}
*   {{< resource_link ba32080c-16da-eb92-bc6f-615dc10a7e31 "2.4.3Truncation Error for a PDE" >}}
*   {{< resource_link 404d1192-4d4a-07bb-c158-0c3605807e8e "2.4.4Finite Difference Methods in Matrix Form" >}}
*   {{< resource_link 7e5587c8-fac2-cbac-56c4-7e6cdfc52004 "2.4.5General Finite Difference Approximations" >}}
*   {{< resource_link 7d8e6a54-9392-cde6-ff4d-914e606da194 "2.4.6Boundary Conditions for Finite Differences" >}}
*   {{< resource_link 9064faf9-febc-8ca2-e94e-1b057fcc34be "\>Truncation Error of Central Difference Approximation" >}}

2.4.1 Local Truncation Error for a Derivative Approximation
-----------------------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.8" "#anchorMO28" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.9" "#anchorMO29" >}}

In the discussion of ODE integration, we used the ideas of consistency and stability to prove convergence through the Dahlquist Equivalence Theorem. Similar concepts also exist for PDE discretizations, however, we cannot cover these here. We will briefly review the local truncation error for finite difference approximations of derivatives here and discuss its application in computing the truncation error of a PDE in Section {{< resource_link ba32080c-16da-eb92-bc6f-615dc10a7e31 "2.4.3" >}}.

Suppose we use a backwards difference, \\(\\delta \_ x^- U\_ i\\) to approximate the first derivative, \\(U\_ x\\) at point \\(i\\). The local truncation error for this derivative approximation can be calculated using Taylor series as we have done in the past:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\tau\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\equiv\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\delta \_ x^{-} U\_ i - {U\_ x}\_ i ,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.61)
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
\\(\\displaystyle \\frac{1}{{\\scriptstyle \\Delta } x}\\left( U\_ i - U\_{i-1}\\right) - {U\_ x}\_ i,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.62)
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
\\(\\displaystyle \\frac{1}{{\\scriptstyle \\Delta } x}\\left\[ U\_ i - \\left( U\_ i - {\\scriptstyle \\Delta } x{U\_ x}\_ i + \\frac{1}{2}{\\scriptstyle \\Delta } x^2{U\_{xx}}\_ i + O({\\scriptstyle \\Delta } x^3)\\right)\\right\] - {U\_ x}\_ i,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.63)
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
\\(\\displaystyle -\\frac{1}{2}{\\scriptstyle \\Delta } x{U\_{xx}}\_ i + O({\\scriptstyle \\Delta } x^2).\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.64)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the analysis shows that the backwards difference is a first-order accurate discretization of the derivative at node \\(i\\).

BackForward Time-Backward Space FTBS ContinueTruncation Error of Central Difference Approximation