---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 3.4 Error Estimates for the Monte Carlo Method
parent_type: CourseSection
parent_uid: 74bb46fc-55cb-5dc9-1f9b-7be6791726ec
title: 3.4 Error Estimates for the Monte Carlo Method
uid: ed041125-462b-3411-0831-40b32f255066
---

*   {{% resource_link 74bb46fc-55cb-5dc9-1f9b-7be6791726ec "\<Error Estimates for the Monte Carlo Method" %}}
*   {{% resource_link 74bb46fc-55cb-5dc9-1f9b-7be6791726ec "3.4.1The Error in Estimating the Mean" %}}
*   {{% resource_link ed041125-462b-3411-0831-40b32f255066 "3.4.2The Error in Estimating Probabilities" %}}
*   {{% resource_link 9fcaf3a2-fde9-2040-23cd-8a8ace84e37f "3.4.3The Error in Estimating the Variance" %}}
*   {{% resource_link 22e0637c-8322-5bd8-a9d4-e80723fbc928 "3.4.4Bootstrapping" %}}
*   {{% resource_link 9fcaf3a2-fde9-2040-23cd-8a8ace84e37f "\>The Error in Estimating the Variance" %}}

3.4.2 The Error In Estimating Probabilities
-------------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.8" "#anchorMO38" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.11" "#anchorMO311" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.12" "#anchorMO312" %}}

Often, Monte Carlo simulations are used to estimate the probability of an event occurring. For example, in the turbine blade example, we might be interested in the probability that the hot metal temperature exceeds a critical value. Generically, suppose that the event of interest is \\(A\\). Then, an estimate of \\(P\\{ A\\}\\) is the fraction of times the event \\(A\\) occurs out of the total number of trials,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\hat{p}(A) = \\frac{N\_ A}{N}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.45)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(N\_ A\\) is the number of times \\(A\\) occurred in the Monte Carlo simulation of sample size \\(N\\).

\\(\\hat{p}(A)\\) is an unbiased estimate of \\(P\\{ A\\}\\). To see this, define a function \\(I(A\_ i)\\) which equals 1 if event \\(A\\) occurred on the \\(i\\)-th trial, and equals zero if \\(A\\) did not occur. For example, if the event \\(A\\) is defined as \\(y > y\_{limit}\\), \\(I(A\_ i)\\) would be defined as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[I(A\_ i) = I(y\_ i > y\_{limit}) = \\left\\{ \\begin{array}{cc} 1 & \\mbox{if } y\_ i > y\_{limit}, \\\\ 0 & \\mbox{if } y\_ i \\leq y\_{limit}. \\end{array}\\right.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.46)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Using this definition, the number of times that \\(A\\) occurred can be written as

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[N\_ A = \\sum \_{i=1}^ N I(A\_ i).\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.47)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Finding the expectation of \\(N\_ A\\) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[E\[N\_ A\] = E\[\\sum \_{i=1}^ N I(A\_ i)\] = \\sum \_{i=1}^ N E\[I(A\_ i)\].\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.48)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since we assume that the Monte Carlo trials are drawn at random and independently from each other, then \\(E\[I(A\_ i)\] = P\\{ A\\}\\). Thus,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[E\[N\_ A\] = N P\\{ A\\}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.49)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Finally, using this result we see that

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[E\[\\hat{p}(A)\] = \\frac{E\[N\_ A\]}{N} = P\\{ A\\} .\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.50)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We can also use the central limit theorem to show that \\(\\hat{p}(A)\\) is normally distributed for large \\(N\\) with mean \\(P\\{ A\\}\\) and standard error,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\sigma \_{\\hat{p}} = \\sqrt {\\frac{P\\{ A\\} (1-P\\{ A\\} )}{N}}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.51)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; \\(\\sqrt {\\frac{P\\{ A\\} (1-P\\{ A\\} )}{2N}}\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; \\(\\sqrt {\\frac{P\\{ B\\} (1-P\\{ B\\} )}{N}}\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(\\sqrt {\\frac{P\\{ B\\} (1-P\\{ B\\} )}{2N}}\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

For estimating the standard error associated with computing \\(P\\{ B\\}\\), the exposition above remains the same, except \\(P\\{ A\\}\\) is replaced by \\(P\\{ B\\}\\).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackError Estimates for the Monte Carlo Method ContinueThe Error in Estimating the Variance