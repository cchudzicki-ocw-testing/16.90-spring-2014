---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.6 Upwinding and the CFL Condition
parent_type: CourseSection
parent_uid: ce70b6b2-dea9-62c9-1d8e-4789958e4499
title: 2.6 Upwinding and the CFL Condition
uid: cf738358-ae33-664a-5d71-baadd24f92cb
---

*   {{< resource_link ce70b6b2-dea9-62c9-1d8e-4789958e4499 "\<Upwinding and the CFL Condition" >}}
*   {{< resource_link ce70b6b2-dea9-62c9-1d8e-4789958e4499 "2.6.1Upwinding" >}}
*   {{< resource_link cf738358-ae33-664a-5d71-baadd24f92cb "2.6.2The CFL Condition" >}}
*   {{< resource_link 935b6a61-8d7d-2772-6ca1-df78ee864834 "\>Eigenvalue Stability of Finite Difference Methods" >}}

2.6.2 The CFL Condition
-----------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.2" "#anchorMO22" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.5" "#anchorMO25" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.6" "#anchorMO26" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.7" "#anchorMO27" >}}

Recall from {{< resource_link 5b35a359-99c0-aad1-8b33-6126f6b0a143 "2.2.3" >}} that the domain of dependence for the convection equation at \\((x,t)\\) is the characteristic \\(x(s\<t)\\). We can also consider the numerical domain of dependence of the solution at \\((x\_ i, t^ n)\\). Figure {{< resource_link b96582f3-0aae-8cbf-f2cc-8c66fb68cfdc "2.18" >}} shows the numerical domain of dependence of the FTBS method. Note that the numerical domain of dependence at \\(n-2\\) includes the nodes \\(i-2, i-1\\), and \\(i\\). \\((i-2,n-2)\\) and (\\(i-1,n-2\\)) are in the domain of dependence of \\((i,n)\\) because these values are required in the calculation of \\(U\_{i-1}^{n-1}\\), which in turn is required to calculate \\(U\_{i}^ n\\). Similarly, \\((i-1,n-2)\\) and \\((i,n-2)\\) are in the domain of dependence of \\((i,n)\\) because they are required in the calculation of \\(U\_{i}^{n-1}\\).

{{< resource b96582f3-0aae-8cbf-f2cc-8c66fb68cfdc >}}

**Figure 2.18**: Numerical domain of dependence for first order upwind scheme.

We now define two terms:

**CFL condition:** The discretization of a PDE satisfies the CFL condition if the numerical domain of dependence includes the physical domain of dependence.

**CFL Theorem:** The CFL condition is a necessary condition for the discretization of a time-dependent PDE to be convergent (i.e. in the limit as \\(\\Delta t \\to 0\\)). Courant, Friedrichs, and Levy are the authors who first described this requirement in 1928 (well before the first computer!)

In Figures {{< resource_link bb4dac45-da61-e3bd-d6e8-d0ec2adc6ba1 "2.19" >}} and {{< resource_link 74c19906-57c0-8786-a23f-c86c7e2000af "2.20" >}}, the CFL conditions are shown graphically for the one-dimensional convection equation discretized using the first-order upwind scheme.

{{< resource bb4dac45-da61-e3bd-d6e8-d0ec2adc6ba1 >}}

**Figure 2.19**: CFL condition satisfied

{{< resource 74c19906-57c0-8786-a23f-c86c7e2000af >}}

**Figure 2.20**: CFL condition not satisfied

For scheme, the CFL condition requires that

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[CFL \\equiv \\frac{|u|{\\Delta t}}{\\Delta x} \\leq 1\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.123)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

If this condition is not satisfied, then the characteristic will be outside of the numerical domain of dependence and the numerical solution cannot possibly converge to the exact solution if the same ration of \\({\\Delta t}/\\Delta x\\) is maintained as \\({\\Delta t}\\to 0\\), since the numerical method will not have the proper domain of dependence in that limit. The non-dimensional number \\(\\frac{|u|{\\Delta t}}{\\Delta x}\\) is called the **CFL Number** or just the **CFL**. In general, the CFL condition for explicit finite difference methods for convection will require that the CFL number be bounded by a constant which will depend upon the particular numerical scheme (for FTBS, the constant is \\(1\\)).

Exercise
--------

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; \\({\\Delta t}=5\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\({\\Delta t}=1\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\({\\Delta t}=0.01\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; \\({\\Delta t}=0.05\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

We can solve for the maximum \\(\\Delta t\\) as \\(\\Delta x/ |u| = 0.05.\\){{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackUpwinding and the CFL Condition ContinueEigenvalue Stability of Finite Difference Methods