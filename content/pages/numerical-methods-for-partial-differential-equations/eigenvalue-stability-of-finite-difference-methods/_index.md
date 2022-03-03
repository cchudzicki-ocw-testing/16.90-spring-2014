---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 2: Numerical Methods for Partial Differential Equations'
parent_type: CourseSection
parent_uid: 125c58ac-6a34-5a7c-bba8-de2d3160cb8b
title: 2.7 Eigenvalue Stability of Finite Difference Methods
uid: 935b6a61-8d7d-2772-6ca1-df78ee864834
---

*   {{< resource_link cf738358-ae33-664a-5d71-baadd24f92cb "\<The CFL Condition" >}}
*   {{< resource_link 935b6a61-8d7d-2772-6ca1-df78ee864834 "2.7.1Fourier Analysis of PDEs" >}}
*   {{< resource_link 3e2eea01-ee64-f3f7-264f-4d9e57b3b622 "2.7.2Matrix Stability for Finite Difference Methods" >}}
*   {{< resource_link c4a73127-b3ff-feee-5cd9-2e3e6319d356 "2.7.3Circulant Matrices" >}}
*   {{< resource_link cb633bb1-3925-0ab5-7f90-8bb74bb848bb "2.7.4Stability Exercises" >}}
*   {{< resource_link 3e2eea01-ee64-f3f7-264f-4d9e57b3b622 "\>Matrix Stability for Finite Difference Methods" >}}

2.7.1 Fourier Analysis of PDEs
------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.2" "#anchorMO22" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.11" "#anchorMO211" >}}

We will develop Fourier analysis in one dimension. The basic ideas extend easily to multiple dimensions. We will consider the convection-diffusion equation,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial U}{\\partial t} + u\\frac{\\partial U}{\\partial x} = \\mu \\frac{\\partial ^2 U}{\\partial x^2}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.124)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We will assume that the velocity, \\(u\\), and the viscosity, \\(\\mu\\) are constant.

The solution is assumed to be periodic over a length \\(L\\). Thus,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U(x+mL,t) = U(x,t)\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.125)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(m\\) is any integer.

A Fourier series with periodicity over length \\(L\\) is given by,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U(x,t) = \\sum \_{m=-\\infty }^{+\\infty } \\hat{U}\_ m(t)e^{i k\_ m x} \\qquad \\mbox{where} \\qquad k\_ m = \\frac{2\\pi m}{L}. \\label{equ:Fourier}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.126)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

\\(k\_ m\\) is generally called the wavenumber, though \\(m\\) is the number of waves occurring over the length \\(L\\). We note that \\(\\hat{U}\_ m(t)\\) is the amplitude of the \\(m\\)-th wavenumber and it is generally complex (since we have used complex exponentials). Substituting the Fourier series into the convection-diffusion equation gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial }{\\partial t}\\left\[\\sum \_{m=-\\infty }^{+\\infty } \\hat{U}\_ m(t)e^{i k\_ m x}\\right\] + u \\frac{\\partial }{\\partial x}\\left\[\\sum \_{m=-\\infty }^{+\\infty } \\hat{U}\_ m(t)e^{i k\_ m x}\\right\] = \\mu \\frac{\\partial ^2}{\\partial x^2}\\left\[\\sum \_{m=-\\infty }^{+\\infty } \\hat{U}\_ m(t)e^{i k\_ m x}\\right\].\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.127)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}
{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\sum \_{m=-\\infty }^{+\\infty } \\frac{{\\rm d}\\hat{U}\_ m}{{\\rm d}t} e^{i k\_ m x} + u \\sum \_{m=-\\infty }^{+\\infty } i k\_ m \\hat{U}\_ m e^{i k\_ m x} = \\mu \\sum \_{m=-\\infty }^{+\\infty } (i k\_ m)^2 \\hat{U}\_ m e^{i k\_ m x}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.128)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Noting that \\(i^2 = -1\\) and collecting terms gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\sum \_{m=-\\infty }^{+\\infty } \\left\[\\frac{{\\rm d}\\hat{U}\_ m}{{\\rm d}t} + \\left(i u k\_ m + \\mu k\_ m^2\\right) \\hat{U}\_ m\\right\] e^{i k\_ m x} = 0. \\label{equ:Fourier\_ preorth}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.129)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The next step is to utilize the orthogonality of the different Fourier modes over the length \\(L\\), specifically,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int \_0^ L e^{-i k\_ n x} e^{i k\_ m x} dx = \\left\\{ \\begin{array}{cc} 0 & \\mbox{if } m \\neq n \\\\ L & \\mbox{if } m = n \\end{array}\\right. \\label{equ:Fourier\_ orth}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.130)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

By multiplying Equation ([2.129](javascript: void(0))) by \\(e^{-i k\_ n x}\\) and integrating from \\(0\\) to \\(L\\), the orthogonality condition gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{{\\rm d}\\hat{U}\_ n}{{\\rm d}t} + \\left(i u k\_ n + \\mu k\_ n^2\\right) \\hat{U}\_ n = 0, \\qquad \\mbox{for any integer value of } n. \\label{equ:Fourier\_ condif1d}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.131)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the evolution of the amplitude for an individual wavenumber is independent of the other wavenumbers. The solution to Equation ([2.131](javascript: void(0))),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\hat{U}\_ n(t) = \\hat{U}\_ n(0) e^{-i u k\_ n t} e^{-\\mu k\_ n^2 t}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.132)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The convection term, which results in the complex time dependent behavior, \\(e^{-i u k\_ n t}\\), only oscillates and does not change the magnitude of \\(\\hat{U}\_ n\\). The diffusion term causes the magnitude to decrease as long as \\(\\mu > 0\\). But, if the diffusion coefficient were negative, then the magnitude would increase unbounded with time. Thus, in the case of the convection-diffusion PDE, as long as \\(\\mu \\geq 0\\), this solution is stable.

Exercise
--------

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; 10 times slower &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; The damping rates are equal &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; 1000 times slower &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; 100 times slower &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: The \\(L\_1\\) mode has a damping rate \\(\\mu k\_ m^2 = \\mu (2\\pi /L)^2\\) the \\(L/10\\) mode has a damping rate of \\(\\mu k\_ m^2 = \\mu (20\\pi /L)^2\\){{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackThe CFL Condition ContinueMatrix Stability for Finite Difference Methods