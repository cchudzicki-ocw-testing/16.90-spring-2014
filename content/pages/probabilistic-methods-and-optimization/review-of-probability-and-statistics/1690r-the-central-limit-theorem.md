---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 3.2 Review of Probability and Statistics
parent_type: CourseSection
parent_uid: 972a23bc-2208-f9b1-2895-30de24175e7d
title: 3.2 Review of Probability and Statistics
uid: 48e310af-9f94-1a31-5e65-7482fc62956d
---

*   {{% resource_link f11bfbbc-299e-7603-ff39-0e8071fc595e "\<Expectations" %}}
*   {{% resource_link 972a23bc-2208-f9b1-2895-30de24175e7d "3.2.1Random Variables" %}}
*   {{% resource_link a3d2bfd5-90c2-ddaf-a1c4-73639ba4be5e "3.2.2Outcomes and Events" %}}
*   {{% resource_link 0c7b4a5a-66d4-c9d6-0849-150ad651b9c6 "3.2.3Distributions" %}}
*   {{% resource_link f11bfbbc-299e-7603-ff39-0e8071fc595e "3.2.4Expectations" %}}
*   {{% resource_link 48e310af-9f94-1a31-5e65-7482fc62956d "3.2.5The Central Limit Theorem" %}}
*   {{% resource_link 2733fa33-374f-cb88-814c-413cb75b3483 "\>Monte Carlo Methods" %}}

3.2.5 The Central Limit Theorem
-------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.7" "#anchorMO37" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.9" "#anchorMO39" %}}

In the first four units, we have introduced the concept of a random variable, the basic axioms of probability and probability distribution functions. We have seen that just like variables can be characterized by their value, random variables can be characterized by their probability distribution. We have also seen that we can have random variables that are functions of other random variables, just like deterministic variables can be functions of other deterministic variables.

Sums of Random Variables
------------------------

It is natural to ask whether there are more parallel properties that random variables and deterministic variables share. For example, we know that the sum of two deterministic variables is another deterministic variable. What can we say about the sum of two random variables? Quite obviously, the sum of two random variables \\(X\\) and \\(Y\\) is a new random variable,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[Z=Z(X,Y)=X+Y\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.17)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

When we are adding two deterministic variables, we just have to add their values. What does it mean to add two random variables ?

Since \\(Z\\) is a random variable, it is characterized by its probability distribution, and this probability distribution has to depend on the distributions of \\(X\\) and \\(Y\\). Suppose \\(X\\) and \\(Y\\) are independent, continuous random variables, and have densities \\(f\_ X\\) and \\(f\_ Y\\). Then the density \\(f\_ Z\\) is given by the convolution,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[f\_ Z(z) = \\int \\limits \_{-\\infty }^{+\\infty } f\_{X}(x)f\_{Y}(z-x) \\, dx\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.18)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, it is indeed possible to think about adding random variables, and the result of such an addition gives us the density of a new random variable via a convolution.

Examples of Sums of Two Random Variables
----------------------------------------

As a first example, suppose \\(X\_1 \\sim \\mathcal{U}(0,1)\\) and \\(X2 \\sim \\mathcal{U}(0,1)\\), then the convolution above results in a density for a triangularly distributed random variable.

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[f\_{Z}(z) = \\left\\{ \\begin{array}{ll} z & \\mbox{for } 0 \\leq z \\leq 1, \\\\\[0.1in\] 2 - z & \\mbox{for } 1 \\leq z \\leq 2, \\\\\[0.1in\] 0 & \\mbox{otherwise } \\end{array}\\right.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.19)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The sum of these two uniformly distributed random variables \\(X\_1\\) and \\(X\_2\\) is a triangularly distributed random variable. Now suppose we add another random variable \\(X3 \\sim \\mathcal{U}(0,1)\\) to this sum, we again get a new random variable, but calculating its density using the convolution is not easy.

However, there is an important exception. Suppose \\(X\_1 \\sim \\mathcal{N}(1,1)\\) and \\(X\_2 \\sim \\mathcal{N}(1,1)\\), then the convolution above results in a density for a normally distributed random variable \\(Z \\sim \\mathcal{N}(2,2)\\). So, the sum of two normally distributed random variables is again a normal random variable. The mean and variance of this sum are the sum of means and variances of the normals we added.

Further, if we average this sum we have,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{Z}{2} = \\frac{X\_1 + X\_2}{2} \\sim \\mathcal{N}(1,\\frac{1}{2})\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.20)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

If we now add \\(X\_3 \\sim \\mathcal{N}(1,1)\\), and average over all three, we again get a normally distributed random with density \\(\\mathcal{N}(1,\\frac{1}{3})\\), and so on. Adding \\(N\\) independent, normal random variables with density \\(\\mathcal{N}(1,1)\\) we obtain,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{X\_1 + X\_2 + X\_3 + .... + X\_{N-1} + X\_ N}{N} \\sim \\mathcal{N}(1, \\frac{1}{N})\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.21)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since this is true, no matter how large we make \\(N\\), we can say that it holds true as \\(N \\to \\infty\\).

The Central Limit Theorem
-------------------------

We saw above that for the particular case of independent, identically and normally distributed variables, the asymptotic average of these variables remains normally distributed. The mean of this asymptotic average is the average of means of each variable, and its variance tends to zero as \\(\\frac{1}{N}\\). Remarkably, this is property is true for the asymptotic average of any independent and identically distributed random variables, even if they are not normally distributed !

This is the basic result of the Central Limit Theorem, which tells us that if \\(X\_1\\), \\(X\_2\\), ... \\(X\_ N\\) are independent, identically distributed random variables, with \\(E(X\_1) = E(X\_2) = ... E(X\_ N) = \\mu\\) and \\(Var(X\_1) = Var(X\_2) = ... Var(X\_ N) = \\sigma ^2\\), then we have

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\sum \\limits \_{i=1}^{N} X\_ i}{N} - \\mu \\to \\mathcal{N}(0, \\frac{\\sigma ^{2}}{N})\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.22)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

as \\(N \\to \\infty\\). So instead of averaging normals, if we kept averaging the uniform random variables that we added earlier, then eventually, the resultant random variable is guaranteed to have a normal distribution ! Not only that, the mean of this normal random variable will have the mean of the uniform random variables we added, and its variance will tend to zero.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} undefined{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\mu , \\mu , \\ldots , \\mu\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(E(X\_1),E(X\_2), \\ldots , E(X\_ N)\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} 0,0,\\(\\ldots\\),0{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

\\(E(X\_1 - \\mu ) = \\int \_{-\\infty }^{+\\infty } (x - \\mu ) f\_ X(x)\\, dx = \\int \_{-\\infty }^{+\\infty } x f\_ X(x)\\, dx - \\int \_{-\\infty }^{+\\infty } \\mu f\_ X(x)\\, dx = \\mu - \\mu \\int \_{-\\infty }^{+\\infty } f\_ X(x)\\, dx = \\mu - \\mu = 0\\){{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\(\\frac{\\sum \\limits \_{i=1}^{N} X\_ i}{N} - \\mu \\to N(\\mu , \\frac{\\sigma ^2}{N}) - \\mu\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\frac{\\sum \\limits \_{i=1}^{N} X\_ i}{N} - \\mu \\to N(\\mu , \\frac{\\sigma ^{2}}{N})\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} \\(\\frac{\\sum \\limits \_{i=1}^{N} X\_ i}{N} - \\mu \\to N(0, \\frac{\\sigma ^{2}}{N})\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} None of the above{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

Direct application of the Central Limit Theorem.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackExpectations ContinueMonte Carlo Methods