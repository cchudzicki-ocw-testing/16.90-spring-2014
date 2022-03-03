---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.3 Order of Accuracy
parent_type: CourseSection
parent_uid: a3fbfbbd-e140-393b-aed5-af945a9316f9
title: 1.3 Order of Accuracy
uid: 58553753-c9cc-c012-f030-d87844ae8db5
---

*   {{% resource_link 09523d4b-aafc-8f4c-e9b7-d3d67ad30e7b "\<Local Order of Accuracy" %}}
*   {{% resource_link a3fbfbbd-e140-393b-aed5-af945a9316f9 "1.3.1Errors" %}}
*   {{% resource_link 6121a3ca-d8f1-c652-7821-6a952ea8ff2c "1.3.2Local Truncation Error" %}}
*   {{% resource_link 09523d4b-aafc-8f4c-e9b7-d3d67ad30e7b "1.3.3Local Order of Accuracy" %}}
*   {{% resource_link 58553753-c9cc-c012-f030-d87844ae8db5 "1.3.4Definition of Multi-Step Methods" %}}
*   {{% resource_link ff3b4491-f1d1-d23e-2d3a-939de701c5c2 "1.3.5Example of Most Accurate Multi-Step Method" %}}
*   {{% resource_link ff3b4491-f1d1-d23e-2d3a-939de701c5c2 "\>Example of Most Accurate Multi-Step Method" %}}

1.3.4 Definition of Multi-Step Methods
--------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.5" "#anchorM15" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.8" "#anchorM18" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.13" "#anchorM113" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.15" "#anchorM115" %}}

The class of finite difference methods known as multi-step methods is one of the most widely-used approaches for solving ordinary differential equations, and forms the basis for solving partial differential equations as well.

Definition of Multi-Step Methods
--------------------------------

The generic form of an \\(s\\)-step multi-step method is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} + \\sum \_{i=1}^ s \\alpha \_ i v^{n+1-i} = {\\Delta t}\\sum \_{i=0}^ s \\beta \_ i f^{n+1-i}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.51)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

A multi-step method with \\(\\beta \_0 = 0\\) is known as an **explicit** method since in this case the new value \\(v^{n+1}\\) can be determined as an explicit function of known values (i.e. from \\(v^ i\\) and \\(f\_ i\\) with \\(i \\leq n\\)). A multi-step method with \\(\\beta \_0 \\neq 0\\) is known as an **implicit** method since in this case the new value \\(v^{n+1}\\) is an implicit function of itself through the forcing function, \\(f^{n+1} = f(v^{n+1},t^{n+1})\\). We defer implicit methods to Section {{% resource_link 935324e3-1ab2-cb57-9059-0ba1f034fcd5 "1.7.1" %}} and focus on explicit methods here.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}} \\(\\alpha \_1=-1, \\beta \_1=1\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\alpha \_1=1, \\beta \_1=2\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\alpha \_2=-1, \\beta \_1=2\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\alpha \_1=-1, \\beta \_1=2\\){{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

Using the notation given above, the forward Euler method is:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\alpha \_1 = -1 \\quad \\mbox{all other} \\quad \\alpha \_ i = 0\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.52)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}
{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\beta \_1 = 1 \\quad \\mbox{all other} \\quad \\beta \_ i = 0\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.53)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\(\\alpha \_1=-1, \\beta \_1=1\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\alpha \_1=1, \\beta \_1=2\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} \\(\\alpha \_2=-1, \\beta \_1=2\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\alpha \_1=-1, \\beta \_1=2\\){{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

Using the notation given above, the midpoint method is:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\alpha \_2 = -1 \\quad \\mbox{all other} \\quad \\alpha \_ i = 0\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.54)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}
{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\beta \_1 = 2 \\quad \\mbox{all other} \\quad \\beta \_ i = 0\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.55)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackLocal Order of Accuracy ContinueExample of Most Accurate Multi-Step Method