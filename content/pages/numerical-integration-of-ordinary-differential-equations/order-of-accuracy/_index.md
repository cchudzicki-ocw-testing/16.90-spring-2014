---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 1: Numerical Integration of Ordinary Differential Equations'
parent_type: CourseSection
parent_uid: 5cae4847-c59a-a247-c767-3c0c6b0abef1
title: 1.3 Order of Accuracy
uid: a3fbfbbd-e140-393b-aed5-af945a9316f9
---

*   {{% resource_link ae250ef9-53d1-78da-8810-f88b0aaa6408 "\<The Midpoint Method" %}}
*   {{% resource_link a3fbfbbd-e140-393b-aed5-af945a9316f9 "1.3.1Errors" %}}
*   {{% resource_link 6121a3ca-d8f1-c652-7821-6a952ea8ff2c "1.3.2Local Truncation Error" %}}
*   {{% resource_link 09523d4b-aafc-8f4c-e9b7-d3d67ad30e7b "1.3.3Local Order of Accuracy" %}}
*   {{% resource_link 58553753-c9cc-c012-f030-d87844ae8db5 "1.3.4Definition of Multi-Step Methods" %}}
*   {{% resource_link ff3b4491-f1d1-d23e-2d3a-939de701c5c2 "1.3.5Example of Most Accurate Multi-Step Method" %}}
*   {{% resource_link 6121a3ca-d8f1-c652-7821-6a952ea8ff2c "\>Local Truncation Error" %}}

1.3.1 Errors
------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.5" "#anchorMO15" %}}

There are two sources of error when we solve an ODE with a numerical method. The first is _rounding error_, due to the finite precision of floating-point arithmetic. The second is _truncation error_ (sometimes called discretization error), due to the method used. The truncation error would remain even if we were to use exact arithmetic. We will be concerned with truncation error, which is typically the dominant error source for our problems of interest. We will further define two types of truncation error: the _global error_ is the difference between the computed solution at \\(t^ n\\) and the true solution of the ODE at \\(t^ n\\), while the _local error_ is the error made in one step of the numerical method, i.e. the difference between the computed solution at \\(t^ n\\) and the solution of the ODE passing through the previous point \\((t^{n-1},v^{n-1})\\). We defer the global error to Section {{% resource_link c1ab4737-a98d-26fb-dcee-7c83dfab47d4 "1.4.2" %}} and will investigate the local error here.

BackThe Midpoint Method ContinueLocal Truncation Error