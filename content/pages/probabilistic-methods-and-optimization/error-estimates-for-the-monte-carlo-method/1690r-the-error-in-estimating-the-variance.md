---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 3.4 Error Estimates for the Monte Carlo Method
parent_type: CourseSection
parent_uid: 74bb46fc-55cb-5dc9-1f9b-7be6791726ec
title: 3.4 Error Estimates for the Monte Carlo Method
uid: 9fcaf3a2-fde9-2040-23cd-8a8ace84e37f
---

*   {{< resource_link ed041125-462b-3411-0831-40b32f255066 "\<The Error in Estimating Probabilities" >}}
*   {{< resource_link 74bb46fc-55cb-5dc9-1f9b-7be6791726ec "3.4.1The Error in Estimating the Mean" >}}
*   {{< resource_link ed041125-462b-3411-0831-40b32f255066 "3.4.2The Error in Estimating Probabilities" >}}
*   {{< resource_link 9fcaf3a2-fde9-2040-23cd-8a8ace84e37f "3.4.3The Error in Estimating the Variance" >}}
*   {{< resource_link 22e0637c-8322-5bd8-a9d4-e80723fbc928 "3.4.4Bootstrapping" >}}
*   {{< resource_link 22e0637c-8322-5bd8-a9d4-e80723fbc928 "\>Bootstrapping" >}}

3.4.3 The Error in Estimating the Variance
------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.8" "#anchorMO38" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.11" "#anchorMO311" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.12" "#anchorMO312" >}}

The Error in Estimating the Variance
------------------------------------

The variance of \\(y\\) is given the symbol, \\(\\sigma \_ y^2\\), and is defined as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\sigma \_ y^2 = E\[(y-\\mu \_ y)^2\] \\label{equ:variance}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.52)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We saw in the previous unit that an unbiased estimator of \\(\\sigma \_ y^2\\) is \\(s\_ y^2\\), that is:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[E\[s\_ y^2\] = \\sigma \_ y^2.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.53)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note, you should try proving this result.

To quantify the uncertainty in this estimator, we would like to determine the standard error,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\sigma \_{s^2\_ y} \\equiv \\left\\{ E\\left\[(s\_ y^2-\\sigma \_ y^2)^2\\right\]\\right\\} ^{1/2}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.54)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Unfortunately, this standard error is not known for general distributions of \\(y\\). However, if \\(y\\) has a normal distribution, then,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\sigma \_{s^2\_ y} = \\frac{\\sigma \_ y^2}{\\sqrt {N/2}} \\label{equ:se\_ s2y\_ normal}\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.55)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Under the assumption of \\(y\\) being normally distributed, the distribution of \\(s^2\_ y\\) is also related to the chi-squared distribution. Specifically, \\((N-1)s^2\_ y/\\sigma ^2\_ y\\) has a chi-square distribution with \\(N-1\\) degrees of freedom. Note that the requirement that \\(y\\) be normally distributed is much more restrictive than the requirements for the mean error estimates to hold. For the mean error estimates, the standard error, \\(\\sigma \_{\\overline{y}} = \\sigma \_ y/\\sqrt {N}\\), is exact regardless of the distribution of \\(y\\). The application of the central limit theorem which gives that\\(\\overline{y}\\) is normally distributed only requires that the number of samples is large but does not constrain the distribution of \\(y\\) itself (beyond requiring that \\(f(y)\\) is continuous).

Standard Deviation
------------------

Typically, the standard deviation of \\(y\\) is estimated using \\(s\_ y\\), i.e. the square root of the variance estimator. This estimate, however, is biased,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[E\[s\_ y\] \\neq \\sigma \_ y.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.56)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The standard error for this estimate is only known exactly when \\(y\\) is normally distributed. In that case,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\sigma \_{s\_ y} \\equiv \\left\\{ E\[(s\_ y-\\sigma \_ y)^2\]\\right\\} ^{1/2} = \\frac{\\sigma \_ y}{\\sqrt {2N}}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.57)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

BackThe Error in Estimating Probabilities ContinueBootstrapping