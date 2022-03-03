---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.11 The Finite Element Method for Two-Dimensional Diffusion
parent_type: CourseSection
parent_uid: c782bcc9-abb3-f6bc-c638-027dfffdc386
title: 2.11 The Finite Element Method for Two-Dimensional Diffusion
uid: cd2d971f-e847-d266-f0b1-555caab639d4
---

*   {{< resource_link d29ce1ed-3626-60b8-be9b-f2741bbc6ee9 "\<Construction of the Stiffness Matrix" >}}
*   {{< resource_link c782bcc9-abb3-f6bc-c638-027dfffdc386 "2.11.1Overview" >}}
*   {{< resource_link 16176028-e869-5612-f636-568d503833fc "2.11.2Reference Element and Linear Elements" >}}
*   {{< resource_link 6075ecc5-d133-cbcb-277c-06977e6970ea "2.11.3Differentiation using the Reference Element" >}}
*   {{< resource_link d29ce1ed-3626-60b8-be9b-f2741bbc6ee9 "2.11.4Construction of the Stiffness Matrix" >}}
*   {{< resource_link cd2d971f-e847-d266-f0b1-555caab639d4 "2.11.5Integration in the Reference Element" >}}
*   {{< resource_link 487c3b15-ab67-d7c9-5cff-a6b147049d0c "\>Probabilistic Methods and Optimization" >}}

2.11.5 Integration in the Reference Element
-------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.20" "#anchorMO220" >}}

The reference element can also be used to evaluate integrals. For example, consider the evaluation of the forcing function integral within an element:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int \_{\\delta \\Omega \_ k} w(\\vec{x})\\, f(\\vec{x})\\, dA.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.285)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In transforming the integral from \\((x,y)\\) to \\((\\xi \_1,\\xi \_2)\\), the differential area of integration must be transformed using the following result:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[dA = dx\\, dy = J d\\xi \_1\\, d\\xi \_2 = J\\, dA\_{\\xi }. \\label{equ:Ax\_ to\_ Axi}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.286)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the integrals can now be evaluated in reference element space,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int \_{\\Omega \_{\\xi }} w(\\vec{x}(\\vec{\\xi }))\\, f(\\vec{x}(\\vec{\\xi }))\\, J dA\_{\\xi }.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.287)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

BackConstruction of the Stiffness Matrix ContinueProbabilistic Methods and Optimization