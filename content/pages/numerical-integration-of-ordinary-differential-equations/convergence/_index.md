---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 1: Numerical Integration of Ordinary Differential Equations'
parent_type: CourseSection
parent_uid: 5cae4847-c59a-a247-c767-3c0c6b0abef1
title: 1.4 Convergence
uid: 99ee39b7-79f4-9afb-0849-103c798f1c50
---

*   {{% resource_link ff3b4491-f1d1-d23e-2d3a-939de701c5c2 "\<Example of Most Accurate Multi-Step Method" %}}
*   {{% resource_link 99ee39b7-79f4-9afb-0849-103c798f1c50 "1.4.1Types of Errors" %}}
*   {{% resource_link c1ab4737-a98d-26fb-dcee-7c83dfab47d4 "1.4.2Convergence of Numerical Methods" %}}
*   {{% resource_link bc0d43fe-1169-e2be-34aa-cfba7fd50607 "1.4.3Rate of Convergence Global Order of Accuracy" %}}
*   {{% resource_link c1ab4737-a98d-26fb-dcee-7c83dfab47d4 "\>Convergence of Numerical Methods" %}}

1.4.1 Types of Errors
---------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.5" "#anchorMO15" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.6" "#anchorMO16" %}}

When we approximate the solution of ODEs numerically, there are two primary sources of error: rounding (or floating point) errors and truncation errors. Rounding errors are associated to the floating-point arithmetic that our computers use to perform calculations. Truncation errors, on the other hand, are errors we incur based on the numerical method; these errors would exist even in the absence of rounding errors. To some extent, we cannot control rounding errors (they are determined by the precision of the machine), but we can control truncation errors.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} Taylor series approximation of \\(u^ n\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} Taylor series approximation of \\(u^{n+1}\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} Taylor series approximation of \\(u\_ t^{n}\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} None of the above{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: The derivative \\(u^{n}\_ t\\) is evaluated directly, and \\(u^ n\\) is given. The truncation error arises due to truncating the Taylor series of \\(u^{n+1}\\).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackExample of Most Accurate Multi-Step Method ContinueConvergence of Numerical Methods