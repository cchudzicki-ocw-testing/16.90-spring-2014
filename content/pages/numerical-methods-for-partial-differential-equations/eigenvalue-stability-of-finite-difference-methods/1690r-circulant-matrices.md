---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.7 Eigenvalue Stability of Finite Difference Methods
parent_type: CourseSection
parent_uid: 935b6a61-8d7d-2772-6ca1-df78ee864834
title: 2.7 Eigenvalue Stability of Finite Difference Methods
uid: c4a73127-b3ff-feee-5cd9-2e3e6319d356
---

*   {{< resource_link 3e2eea01-ee64-f3f7-264f-4d9e57b3b622 "\<Matrix Stability for Finite Difference Methods" >}}
*   {{< resource_link 935b6a61-8d7d-2772-6ca1-df78ee864834 "2.7.1Fourier Analysis of PDEs" >}}
*   {{< resource_link 3e2eea01-ee64-f3f7-264f-4d9e57b3b622 "2.7.2Matrix Stability for Finite Difference Methods" >}}
*   {{< resource_link c4a73127-b3ff-feee-5cd9-2e3e6319d356 "2.7.3Circulant Matrices" >}}
*   {{< resource_link cb633bb1-3925-0ab5-7f90-8bb74bb848bb "2.7.4Stability Exercises" >}}
*   {{< resource_link cb633bb1-3925-0ab5-7f90-8bb74bb848bb "\>Stability Exercises" >}}

2.7.3 Circulant Matrices
------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.10" "#anchorMO210" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.11" "#anchorMO211" >}}

Though the eigenvalues of \\(A\\) typically require numerical techniques for the general problem, a special case of practical interest occurs when the matrix is ‘periodic'. That is, the column entries shift a column every row. Thus, the matrix has the form,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[A = \\left(\\begin{array}{ccccc} a\_1 & a\_2 & a\_3 & \\ldots & a\_{N } \\\\ a\_ N & a\_1 & a\_2 & \\ldots & a\_{N-1} \\\\ \\vdots & \\vdots & \\vdots & \\ddots & \\vdots \\\\ a\_2 & a\_3 & a\_4 & \\ldots & a\_1 \\end{array}\\right)\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.140)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This type of matrix is known as a circulant matrix. Circulant matrices have eigenvalues given by,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\lambda \_ n = \\sum \_{j=1}^{N} a\_ j e^{i\\, 2\\pi (j-1) \\frac{n}{N}} \\qquad \\mbox{for} \\quad n = 0, 1, \\ldots , N-1 \\label{equ:circulant\_ eig}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.141)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

As we saw in Section {{< resource_link 3e2eea01-ee64-f3f7-264f-4d9e57b3b622 "2.7.2" >}}, when periodic boundary conditions are assumed, the central space discretization of one-dimensional convection gives purely imaginary eigenvalues, and when scaled by a timestep for which the CFL number is one, the eigenvalues stretch along the axis until \\(\\pm i\\). Since for a convection problem with constant velocity and periodic boundary conditions gives a circulant matrix, we can use Equation ([2.141](javascript: void(0))) to determine the eigenvalues analytically. We begin by finding the coefficients, \\(a\_ j\\). For a central space discretization, we find,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[a\_2 = -\\frac{u}{2{\\scriptstyle \\Delta } x}, \\quad a\_ N = \\frac{u}{2{\\scriptstyle \\Delta } x}, \\mbox{ and for all other } j, \\quad a\_ j = 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.142)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, substituting these \\(a\_ j\\) into Equation ([2.141](javascript: void(0))) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\lambda \_ n\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -\\frac{u}{2{\\scriptstyle \\Delta } x} e^{i\\, 2\\pi \\frac{n}{N}} + \\frac{u}{2{\\scriptstyle \\Delta } x} e^{i\\, 2\\pi (N-1) \\frac{n}{N}},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.143)
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
\\(\\displaystyle -\\frac{u}{2{\\scriptstyle \\Delta } x} e^{i\\, 2\\pi \\frac{n}{N}} + \\frac{u}{2{\\scriptstyle \\Delta } x} e^{i\\, 2\\pi n} e^{-i\\, 2\\pi \\frac{n}{N}}.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.144)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since \\(e^{i\\, 2\\pi n} = 1\\) (because \\(n\\) is an integer), then,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\lambda \_ n\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -\\frac{u}{2{\\scriptstyle \\Delta } x} e^{i\\, 2\\pi \\frac{n}{N}} + \\frac{u}{2{\\scriptstyle \\Delta } x} e^{-i\\, 2\\pi \\frac{n}{N}},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.145)
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
\\(\\displaystyle -\\frac{u}{2{\\scriptstyle \\Delta } x}\\left(e^{i\\, 2\\pi \\frac{n}{N}} - e^{-i\\, 2\\pi \\frac{n}{N}}\\right),\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.146)
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
\\(\\displaystyle -i\\frac{u}{{\\scriptstyle \\Delta } x}\\sin \\left(2\\pi \\frac{n}{N}\\right).\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.147)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Multiplying by the timestep,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\lambda \_ n {\\Delta t}= -i\\frac{u{\\Delta t}}{{\\scriptstyle \\Delta } x}\\sin \\left(2\\pi \\frac{n}{N}\\right).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.148)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

As observed in Section {{< resource_link 3e2eea01-ee64-f3f7-264f-4d9e57b3b622 "2.7.2" >}}, the eigenvalues are purely imaginary and will extend to \\(\\pm i\\) when \\(\\mathrm{CFL} = |u|{\\Delta t}/{\\scriptstyle \\Delta } x= 1\\).

BackMatrix Stability for Finite Difference Methods ContinueStability Exercises