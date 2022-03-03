---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.4 Analysis of Finite Difference Methods
parent_type: CourseSection
parent_uid: c9ae23f7-07d4-0d5c-c85b-b19ebf476df0
title: 2.4 Analysis of Finite Difference Methods
uid: 9064faf9-febc-8ca2-e94e-1b057fcc34be
---

*   {{< resource_link c9ae23f7-07d4-0d5c-c85b-b19ebf476df0 "\<Analysis of Finite Difference Methods" >}}
*   {{< resource_link c9ae23f7-07d4-0d5c-c85b-b19ebf476df0 "2.4.1Local Truncation Error for a Derivative Approximation" >}}
*   {{< resource_link 9064faf9-febc-8ca2-e94e-1b057fcc34be "2.4.2Truncation Error of Central Difference Approximation" >}}
*   {{< resource_link ba32080c-16da-eb92-bc6f-615dc10a7e31 "2.4.3Truncation Error for a PDE" >}}
*   {{< resource_link 404d1192-4d4a-07bb-c158-0c3605807e8e "2.4.4Finite Difference Methods in Matrix Form" >}}
*   {{< resource_link 7e5587c8-fac2-cbac-56c4-7e6cdfc52004 "2.4.5General Finite Difference Approximations" >}}
*   {{< resource_link 7d8e6a54-9392-cde6-ff4d-914e606da194 "2.4.6Boundary Conditions for Finite Differences" >}}
*   {{< resource_link ba32080c-16da-eb92-bc6f-615dc10a7e31 "\>Truncation Error for a PDE" >}}

2.4.2 Truncation Error of Central Difference Approximation
----------------------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.8" "#anchorMO28" >}}

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\(-\\frac{1}{3}\\Delta x U\_{xx\_ i} + \\mathcal{O}(\\Delta x^3)\\), first-order accurate{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(-\\frac{1}{6}\\Delta x U\_{xxx\_ i} + \\mathcal{O}(\\Delta x^3)\\), first-order accurate{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} \\(-\\frac{1}{6}\\Delta x^2 U\_{xxx\_ i} + \\mathcal{O}(\\Delta x^4)\\), second-order accurate{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(-\\frac{1}{12}\\Delta x^2 U\_{xxx\_ i} + \\mathcal{O}(\\Delta x^4)\\), second-order accurate{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: The truncation error can be computed by inserting the Taylor series into the finite difference approximation and cancelling the appropriate terms. Since the error is \\(\\mathcal{O}(\\Delta x^2)\\), the approximation is second-order accurate.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackAnalysis of Finite Difference Methods ContinueTruncation Error for a PDE