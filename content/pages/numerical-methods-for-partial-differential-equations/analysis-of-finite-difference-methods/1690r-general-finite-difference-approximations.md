---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.4 Analysis of Finite Difference Methods
parent_type: CourseSection
parent_uid: c9ae23f7-07d4-0d5c-c85b-b19ebf476df0
title: 2.4 Analysis of Finite Difference Methods
uid: 7e5587c8-fac2-cbac-56c4-7e6cdfc52004
---

*   {{% resource_link 404d1192-4d4a-07bb-c158-0c3605807e8e "\<Finite Difference Methods in Matrix Form" %}}
*   {{% resource_link c9ae23f7-07d4-0d5c-c85b-b19ebf476df0 "2.4.1Local Truncation Error for a Derivative Approximation" %}}
*   {{% resource_link 9064faf9-febc-8ca2-e94e-1b057fcc34be "2.4.2Truncation Error of Central Difference Approximation" %}}
*   {{% resource_link ba32080c-16da-eb92-bc6f-615dc10a7e31 "2.4.3Truncation Error for a PDE" %}}
*   {{% resource_link 404d1192-4d4a-07bb-c158-0c3605807e8e "2.4.4Finite Difference Methods in Matrix Form" %}}
*   {{% resource_link 7e5587c8-fac2-cbac-56c4-7e6cdfc52004 "2.4.5General Finite Difference Approximations" %}}
*   {{% resource_link 7d8e6a54-9392-cde6-ff4d-914e606da194 "2.4.6Boundary Conditions for Finite Differences" %}}
*   {{% resource_link 7d8e6a54-9392-cde6-ff4d-914e606da194 "\>Boundary Conditions for Finite Differences" %}}

2.4.5 General Finite Difference Approximations
----------------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.3" "#anchorMO23" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.8" "#anchorMO28" %}}

So far we have developed several finite difference approximations for the first derivative and the central difference operator for the second derivative. As we've seen before for first and second derivative approximations, finite difference approximations may be obtained from the definition of the derivative. In practice, generating a finite difference approximation starting from the definition of the derivative can be difficult to extend to a variety of situations. For example, suppose that a backwards difference was desired for \\(U\_{x\_ i}\\) using three nodes. Mathematically, we want to find coefficients \\(\\alpha \_ i\\), \\(\\alpha \_{i-1}\\), and \\(\\alpha \_{i-2}\\) of \\(U\_ i\\), \\(U\_{i-1}\\), and \\(U\_{i-2}\\) that would give an approximation to \\(U\_{x\_ i}\\), i.e.

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{1}{\\Delta x}\\left(\\alpha \_ i U\_ i + \\alpha \_{i-1} U\_{i-1} + \\alpha \_{i-2} U\_{i-2}\\right) \\approx {U\_ x}\_ i.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.81)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note, we have included a factor of \\(1/\\Delta x\\) in this backwards finite difference approximation of the first derivative since we know that the formal definition of the first derivative involves calculating the difference of \\(U(x+\\Delta x/2)\\) and \\(U(x-\\Delta x/2)\\) dividing by \\(\\Delta x\\). Doing this, the coefficients \\(\\alpha\\) will not depend on \\(\\Delta x\\). Now, we will utilize Taylor series to construct the truncation error for this approximation and then find the \\(\\alpha\\) values that achieve the highest-order of accuracy. The necessary Taylor series expansions are,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\begin{array}{rcrcrcrcrcr} U\_{i} & = & U\_{i} \\\\ U\_{i-1} & = & U\_ i & -& \\Delta x {U\_ x}\_ i & +& \\frac{1}{2} \\Delta x^2 {U\_{xx}}\_ i & -& \\frac{1}{6} \\Delta x^3 {U\_{xxx}}\_ i & +& O(\\Delta x^4) \\\\ U\_{i-2} & = & U\_ i & -& (2\\Delta x) {U\_ x}\_ i & +& \\frac{1}{2} (2\\Delta x)^2 {U\_{xx}}\_ i & -& \\frac{1}{6} (2\\Delta x)^3 {U\_{xxx}}\_ i & +& O(\\Delta x^4) \\end{array}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.82)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Substituting these Taylor series into the three-point backwards difference formula and gathering the terms that are the same order in \\(\\Delta x\\) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\begin{array}{ccrcccccrr} \\frac{1}{\\Delta x}\\left(\\alpha \_ i U\_ i + \\alpha \_{i-1} U\_{i-1} + \\alpha \_{i-2} U\_{i-2}\\right) & = & ( & \\alpha \_{i} & +& \\alpha \_{i-1} & +& \\alpha \_{i-2} & ) & \\frac{1}{\\Delta x} U\_ i \\\\ & - & ( & & & \\alpha \_{i-1} & +& 2\\alpha \_{i-2} & ) & {U\_ x}\_ i \\\\ & + & \\frac{1}{2}( & & & \\alpha \_{i-1} & +& 4\\alpha \_{i-2} & ) & \\Delta x {U\_{xx}}\_ i \\\\ & - & \\frac{1}{6}( & & & \\alpha \_{i-1} & +& 8\\alpha \_{i-2} & ) & \\Delta x^2 {U\_{xxx}}\_ i \\\\ & + & O( & \\Delta x^3 & ) \\end{array} \\label{equ:taylorsintobwd}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.83)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since we have 3 coefficients (\\(\\alpha \_ i, \\alpha \_{i-1}, \\alpha \_{i-2}\\)), we may choose these coefficients such that the terms multiplying \\(U\_{x\_ i}\\) sum to 1, while the terms multiplying \\(\\frac{1}{\\Delta x} U\_ i\\) and \\(\\Delta x U\_{xx\_ i}\\) sum to zero. Using matrix notation:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[\\begin{array}{rrr} 1 & 1 & 1 \\\\ 0 & -1 & -2 \\\\ 0 & 1 & 4 \\end{array}\\right\] \\left\[\\begin{array}{c} \\alpha \_{i} \\\\ \\alpha \_{i-1} \\\\ \\alpha \_{i-2} \\end{array}\\right\] = \\left\[\\begin{array}{c} 0 \\\\ 1 \\\\ 0 \\end{array}\\right\] \\qquad \\qquad \\text {which gives}\\qquad \\qquad \\left\[\\begin{array}{c} \\alpha \_{i} \\\\ \\alpha \_{i-1} \\\\ \\alpha \_{i-2} \\end{array}\\right\] = \\left\[\\begin{array}{r} \\tfrac {3}{2} \\\\ -2 \\\\ \\tfrac {1}{2} \\end{array}\\right\].\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.84)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus the three-point backwards difference approximation for \\(U\_{x\_ i}\\) is equal to \\((\\frac{3}{2}U\_ i - 2U\_{i-1} + \\frac{1}{2}U\_{i-2})/\\Delta x\\). The truncation error can be found by substituting the \\(\\alpha\\)'s in Equation [2.83](javascript: void(0)) to show that,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tau = \\frac{1}{\\Delta x}\\left(\\frac{3}{2}U\_ i - 2 U\_{i-1} + \\frac{1}{2}U\_{i-2}\\right) - {U\_ x}\_ i = -\\frac{1}{3}\\Delta x^2 {U\_{xxx}}\_ i + O(\\Delta x^3)\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.85)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, this approximation for \\(U\_{x\_ i}\\) is second-order accurate. This approach can be generalized to the approximation of the \\(k-th\\) derivative,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left.\\frac{\\partial ^ k U}{\\partial x^ k}\\right|\_ i\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\approx\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{1}{(\\Delta x)^ k} \\sum \_{j \\in \\mathcal{S}} \\alpha \_ j U\_{j}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.86)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\alpha \_ j\\) are the coefficients for the finite difference approximation. \\(\\mathcal{S}\\) is called the stencil, and contains the list of points used in the finite difference approximation. For example the central difference approximation, \\(\\delta \_ x^2\\), has a 3-point stencil using the nodal values \\(U\_{i-1}, U\_ i\\) and \\(U\_{i+1}\\).

Exercise
--------

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}} \\(\[1,-2,1\]\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\[\\frac{1}{2},-2,\\frac{3}{2}\]\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\[\\frac{3}{2},-2,\\frac{1}{2}\]\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\[1,-4,3\]\\){{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: We solve the system shown above with the right hand side \\(\[0,0,1\]\\) to obtain the coefficients.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackFinite Difference Methods in Matrix Form ContinueBoundary Conditions for Finite Differences