---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 3.5 Variance Reduction Techniques for the Monte Carlo Method
parent_type: CourseSection
parent_uid: e719ff51-42ac-62fb-c38b-4410308e2feb
title: 3.5 Variance Reduction Techniques for the Monte Carlo Method
uid: bb1256bc-6917-d853-f4c6-36ce5943967f
---

*   {{% resource_link e719ff51-42ac-62fb-c38b-4410308e2feb "\<Variance Reduction Techniques for the Monte Carlo Method" %}}
*   {{% resource_link e719ff51-42ac-62fb-c38b-4410308e2feb "3.5.1Monte Carlo Error as a Random Variable" %}}
*   {{% resource_link bb1256bc-6917-d853-f4c6-36ce5943967f "3.5.2Importance Sampling" %}}
*   {{% resource_link 6f317b0d-95c1-d32c-f178-c9fdbae632d2 "\>Introduction to Design Optimization" %}}

3.5.2 Importance Sampling
-------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.4" "#anchorMO34" %}}

Introduction
------------

A Monte Carlo method better than SRS will reduce the variance of the error. Such methods are called variance reduction techniques. One important variance reduction technique is called importance sampling. Importance Sampling reduces variance by cleverly changing the underlying distribution from which we sample. Suppose that we seek to approximate the expected value,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mu = \\int \\limits \_{-\\infty }^{\\infty } h(x) \\, f\_ X(x) \\, dx\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.61)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Suppose we know another probability density \\(w(x)\\). The expectation can then be written as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mu = \\int \\limits \_{-\\infty }^{\\infty } h(x) \\, \\frac{f\_ X(x)}{w(x)} \\, w(x) \\, dx\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.62)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Now instead of sampling from \\(f\_ X(x)\\), we would sample from \\(w(x)\\), but we would have to modify the canonical estimator to the weighted form,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\bar{y}\_{IS} = \\frac{1}{N} \\sum \\limits \_{i=1}^{N} h(x\_ i)\\frac{f\_ X(x\_ i)}{w(x\_ i)} = \\frac{1}{N} \\sum \\limits \_{i=1}^{N} h(x\_ i) w^{\*}(x\_ i)\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.63)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We have modified the underlying distribution from which we are sampling, and hence we have weighted each sample to correct for the bias our modification introduced.

Properties of Importance Sampling Based Methods
-----------------------------------------------

Clearly \\(E(\\bar{y}\_{IS}) = \\mu\\) (show this), but what about \\(Var(\\bar{y}\_{IS})\\) ? We have,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[Var(\\bar{y}\_{IS}) = \\frac{1}{N^2} \\sum \\limits \_{i=1}^{N} Var(h(x\_ i w^{\*}(x\_ i))) = \\frac{1}{N} Var(h(x) w^{\*}(x))\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.64)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The importance sampling method thus reduces variance if we pick a \\(w(x)\\) such that, \\(Var\_{f\_ X}(h(x)) \\leq Var\_{w}(h(x) w^{\*}(x))\\). A little algebra shows that this is true if

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int h^2(x) \\, \\frac{f(x)}{w(x)} \\, f(x) \\, dx \\leq \\int h^2(x) \\, f(x) \\, dx\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.65)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In class, we will discuss how we can pick such a density \\(w(x)\\) and develop an importance sampling algorithm for estimating the probability of low probability events.

BackVariance Reduction Techniques for the Monte Carlo Method ContinueIntroduction to Design Optimization