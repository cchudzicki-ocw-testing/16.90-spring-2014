---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.4 Analysis of Finite Difference Methods
parent_type: CourseSection
parent_uid: c9ae23f7-07d4-0d5c-c85b-b19ebf476df0
title: 2.4 Analysis of Finite Difference Methods
uid: 7d8e6a54-9392-cde6-ff4d-914e606da194
---

*   {{< resource_link 7e5587c8-fac2-cbac-56c4-7e6cdfc52004 "\<General Finite Difference Approximations" >}}
*   {{< resource_link c9ae23f7-07d4-0d5c-c85b-b19ebf476df0 "2.4.1Local Truncation Error for a Derivative Approximation" >}}
*   {{< resource_link 9064faf9-febc-8ca2-e94e-1b057fcc34be "2.4.2Truncation Error of Central Difference Approximation" >}}
*   {{< resource_link ba32080c-16da-eb92-bc6f-615dc10a7e31 "2.4.3Truncation Error for a PDE" >}}
*   {{< resource_link 404d1192-4d4a-07bb-c158-0c3605807e8e "2.4.4Finite Difference Methods in Matrix Form" >}}
*   {{< resource_link 7e5587c8-fac2-cbac-56c4-7e6cdfc52004 "2.4.5General Finite Difference Approximations" >}}
*   {{< resource_link 7d8e6a54-9392-cde6-ff4d-914e606da194 "2.4.6Boundary Conditions for Finite Differences" >}}
*   {{< resource_link 3d8df8b8-2291-7094-b5a6-9893808a75cc "\>Introduction to Finite Volume Methods" >}}

2.4.6 Boundary Conditions for Finite Differences
------------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.3" "#anchorMO23" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.8" "#anchorMO28" >}}

In this section, we discuss the implementation of finite difference methods at boundaries. This discussion is not meant to be comprehensive, as the issues are many and often subtle. In particular, we only focus on Dirichlet boundary conditions.

A Dirichlet boundary condition is one in which the state is specified at the boundary. For example, in a heat transfer problem, the temperature might be known at the boundary. Dirichlet boundary conditions can be implemented in a relatively straightforward manner. For example, suppose that we are solving a one-dimensional convection-diffusion problem and we want the value of \\(U\\) at \\(i=0\\), to be \\(U\_{inlet}\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U\_0 = U\_{inlet}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.87)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

To implement this, we fix \\(U\_0 = U\_{inlet}\\) and apply the finite difference discretization only over the interior of the computational domain accounting for the known value of \\(U\_0\\) at any place where the interior discretization depends on it. For example, at the first interior node (i.e. \\(i=1\\)), the central difference discretization of 1-D convection-diffusion gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{{\\rm d}U\_1}{{\\rm d}t} + u\_{1}\\frac{U\_{2} - U\_0}{2{\\scriptstyle \\Delta } x} = \\mu \\frac{U\_2 - 2 U\_1 + U\_0}{{\\scriptstyle \\Delta } x^2}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.88)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Accounting for the known value of \\(U\_0\\), this becomes,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{{\\rm d}U\_1}{{\\rm d}t} + u\_{1}\\frac{U\_{2} - U\_{inlet}}{2{\\scriptstyle \\Delta } x} = \\mu \\frac{U\_2 - 2 U\_1 + U\_{inlet}}{{\\scriptstyle \\Delta } x^2}. \\label{equ:dirichlet\_ example}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.89)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In terms of the vector notation, when a Dirichlet boundary condition is applied we usually remove that state from the vector \\(U\\). So, in the situation where \\(U\_0\\) is known, the state vector is defined as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U = \\left( U\_{1}, U\_{2}, \\, \\ldots ,\\, U\_{i-1}, U\_{i}, U\_{i+1}, \\, \\ldots , \\, U\_{N\_ x-1}, U\_{N\_ x}\\right)^ T,\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.90)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The right-hand side \\(b\\) vector then will contain the contributions from the known boundary values. For example, by re-arranging Equation ([2.89](javascript: void(0))), the first row of \\(b\\) contains,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[b\_1 = u\_{2}\\frac{U\_{inlet}}{2{\\scriptstyle \\Delta } x} + \\mu \\frac{U\_{inlet}}{{\\scriptstyle \\Delta } x^2}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.91)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since \\(U\_{inlet}\\) does not enter any of the other node's stencils, the remaining rows of \\(b\\) will be zero (unless they are altered by the other boundary).

Effect of boundary conditions on the number of degrees of freedom for the 1D Laplace equation
---------------------------------------------------------------------------------------------

The number of degrees of freedom in a set of equations is considered to be the number of unknowns. Consider the 1D Laplace equation defined on a finite domain \\(x \\in \[0, T\].\\)

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial ^2 u(x)}{\\partial x^2} = 0, \\quad u(0) = a\_1, u(T) = a\_2\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.92)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Suppose we discretize \\(x\\) into \\(N\\) unknowns \\((x\_1, \\ldots x\_ N)\\) and we use a second order central difference scheme to approximate the left side of the Laplace equation. The resulting linear equations become

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{1}{(\\Delta x)^2} \\left\[ \\begin{array}{cccccc} (\\Delta x)^2 & 0 & 0 & 0 & \\ldots & 0 \\\\ 1 & -2 & 1 & 0 & \\ldots & 0 \\\\ 0 & 1 & -2 & 1 & \\ldots & 0 \\\\ \\vdots & \\ddots & \\ddots & \\ddots & \\ddots & \\vdots \\\\ 0 & \\ldots & 0 & 1 & -2 & 1 \\\\ 0 & \\ldots & 0 & 0 & 0 & (\\Delta x)^2 \\end{array} \\right\] \\left\[ \\begin{array}{c} u(x\_1) \\\\ u(x\_2) \\\\ \\vdots \\\\ u(x\_{N-1}) \\\\ u(x\_{N}) \\end{array}\\right\] = \\left\[ \\begin{array}{c} a\_1 \\\\ 0 \\\\ \\vdots \\\\ 0 \\\\ a\_2 \\end{array} \\right\]\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.93)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

It appears that this equation has \\(N\\) unknowns and \\(N\\) degrees of freedom.

However if we rewrite the first two equations specified by this system:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle u(x\_1)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle = a\_1\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.94)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle u(x\_1) - 2u(x\_2) + u(x\_3)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle = 0\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.95)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We can now remove \\(x\_1\\) from this system by converting the second equation into

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[-2 u(x\_2) + u(x\_3) = -a\_1\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.96)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We can perform the same trick for the last equation to obtain

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u(x\_{N-2}) - 2u(x\_{N-1}) = - a\_2\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.97)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Finally we obtain the system

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{1}{(\\Delta x^2)}\\left\[ \\begin{array}{cccccc} -2(\\Delta x^2) & \\Delta x^2 & 0 & \\ldots & \\ldots & 0 \\\\ 1 & -2 & 1 & 0 & \\ldots & 0 \\\\ 0 & 1 & -2 & 1 & \\ldots & 0 \\\\ \\vdots & \\ddots & \\ddots & \\ddots & \\ddots & \\vdots \\\\ 0 & \\ldots & 1 & -2 & 1 & 0 \\\\ 0 & \\ldots & \\ldots & 0 & \\Delta x^2 & -2\\Delta x^2 \\\\ \\end{array} \\right\] \\left\[ \\begin{array}{c} u(x\_2) \\\\ u(x\_3) \\\\ \\vdots \\\\ u(x\_{N-1}) \\end{array}\\right\]= \\left\[ \\begin{array}{c} -a\_1 \\\\ 0 \\\\ \\vdots \\\\ 0 \\\\ -a\_2 \\end{array} \\right\]\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.98)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This system has \\(N-2\\) degrees of freedom. Thus we see that the specification of the Dirichlet boundary conditions has _reduced_ the number of degrees of freedom of the system compared to the number of discretization points.

BackGeneral Finite Difference Approximations ContinueIntroduction to Finite Volume Methods