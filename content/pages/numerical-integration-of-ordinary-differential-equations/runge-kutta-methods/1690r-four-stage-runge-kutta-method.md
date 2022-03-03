---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.9 Runge-Kutta Methods
parent_type: CourseSection
parent_uid: c5e7e539-a82c-8e62-0c8a-e738a18f6f10
title: 1.9 Runge-Kutta Methods
uid: d5200dfd-d11c-9d13-8626-a6b253c602ff
---

*   {{% resource_link c5e7e539-a82c-8e62-0c8a-e738a18f6f10 "\<Runge-Kutta Methods" %}}
*   {{% resource_link c5e7e539-a82c-8e62-0c8a-e738a18f6f10 "1.9.1Two-Stage Runge-Kutta Methods" %}}
*   {{% resource_link d5200dfd-d11c-9d13-8626-a6b253c602ff "1.9.2Four-Stage Runge-Kutta Method" %}}
*   {{% resource_link 1f5a4263-b1f3-f522-02d6-af00f58ae206 "1.9.3Stability Regions" %}}
*   {{% resource_link 1f5a4263-b1f3-f522-02d6-af00f58ae206 "\>Stability Regions" %}}

1.9.2 Four-stage Runge-Kutta Method
-----------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.16" "#anchorMO116" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.17" "#anchorMO117" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.19" "#anchorMO119" %}}

The most popular form of a four-stage Runge-Kutta method is:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle a\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {\\Delta t}f(v^ n, t^ n)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.145)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle b\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {\\Delta t}f(v^ n+a/2, t^ n + {\\Delta t}/2)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.146)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle c\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {\\Delta t}f(v^ n+b/2, t^ n + {\\Delta t}/2)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.147)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle d\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {\\Delta t}f(v^ n+c, t^ n + {\\Delta t})\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.148)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^{n+1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^ n + \\frac{1}{6}(a + 2b + 2c + d)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.149)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note that this method requires four evaluations of \\(f\\) per iteration. This method is fourth-order accurate, \\(p=4\\).

BackRunge-Kutta Methods ContinueStability Regions