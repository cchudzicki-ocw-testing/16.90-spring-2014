---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.3 Order of Accuracy
parent_type: CourseSection
parent_uid: a3fbfbbd-e140-393b-aed5-af945a9316f9
title: 1.3 Order of Accuracy
uid: ff3b4491-f1d1-d23e-2d3a-939de701c5c2
---

*   {{< resource_link 58553753-c9cc-c012-f030-d87844ae8db5 "\<Definition of Multi-Step Methods" >}}
*   {{< resource_link a3fbfbbd-e140-393b-aed5-af945a9316f9 "1.3.1Errors" >}}
*   {{< resource_link 6121a3ca-d8f1-c652-7821-6a952ea8ff2c "1.3.2Local Truncation Error" >}}
*   {{< resource_link 09523d4b-aafc-8f4c-e9b7-d3d67ad30e7b "1.3.3Local Order of Accuracy" >}}
*   {{< resource_link 58553753-c9cc-c012-f030-d87844ae8db5 "1.3.4Definition of Multi-Step Methods" >}}
*   {{< resource_link ff3b4491-f1d1-d23e-2d3a-939de701c5c2 "1.3.5Example of Most Accurate Multi-Step Method" >}}
*   {{< resource_link 99ee39b7-79f4-9afb-0849-103c798f1c50 "\>Convergence" >}}

1.3.5 Example of Most Accurate Multi-Step Method
------------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.5" "#anchorMO15" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.6" "#anchorMO16" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.8" "#anchorMO18" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.15" "#anchorMO115" >}}

In this example, we will derive the most accurate multi-step method of the following form:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} + \\alpha \_1 v^ n + \\alpha \_2 v^{n-1} = {\\Delta t}\\left\[ \\beta \_1 f^ n + \\beta \_2 f^{n-1} \\right\]\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.56)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The local truncation error for this method is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tau = - \\alpha \_1 u^ n - \\alpha \_2 u^{n-1} + {\\Delta t}\\left\[ \\beta \_1 f^ n + \\beta \_2 f^{n-1} \\right\] - u^{n+1}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.57)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Substitution of \\(f^ n = u\_ t^ n\\) and \\(f^{n-1} = u\_ t^{n-1}\\) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tau = - \\alpha \_1 u^ n - \\alpha \_2 u^{n-1} + {\\Delta t}\\left\[ \\beta \_1 u\_ t^ n + \\beta \_2 u\_ t^{n-1} \\right\] - u^{n+1}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.58)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, Taylor series about \\(t=t^ n\\) are substituted for \\(u^{n-1}\\), \\(u\_ t^{n-1}\\), and \\(u^{n+1}\\) to give,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\tau\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle - \\alpha \_1 u^ n - \\alpha \_2\\left\[ u^ n - {\\Delta t}u^ n\_ t + \\frac{1}{2}{\\Delta t}^2 u^ n\_{tt} - \\frac{1}{6}{\\Delta t}^3 u^ n\_{ttt} + \\frac{1}{24}{\\Delta t}^4 u^ n\_{tttt} + O({\\Delta t}^5) \\right\]\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.59)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle + {\\Delta t}\\beta \_1 u\_ t^ n + {\\Delta t}\\beta \_2 \\left\[ u^ n\_ t - {\\Delta t}u^ n\_{tt} + \\frac{1}{2}{\\Delta t}^2 u^ n\_{ttt} - \\frac{1}{6}{\\Delta t}^3 u^ n\_{tttt} + O({\\Delta t}^4) \\right\]\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.60)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle - \\left\[ u^ n + {\\Delta t}u^ n\_ t + \\frac{1}{2}{\\Delta t}^2 u^ n\_{tt} + \\frac{1}{6}{\\Delta t}^3 u^ n\_{ttt} + \\frac{1}{24}{\\Delta t}^4 u^ n\_{tttt} + O({\\Delta t}^5) \\right\]\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.61)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Next, collect the terms in powers of \\({\\Delta t}\\), which gives the following coefficients:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\begin{array}{r@{:\\: \\: }cccccccccc} u^ n & - & \\alpha \_1 & - & \\alpha \_2 & & & & & - & 1 \\\\\[0.1in\] {\\Delta t}u\_ t^ n & & & & \\alpha \_2 & + & \\beta \_1 & + & \\beta \_2 & - & 1 \\\\\[0.1in\] {\\Delta t}^2 u\_{tt}^ n & & & - & \\frac{\\alpha \_2}{2} & & & - & \\beta \_2 & - & \\frac{1}{2} \\\\\[0.1in\] {\\Delta t}^3 u\_{ttt}^ n & & & & \\frac{\\alpha \_2}{6} & & & + & \\frac{\\beta \_2}{2} & - & \\frac{1}{6} \\\\\[0.1in\] {\\Delta t}^4 u\_{tttt}^ n & & & -& \\frac{\\alpha \_2}{24} & & & - & \\frac{\\beta \_2}{6} & - & \\frac{1}{24} \\end{array}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.62)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

To find the most accurate multi-step method of the given form, we solve for the values of \\(\\alpha \_1\\), \\(\\alpha \_2\\), \\(\\beta \_1\\), and \\(\\beta \_2\\) that result in the coefficients of the first four terms being identically zero.

**Exercise 1** Use MATLAB{{< sup "®" >}}'s backslash command in the form

 x= A\\b 

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; \\(\[4,-5,2,4\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(\[1,0,-1,5\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(\[4,2,-4,1\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; \\(\[4,-5,4,2\]\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; p=1 &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; p=2 &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; p=3 &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; p=4 &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: Note, with these values, the leading error term is \\(-\\frac{1}{6}{\\Delta t}^4 u\_{tttt}^ n\\). Thus, the scheme is third order accurate (\\(p=3\\)).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackDefinition of Multi-Step Methods ContinueConvergence