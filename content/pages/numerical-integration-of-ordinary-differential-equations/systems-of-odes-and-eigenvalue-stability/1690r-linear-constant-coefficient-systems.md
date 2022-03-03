---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.6 Systems of ODE's and Eigenvalue Stability
parent_type: CourseSection
parent_uid: 36e637ce-d6ff-e05d-3606-0d537611ad2e
title: 1.6 Systems of ODE's and Eigenvalue Stability
uid: e8dbfb22-04cb-6fc4-431e-0b32e5ea65da
---

*   {{< resource_link 36e637ce-d6ff-e05d-3606-0d537611ad2e "\<Systems of ODE's and Eigenvalue Stability" >}}
*   {{< resource_link 36e637ce-d6ff-e05d-3606-0d537611ad2e "1.6.1Nonlinear Systems" >}}
*   {{< resource_link e8dbfb22-04cb-6fc4-431e-0b32e5ea65da "1.6.2Linear Constant Coefficient Systems" >}}
*   {{< resource_link 04ce95ca-3b3a-cc38-5d83-81923a3dd6fe "1.6.3Eigenvalue Stability for a Linear ODE" >}}
*   {{< resource_link 64bbf174-0326-6a46-283d-2d2450cf7589 "1.6.4Imaginary Eigenvalues" >}}
*   {{< resource_link 04ce95ca-3b3a-cc38-5d83-81923a3dd6fe "\>Eigenvalue Stability for a Linear ODE" >}}

1.6.2 Linear Constant Coefficient Systems
-----------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.1" "#anchorMO11" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.2" "#anchorMO12" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.3" "#anchorMO13" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.4" "#anchorMO14" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.9" "#anchorMO19" >}}

The analysis of numerical methods applied to linear, constant coefficient systems can provide significant insight into the behavior of numerical methods for nonlinear problems. Consider the following problem,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u\_ t = A u, \\label{equ:ODElinear\_ sys}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.90)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(A\\) is a \\(d \\times d\\) matrix. Assuming that a complete set of eigenvectors exists, the matrix \\(A\\) can be decomposed as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[A = R\\Lambda R^{-1}, \\qquad \\Lambda = \\mbox{diag}(\\lambda \_1, \\lambda \_2, \\cdots , \\lambda \_ d), \\qquad R = \\left(\\begin{array}{c|c|c|c|c}r\_1 & r\_2 & r\_3 & \\cdots & r\_ d \\\\ \\end{array}\\right) \\label{equ:eigen}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.91)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The solution to Equation [1.90](javascript: void(0)) can be derived as follows,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle u\_ t\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle A u\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.92)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle u\_ t\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle R\\Lambda R^{-1} u\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.93)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle R^{-1} u\_ t\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\Lambda R^{-1} u\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.94)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, defining \\(w = R^{-1} u\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[w\_ t = \\Lambda w.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.95)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since \\(\\Lambda\\) is a diagonal matrix, this system of equations is actually uncoupled from each other, so that each of the eigenmodes has its own independent evolution equation,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[(w\_ j)\_ t = \\lambda \_ j w\_ j, \\qquad \\mbox{for each } j = 1 \\mbox{ to } d\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.96)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since each of the eigenmodes has a solution \\(w\_ j(t) = w\_ j(0)\\exp (\\lambda \_ j t)\\), then the solution for \\(u(t)\\) can be written as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u(t) = \\sum \_{j=1}^ d w\_ j(0) r\_ j e^{\\lambda \_ j t}. \\label{equ:ODElinear\_ sys\_ solution}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.97)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note that the eigenvalues are in general complex, \\(\\lambda \_ j = {\\lambda \_ j}\_ r + i {\\lambda \_ j}\_ i\\). The imaginary part of the eigenvalues determines the frequency of oscillations, and the real part of the eigenvalues determines the growth or decay rate. Specifically,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[e^{\\lambda t} = e^{(\\lambda \_ r + i \\lambda \_ i)t} = \\left(\\cos \\lambda \_ i t + i\\sin \\lambda \_ i t\\right) e^{ \\lambda \_ r t}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.98)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, when \\(\\lambda \_ r > 0\\), the solution will grow unbounded as \\(t \\rightarrow \\infty\\).

BackSystems of ODE's and Eigenvalue Stability ContinueEigenvalue Stability for a Linear ODE