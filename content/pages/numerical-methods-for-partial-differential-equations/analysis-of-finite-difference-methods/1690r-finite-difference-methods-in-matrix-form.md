---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.4 Analysis of Finite Difference Methods
parent_type: CourseSection
parent_uid: c9ae23f7-07d4-0d5c-c85b-b19ebf476df0
title: 2.4 Analysis of Finite Difference Methods
uid: 404d1192-4d4a-07bb-c158-0c3605807e8e
---

*   {{< resource_link ba32080c-16da-eb92-bc6f-615dc10a7e31 "\<Truncation Error for a PDE" >}}
*   {{< resource_link c9ae23f7-07d4-0d5c-c85b-b19ebf476df0 "2.4.1Local Truncation Error for a Derivative Approximation" >}}
*   {{< resource_link 9064faf9-febc-8ca2-e94e-1b057fcc34be "2.4.2Truncation Error of Central Difference Approximation" >}}
*   {{< resource_link ba32080c-16da-eb92-bc6f-615dc10a7e31 "2.4.3Truncation Error for a PDE" >}}
*   {{< resource_link 404d1192-4d4a-07bb-c158-0c3605807e8e "2.4.4Finite Difference Methods in Matrix Form" >}}
*   {{< resource_link 7e5587c8-fac2-cbac-56c4-7e6cdfc52004 "2.4.5General Finite Difference Approximations" >}}
*   {{< resource_link 7d8e6a54-9392-cde6-ff4d-914e606da194 "2.4.6Boundary Conditions for Finite Differences" >}}
*   {{< resource_link 7e5587c8-fac2-cbac-56c4-7e6cdfc52004 "\>General Finite Difference Approximations" >}}

2.4.4 Finite Difference Methods in Matrix Form
----------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.3" "#anchorMO23" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.8" "#anchorMO28" >}}

Consider the one-dimensional convection-diffusion equation,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\dfrac {\\partial U}{\\partial t} + u \\dfrac {\\partial U}{\\partial x} -\\mu \\dfrac {\\partial ^2 U}{\\partial x^2}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.73)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Approximating the spatial derivative using the central difference operators gives the following approximation at node \\(i\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\dfrac {d U\_ i}{d t} + u\_ i \\delta \_{2x} U\_ i - \\mu \\delta \_ x^2 U\_ i\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.74)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Assembling all of the nodal states into a single vector

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle U = \\left( U\_0,\\, U\_1,\\, \\ldots ,\\, U\_{i-1},\\, U\_ i,\\, U\_{i+1},\\, \\ldots ,\\, U\_{N\_ x-1},\\, U\_{N\_ x}\\right)^ T,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.75)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

gives a system of coupled ODEs of the form:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\dfrac {d U}{d t}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle A U + b \\label{equ:linSys}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.76)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(b\\) will contain the boundary condition related data. The matrix \\(A\\) has the form:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle A\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[\\begin{array}{cccc} A\_{0,0} & A\_{0,1} & \\ldots & A\_{0,N\_ x} \\\\ A\_{1,0} & A\_{1,1} & \\ldots & A\_{1,N\_ x} \\\\ \\vdots & \\vdots & \\ddots & \\vdots \\\\ A\_{N\_ x,0} & A\_{N\_ x,1} & \\ldots & A\_{N\_ x,N\_ x} \\end{array} \\right\].\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.77)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note that row \\(i\\) of this matrix contains the coefficients of the nodal values for the ODE governing node \\(i\\). Except for rows requiring boundary condition data, the values of \\(A\_{i,j}\\) are related to the coefficients \\(\\alpha \_ j\\) of the finite difference approximation. Specifically, for our central difference approximation

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle A\_{i,i-1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{u\_ i}{2 \\Delta x} + \\frac{\\mu }{\\Delta x^2},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.78)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle A\_{i,i}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle - 2\\frac{\\mu }{\\Delta x^2},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.79)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle A\_{i,i+1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -\\frac{u\_ i}{2 \\Delta x} + \\frac{\\mu }{\\Delta x^2},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.80)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

and all other entries of row \\(i\\) are zero. In general, the number of non-zero entries of row \\(i\\) will correspond to the size of the stencil of the finite difference approximations used. We refer to Equation [2.76](javascript: void(0)) as being semi-discrete, since we have discretized the PDE in space but not in time. To make this a fully discrete approximation, we can apply any of the ODE integration methods that we discussed previously.

**Implementation Notes** When explicit methods are used to represent a FD method, then the \\(A\\) matrix does not need to be directly formed. Implementing a finite difference approximation at each node will suffice as we will only be interested in _matrix-vector multiplication_, i.e. we only need to _apply_ \\(A\\).

On the other hand, implicit methods require the solution of a linear system. The solutions methods often require the representation of \\(A\\) as a matrix, and thus it must be constructed.

BackTruncation Error for a PDE ContinueGeneral Finite Difference Approximations