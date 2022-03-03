---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.7 Eigenvalue Stability of Finite Difference Methods
parent_type: CourseSection
parent_uid: 935b6a61-8d7d-2772-6ca1-df78ee864834
title: 2.7 Eigenvalue Stability of Finite Difference Methods
uid: cb633bb1-3925-0ab5-7f90-8bb74bb848bb
---

*   {{< resource_link c4a73127-b3ff-feee-5cd9-2e3e6319d356 "\<Circulant Matrices" >}}
*   {{< resource_link 935b6a61-8d7d-2772-6ca1-df78ee864834 "2.7.1Fourier Analysis of PDEs" >}}
*   {{< resource_link 3e2eea01-ee64-f3f7-264f-4d9e57b3b622 "2.7.2Matrix Stability for Finite Difference Methods" >}}
*   {{< resource_link c4a73127-b3ff-feee-5cd9-2e3e6319d356 "2.7.3Circulant Matrices" >}}
*   {{< resource_link cb633bb1-3925-0ab5-7f90-8bb74bb848bb "2.7.4Stability Exercises" >}}
*   {{< resource_link bda18124-71a5-87a7-513f-cb81480a1e18 "\>Method of Weighted Residuals" >}}

2.7.4 Stability Exercises
-------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.9" "#anchorMO29" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.10" "#anchorMO210" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.11" "#anchorMO211" >}}

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; All in the left half plane &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; Two in the left half plane, the rest in a circle in the right half plane &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; Two in the right half plane, the rest in a circle in the right half plane &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; "Along the imaginary axis &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

To implement a backward spatial discretization, we modify the matrix A:

for i = 2:Nx-1 A(i,i) = u/dx; A(i,i-1) = -u/dx; end{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Exercise 2
----------

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; \\(-\\frac{u}{\\Delta x} -\\frac{u}{\\Delta x}\\left\[\\cos \\left(2\\pi \\frac{n}{N}\\right) - i\\sin \\left(2\\pi \\frac{n}{N}\\right)\\right\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; \\(-\\frac{u}{\\Delta x} +\\frac{u}{\\Delta x}\\left\[\\cos \\left(2\\pi \\frac{n}{N}\\right) - i\\sin \\left(2\\pi \\frac{n}{N}\\right)\\right\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(\\frac{u}{\\Delta x} +\\frac{u}{\\Delta x}\\left\[\\cos \\left(2\\pi \\frac{n}{N}\\right) + i\\sin \\left(2\\pi \\frac{n}{N}\\right)\\right\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(-\\frac{u}{\\Delta x} +\\frac{u}{\\Delta x}\\left\[\\cos \\left(2\\pi \\frac{n}{N}\\right) + i\\sin \\left(2\\pi \\frac{n}{N}\\right)\\right\]\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: We use the formula for the eigenvalues of a circulant matrix with \\(a\_1= -u/\\Delta x\\) and \\(a\_ N = u/ \\Delta x\\).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackCirculant Matrices ContinueMethod of Weighted Residuals