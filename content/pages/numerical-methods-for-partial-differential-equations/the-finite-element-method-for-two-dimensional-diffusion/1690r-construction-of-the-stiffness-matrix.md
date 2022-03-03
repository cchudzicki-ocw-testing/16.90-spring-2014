---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.11 The Finite Element Method for Two-Dimensional Diffusion
parent_type: CourseSection
parent_uid: c782bcc9-abb3-f6bc-c638-027dfffdc386
title: 2.11 The Finite Element Method for Two-Dimensional Diffusion
uid: d29ce1ed-3626-60b8-be9b-f2741bbc6ee9
---

*   {{% resource_link 6075ecc5-d133-cbcb-277c-06977e6970ea "\<Differentiation using the Reference Element" %}}
*   {{% resource_link c782bcc9-abb3-f6bc-c638-027dfffdc386 "2.11.1Overview" %}}
*   {{% resource_link 16176028-e869-5612-f636-568d503833fc "2.11.2Reference Element and Linear Elements" %}}
*   {{% resource_link 6075ecc5-d133-cbcb-277c-06977e6970ea "2.11.3Differentiation using the Reference Element" %}}
*   {{% resource_link d29ce1ed-3626-60b8-be9b-f2741bbc6ee9 "2.11.4Construction of the Stiffness Matrix" %}}
*   {{% resource_link cd2d971f-e847-d266-f0b1-555caab639d4 "2.11.5Integration in the Reference Element" %}}
*   {{% resource_link cd2d971f-e847-d266-f0b1-555caab639d4 "\>Integration in the Reference Element" %}}

2.11.4 Construction of the Stiffness Matrix
-------------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.17" "#anchorMO217" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.20" "#anchorMO220" %}}

The stiffness matrix arises in the calculation of \\(\\int \_{\\Omega } \\nabla \\phi \_ i \\cdot \\left(k\\nabla \\tilde{T}\\right)\\, dA\\). As in the one-dimensional case, the \\(i\\)-th row of the stiffness matrix \\(K\\) corresponds to the weighted residual of \\(\\phi \_ i\\). The \\(j\\)-th column in the \\(i\\)-th row corresponds to the dependence of the \\(i\\)-th weighted residual on \\(a\_ j\\). Further drawing on the one-dimensional example, the weighted residuals are assembled by calculating the contribution to all of the residuals from within a single element. In the two-dimensional linear element situation, three weighted residuals are impacted by a given element, specifically, the weighted residuals corresponding to the nodal basis functions of the three nodes of the triangle. For example, in each element we must calculate

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int \_{\\Omega \_ e} \\nabla \\phi \_1 \\cdot \\left(k\\nabla \\tilde{T}\\right)\\, dA, \\qquad \\int \_{\\Omega \_ e} \\nabla \\phi \_2 \\cdot \\left(k\\nabla \\tilde{T}\\right)\\, dA, \\qquad \\int \_{\\Omega \_ e} \\nabla \\phi \_3 \\cdot \\left(k\\nabla \\tilde{T}\\right)\\, dA,\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.281)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\Omega \_ e\\) is spatial domain for a specific element. As described in Section {{% resource_link 6075ecc5-d133-cbcb-277c-06977e6970ea "2.11.3" %}}, the gradient of \\(\\tilde{T}\\) can be written,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\nabla \\tilde{T}(x,y)= \\sum \_{j=1}^{3} a\_ j\\nabla \\phi \_ j(x,y),\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.282)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

thus the weighted residuals expand to,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int \_{\\Omega } \\nabla \\phi \_ i \\cdot \\left(k\\nabla \\tilde{T}\\right)\\, dA = \\sum \_{j=1}^{3} a\_ j K\_{i,j}, \\qquad \\mbox{where } \\qquad K\_{i,j} \\equiv \\int \_{\\Omega } \\nabla \\phi \_ i \\cdot \\left(k\\nabla \\phi \_ j\\right)\\, dA.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.283)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

For the situation in which \\(k\\) is constant and linear elements are used, then this reduces to

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[K\_{i,j} \\equiv k \\nabla \\phi \_ i \\cdot \\nabla \\phi \_ j A\_ e,\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.284)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(A\_ e\\) is the area of element \\(e\\).

BackDifferentiation using the Reference Element ContinueIntegration in the Reference Element