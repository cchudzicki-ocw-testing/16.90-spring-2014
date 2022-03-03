---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 3: Probabilistic Methods and Optimization'
parent_type: CourseSection
parent_uid: 487c3b15-ab67-d7c9-5cff-a6b147049d0c
title: 3.5 Variance Reduction Techniques for the Monte Carlo Method
uid: e719ff51-42ac-62fb-c38b-4410308e2feb
---

*   {{% resource_link 22e0637c-8322-5bd8-a9d4-e80723fbc928 "\<Bootstrapping" %}}
*   {{% resource_link e719ff51-42ac-62fb-c38b-4410308e2feb "3.5.1Monte Carlo Error as a Random Variable" %}}
*   {{% resource_link bb1256bc-6917-d853-f4c6-36ce5943967f "3.5.2Importance Sampling" %}}
*   {{% resource_link bb1256bc-6917-d853-f4c6-36ce5943967f "\>Importance Sampling" %}}

3.5.1 Monte Carlo Error as a Random Variable
--------------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.9" "#anchorMO39" %}}

Monte Carlo Error as a Random Variable
--------------------------------------

In the last subsection, we analyzed the error made while using the Monte Carlo method to tackle problems exhibiting uncertainty. The key ideas in our analysis were:

1.  The recognition of the Monte Carlo error as a random variable.
    
2.  The result that the error has a normal distribution under certain sampling conditions.
    

Specifically, we recognized that the error \\(e\\) made in estimating the expected value of a random variable \\(X\\) with a distribution \\(f\_ X\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mu \_ X = \\int \\limits \_{-\\infty }^{\\infty } x \\, f\_ X(x) \\, dx\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.58)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

using the canonical estimator,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\bar{y} = \\frac{1}{N} \\sum \\limits \_{i=1}^{N} y\_ i\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.59)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

is a normally distributed random variable,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[e \\to \\mathcal{N}\\left(0,\\frac{\\sigma ^2}{N}\\right)\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.60)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Improving the Monte Carlo Method
--------------------------------

The standard Monte Carlo method that we have seen so far is also called Simple Random Sampling (SRS). As this name suggests, the standard Monte Carlo method is the most simple approach towards dealing with randomness in a system. It is intuitive to think that there are more sophisticated approaches to handle randomness, which would decrease the error faster than SRS.

BackBootstrapping ContinueImportance Sampling