---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.9 Introduction to Finite Elements
parent_type: CourseSection
parent_uid: 876be530-ac05-3384-5428-281b2b3c5b68
title: 2.9 Introduction to Finite Elements
uid: c369789e-d0c6-3741-858a-5dcba10708e4
---

*   {{< resource_link 2f262139-b40f-5261-66c9-51230f32cd54 "\<Weak Form of the Weighted Residual" >}}
*   {{< resource_link 876be530-ac05-3384-5428-281b2b3c5b68 "2.9.1Motivation" >}}
*   {{< resource_link cc8eecdb-7e89-e1db-ce16-2f90e5ff68fb "2.9.21-D Finite Element Mesh and Notation" >}}
*   {{< resource_link 03bb574d-085a-6995-0b35-3c2a70257228 "2.9.31-D Linear Elements and the Nodal Basis" >}}
*   {{< resource_link 2f262139-b40f-5261-66c9-51230f32cd54 "2.9.4Weak Form of the Weighted Residual" >}}
*   {{< resource_link c369789e-d0c6-3741-858a-5dcba10708e4 "2.9.5Calculation of the Finite Element Weighted Residual" >}}
*   {{< resource_link e47fb6af-9d83-9e3b-073e-b5053c6c2226 "2.9.6Calculation of the Stiffness Matrix" >}}
*   {{< resource_link e47fb6af-9d83-9e3b-073e-b5053c6c2226 "\>Calculation of the Stiffness Matrix" >}}

2.9.5 Calculation of the Finite Element Weighted Residual
---------------------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.12" "#anchorMO212" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.14" "#anchorMO214" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.15" "#anchorMO215" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.16" "#anchorMO216" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.17" "#anchorMO217" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.20" "#anchorMO220" >}}

The implementation of the finite element method requires finding the weak form of the residual for each weight function \\(\\phi \_ j(x)\\). For the diffusion problem the \\(j^{th}\\) weighted residual is

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[r(\\tilde{T}, \\phi \_ j) \\equiv \\left\[\\phi \_ j\\, k \\tilde{T}\_ x\\right\]^{L/2}\_{-L/2} - \\int \_{-L/2}^{L/2} {\\phi \_ j}\_ x\\, k \\tilde{T}\_ x\\, dx + \\int \_{-L/2}^{L/2} \\phi \_ j f\\, dx. \\label{equ:Rj\_ dif1d}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.211)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We will consider the evaluation of the term \\(\\int \_{-L/2}^{L/2} \\phi \_{j\_ x}k\\tilde{T}\_{x} dx\\) below. The approximation of \\(\\int \_{-L/2}^{L/2} \\phi \_{j\_ x} f dx\\) will be discussed in Section {{< resource_link 62673265-55df-f200-dae2-644697a179db "2.10.1" >}}; for now, we assume that this integral can be calculated analytically. For now, consider the term \\(\\int \_{-L/2}^{L/2} {\\phi \_ j}\_ x\\, k \\tilde{T}\_ x\\, dx\\). While it is a global integral (i.e., an integral over the entire domain), in reality \\(\\phi \_ j(x)\\) is non-zero only over the two elements that include node \\(j\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\Rightarrow \\int \_{-L/2}^{L/2} {\\phi \_ j}\_ x\\, k \\tilde{T}\_ x\\, dx = \\int \_{x\_{j-1}}^{x\_{j+1}} {\\phi \_ j}\_ x\\, k \\tilde{T}\_ x\\, dx.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.212)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The derivative of basis function \\(j\\) is

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[{\\phi \_ j}\_ x(x) = \\left\\{ \\begin{array}{cl} 0, & \\mbox{for } x \< x\_{j-1}, \\\\\[0.1in\] \\frac{1}{\\Delta x\_{j-1}}, & \\mbox{for } x\_{j-1} \< x \< x\_{j},\\\\\[0.1in\] \\frac{-1}{\\Delta x\_{j}}, & \\mbox{for } x\_{j} \< x \< x\_{j+1},\\\\\[0.1in\] 0, & \\mbox{for } x > x\_{j+1}. \\end{array}\\right. \\label{equ:phi\_ x\_ linear}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.213)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int \_{x\_{j-1}}^{x\_{j+1}} {\\phi \_ j}\_ x\\, k \\tilde{T}\_ x\\, dx = \\frac{1}{\\Delta x\_{j-1}} \\int \_{x\_{j-1}}^{x\_{j }} k \\tilde{T}\_ x\\, dx - \\frac{1}{\\Delta x\_{j }} \\int \_{x\_{j }}^{x\_{j+1}} k \\tilde{T}\_ x\\, dx.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.214)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Next, take the derivative of \\(\\tilde{T}\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tilde{T}\_ x(x) = \\sum \_{i=1}^{N+1} a\_ i {\\phi \_ i}\_ x(x).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.215)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

For the integral in element \\(j-1\\), the only non-zero contributions to \\(\\tilde{T}\_ x\\) are from \\(\\phi \_{j-1}\\) and \\(\\phi \_{j}\\), specifically,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mbox{In element }j-1: \\qquad \\tilde{T}\_ x = a\_{j-1}{\\phi \_{j-1}}\_ x + a\_{j}{\\phi \_{i}}\_ x = \\frac{a\_ j - a\_{j-1}}{\\Delta x\_{j-1}}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.216)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Similarly,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mbox{In element }j: \\qquad \\tilde{T}\_ x = a\_{j}{\\phi \_{j}}\_ x + a\_{j+1}{\\phi \_{j+1}}\_ x = \\frac{a\_{j+1}-a\_ j}{\\Delta x\_{j}}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.217)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Substituting these expressions for the derivatives into the integral gives

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int \_{x\_{j-1}}^{x\_{j+1}} {\\phi \_ j}\_ x\\, k \\tilde{T}\_ x\\, dx = \\frac{a\_{j}-a\_{j-1}}{(\\Delta x\_{j-1})^2} \\int \_{x\_{j-1}}^{x\_{j }} k \\, dx - \\frac{a\_{j+1}-a\_{j}}{(\\Delta x\_{j })^2} \\int \_{x\_{j }}^{x\_{j+1}} k \\, dx.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.218)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

At this point, we must integrate \\(k(x)\\) in each element. Efficient numerical methods to approximate this integral are discussed in Section {{< resource_link 62673265-55df-f200-dae2-644697a179db "2.10.1" >}}. For the situation in which \\(k\\) is constant throughout the domain the integral reduces to the following expression.

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mbox{For }k = \\mbox{constant}: \\qquad \\int \_{x\_{j-1}}^{x\_{j+1}} {\\phi \_ j}\_ x\\, k \\tilde{T}\_ x\\, dx = k\\frac{a\_{j}-a\_{j-1}}{\\Delta x\_{j-1}}- k\\frac{a\_{j+1}-a\_{j}}{\\Delta x\_{j }}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.219)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Exercise
--------

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\(k\\frac{-a\_{j-1} - a\_{j+1}}{\\Delta x}\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} \\(k\\frac{-a\_{j-1} + 2a\_ j - a\_{j+1}}{\\Delta x}\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(k\\frac{-a\_{j-1} - a\_{j+1}}{2\\Delta x}\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(k\\frac{ a\_{j-1} + 2a\_ j + a\_{j+1}}{\\Delta x}\\){{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: Setting \\(\\Delta x\_{j-1} = \\Delta x\_{j+1} = \\Delta x\\), we get the same approximation for the second derivative that we saw in the section of finite differences. Is that a coincidence?{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackWeak Form of the Weighted Residual ContinueCalculation of the Stiffness Matrix