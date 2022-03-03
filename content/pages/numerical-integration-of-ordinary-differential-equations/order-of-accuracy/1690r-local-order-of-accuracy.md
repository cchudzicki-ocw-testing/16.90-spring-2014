---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.3 Order of Accuracy
parent_type: CourseSection
parent_uid: a3fbfbbd-e140-393b-aed5-af945a9316f9
title: 1.3 Order of Accuracy
uid: 09523d4b-aafc-8f4c-e9b7-d3d67ad30e7b
---

*   {{< resource_link 6121a3ca-d8f1-c652-7821-6a952ea8ff2c "\<Local Truncation Error" >}}
*   {{< resource_link a3fbfbbd-e140-393b-aed5-af945a9316f9 "1.3.1Errors" >}}
*   {{< resource_link 6121a3ca-d8f1-c652-7821-6a952ea8ff2c "1.3.2Local Truncation Error" >}}
*   {{< resource_link 09523d4b-aafc-8f4c-e9b7-d3d67ad30e7b "1.3.3Local Order of Accuracy" >}}
*   {{< resource_link 58553753-c9cc-c012-f030-d87844ae8db5 "1.3.4Definition of Multi-Step Methods" >}}
*   {{< resource_link ff3b4491-f1d1-d23e-2d3a-939de701c5c2 "1.3.5Example of Most Accurate Multi-Step Method" >}}
*   {{< resource_link 58553753-c9cc-c012-f030-d87844ae8db5 "\>Definition of Multi-Step Methods" >}}

1.3.3 Local Order of Accuracy
-----------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.5" "#anchorM15" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.8" "#anchorM18" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.10" "#anchorM110" >}}

Suppose we are given a numerical method for solving \\(u\_ t = f(u,t)\\) which we write in the following form,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} = N(v^{n+1},v^ n,v^{n-1}, \\ldots , {\\Delta t})\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.48)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

For simplicity, the possible dependence on \\(t\\) at various \\(n\\) has been omitted in the definition of \\(N\\) (though it should be there). The local truncation error, \\(\\tau\\), is defined as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tau \\equiv N(u^{n+1},u^ n,u^{n-1}, \\ldots , {\\Delta t}) - u^{n+1}, \\label{equ:lte}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.49)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

and the local order of accuracy \\(p\\) is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[|\\tau | = O({\\Delta t}^{p+1}) \\qquad \\mbox{as} \\qquad {\\Delta t}\\rightarrow 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.50)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note: the local order of accuracy is defined to be one less than the order of the leading term of the local truncation error so that the local and global accuracy will be the same.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} p=0{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} p=1{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} p=2{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} None of the above{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} p=0{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} p=1{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} p=2{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} None of the above{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackLocal Truncation Error ContinueDefinition of Multi-Step Methods