---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.5 Zero Stability and the Dahlquist Equivalence Theorem
parent_type: CourseSection
parent_uid: fab29380-eb66-91e4-e3ce-4dfce3f50fbe
title: 1.5 Zero Stability and the Dahlquist Equivalence Theorem
uid: e726e961-fd26-9620-907a-1248b173744d
---

*   {{% resource_link 69a13333-afb5-90ee-d339-c7fba31529fd "\<Stability" %}}
*   {{% resource_link fab29380-eb66-91e4-e3ce-4dfce3f50fbe "1.5.1Consistency" %}}
*   {{% resource_link 69a13333-afb5-90ee-d339-c7fba31529fd "1.5.2Stability" %}}
*   {{% resource_link e726e961-fd26-9620-907a-1248b173744d "1.5.3Dahlquist Equivalence Theorem" %}}
*   {{% resource_link 36e637ce-d6ff-e05d-3606-0d537611ad2e "\>Systems of ODE's and Eigenvalue Stability" %}}

1.5.3 Dahlquist Equivalence Theorem
-----------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.7" "#anchorMO17" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.8" "#anchorMO18" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.9" "#anchorMO19" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.10" "#anchorMO110" %}}

In order for a multi-step method to be convergent (as described in Section {{% resource_link c1ab4737-a98d-26fb-dcee-7c83dfab47d4 "1.4.2" %}}), two conditions must be met:

**Consistency**: In the limit of \\({\\Delta t}\\rightarrow 0\\), the method must be a consistent discretization of the ordinary differential equation.

**Stability** In the limit of \\({\\Delta t}\\rightarrow 0\\), the method must not have solutions that can grow unbounded as \\(n = T/{\\Delta t}\\rightarrow \\infty\\).

The Dahlquist Equivalence Theorem in fact guarantees that a consistent and stable multi-step method is convergent, and vice-versa:

Dahlquist Equivalence Theorem
-----------------------------

A multi-step method is convergent if and only if it is consistent and stable.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} zero stable, not consistent, convergent{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} zero stable, consistent, convergent{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} not zero stable, consistent, not convergent{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} not zero stable, not consistent, not convergent{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: The method is consistent, but not zero stable. Since it is not zero stable, the Dahlquist equivalence theorem tells us that the method is not convergent.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackStability ContinueSystems of ODE's and Eigenvalue Stability