---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 3.2 Review of Probability and Statistics
parent_type: CourseSection
parent_uid: 972a23bc-2208-f9b1-2895-30de24175e7d
title: 3.2 Review of Probability and Statistics
uid: 0c7b4a5a-66d4-c9d6-0849-150ad651b9c6
---

*   {{% resource_link a3d2bfd5-90c2-ddaf-a1c4-73639ba4be5e "\<Outcomes and Events" %}}
*   {{% resource_link 972a23bc-2208-f9b1-2895-30de24175e7d "3.2.1Random Variables" %}}
*   {{% resource_link a3d2bfd5-90c2-ddaf-a1c4-73639ba4be5e "3.2.2Outcomes and Events" %}}
*   {{% resource_link 0c7b4a5a-66d4-c9d6-0849-150ad651b9c6 "3.2.3Distributions" %}}
*   {{% resource_link f11bfbbc-299e-7603-ff39-0e8071fc595e "3.2.4Expectations" %}}
*   {{% resource_link 48e310af-9f94-1a31-5e65-7482fc62956d "3.2.5The Central Limit Theorem" %}}
*   {{% resource_link f11bfbbc-299e-7603-ff39-0e8071fc595e "\>Expectations" %}}

3.2.3 Distributions
-------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.3" "#anchorMO33" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.4" "#anchorMO34" %}}

In the first unit, we were introduced to the concept of a random variable, where we distinguished it from a deterministic variable. The first step in an engineering analysis is to identify the random variables present in the system. Then, we need to characterize these random variables, i.e. specify appropriate models of their uncertain behavior.

Random variables can be characterized by assigning them with a probability distribution function. A discrete random variable is characterized by its probability mass function, which assigns probabilities to the event that the random variable takes certain values. A continuous random variable is characterized by its probability density function, which assigns probabilities to the event that the random variable lies in a certain interval. We first discuss the probability mass functions, and then move on the probability density functions.

Probability Mass Functions
--------------------------

Consider a discrete random variable \\(X\\), and the event \\(A\\) that \\(X\\) is equal to a specific value \\(x\\). The probability of \\(A\\) can be written as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[P\\{ A\\} =P\\{ X=x\\} =p\_ X(x)\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.3)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(p\_ X(x)\\) is called the probability mass function of \\(X\\). Note that since \\(p\_ X(x)\\) is a probability value, it is always less than one, and it is zero at all those points which the random variable \\(X\\) will never be equal to.

**Example 3:** Consider the rotor blades in example 1 of unit 1. Suppose the total number of rotor blades was 4. The random variable \\(N\_ R\\) is a discrete random variable, which can take 5 different values. A possible probability mass funtion for \\(N\_ R\\) is as follows,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[p\_{N\_ R}(x) = \\left\\{ \\begin{array}{ll} 0.6 & \\mbox{for } x = 0, \\\\\[0.1in\] 0.2 & \\mbox{for } x = 1, \\\\\[0.1in\] 0.1 & \\mbox{for } x = 2, \\\\\[0.1in\] 0.05 & \\mbox{for } x = 3, \\\\\[0.1in\] 0.05 & \\mbox{for } x = 4, \\\\\[0.1in\] 0 & \\mbox{for } x \\neq \\{ 0,1,2,3,4\\} \\end{array}\\right.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.4)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note that since the \\(p\_{N\_ R}(x)\\) are probability values, they sum to 1 over their domain \\(x\\).

Probability Density Functions
-----------------------------

A probability density function (PDF) is used to describe the probability of a continuous random variable being in some range. In particular, consider a random variable \\(X\\), and the event \\(A\\) that it lies between the numbers \\(a\\) and \\(b\\), i.e., \\(a \\leq X \\leq b\\). The probability of the event \\(A\\) can be written as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[P\\{ A\\} = P\\{ a \\leq X \\leq b\\} = \\int \\limits \_{a}^{b} f\_ X(x) dx,\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.5)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(f\_ X(x)\\) is called the probability density of \\(X\\). Note that unlike the probability mass function, the probability density function \\(f\_ X(x)\\), by itself, does not give the probability of an event occuring. Indeed, \\(f\_ X(x)\\) can be more than one for a given value of \\(x\\), however it can never be less than zero for any \\(x\\).

A common (and probably the simplest) distribution is the uniform distribution. In this case, the probability density is constant within some range and zero outside of this range,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[f\_ X(x) = \\left\\{ \\begin{array}{ll} \\frac{1}{b-a} & \\mbox{for } a \\leq x \\leq b, \\\\\[0.1in\] 0, & \\mbox{otherwise}. \\end{array}\\right.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.6)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We would say that the random variable \\(X\\) is uniformly distributed, and denote it as \\(X \\sim U(a,b)\\). Other distribution types are described later in the unit.

Cumulative Density Functions
----------------------------

The cumulative distribution function (CDF) of a random variable \\(X\\) is defined as the probability of the event that \\(X \\leq x\\). Specifically,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[F(x) \\equiv P\\{ X \\leq x\\}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.7)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The CDF and PDF of \\(X\\) are related as follows,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[F(a) = \\int ^{a}\_{-\\infty } f\_ X(x)\\, dx\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.8)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, we can show,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[F(b) - F(a) = \\int ^{b}\_{a} f\_ X(x)\\, dx.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.9)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Furthermore, this implies that

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[f\_ X = \\frac{dF}{dx}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.10)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Some Common Types of Distributions
----------------------------------

The normal (or Gaussian) distribution is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[f\_ X(x) = \\frac{1}{\\sigma \_ x\\sqrt {2\\pi }}e^{-(x-\\mu \_ x)^2/2\\sigma \_ x^2}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.11)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We will use the common notation \\(X \\sim \\mathcal{N}(\\mu ,\\sigma ^2)\\) to indicate that \\(X\\) is a normally-distributed random variable with mean \\(\\mu\\) and variance \\(\\sigma ^2\\).

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} 0.2{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} 0.1{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} 0.05{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} None of the above{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

\\(P\\{ B\\}\\) = \\(P\\{ NR > 2\\}\\) = \\(P\\{ N\_ R = 3 \\text { or } N\_ R = 4\\}\\) = \\(p\_{N\_ R}(3) + p\_{N\_ R}(4)\\) = 0.05 + 0.05 = 0.1{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\(\\int \_{\\frac{a+b}{2}}^{\\frac{a+b}{2}} f\_ X(x) \\, dx\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(f\_ X(\\frac{a+b}{2})\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} 0{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} Both a and c{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

For a continuous random variable, the probability of the random variable taking any single value is 0, only events where the random variable lies in an interval have non-zero probability. Another way to see this is that

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[P\\{ \\frac{a+b}{2} \\leq X \\leq \\frac{a+b}{2}\\} = \\int \_{\\frac{a+b}{2}}^{\\frac{a+b}{2}} f\_ X(x) \\, dx = 0\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.12)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

by the definition of a definite integral.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

{{< quiz_multiple_choice questionId="Q3_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\(\\int \_{a}^{\\infty } f\_ X(x) \\, dx\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\int \_{a}^{b} f\_ X(x) \\, dx\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\int \_{-\\infty }^{\\infty } f\_ X(x) \\, dx\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} All of the above{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

The distribution of \\(X\\), \\(f\_ X(x)\\) is non-zero in the interval \\(\\{ a \\leq X \\leq b \\}\\), and 0 everywhere else. Now by definition \\(F(b)=\\int \_{-\\infty }^{b} f\_ X(x) \\, dx\\). This is equal to all the three integrals above because \\(f\_ X(x)\\) is zero outside the interval \\(\\{ a \\leq X \\leq b\\}\\).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackOutcomes and Events ContinueExpectations