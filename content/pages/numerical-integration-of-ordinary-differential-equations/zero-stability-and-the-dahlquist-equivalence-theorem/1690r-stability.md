---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.5 Zero Stability and the Dahlquist Equivalence Theorem
parent_type: CourseSection
parent_uid: fab29380-eb66-91e4-e3ce-4dfce3f50fbe
title: 1.5 Zero Stability and the Dahlquist Equivalence Theorem
uid: 69a13333-afb5-90ee-d339-c7fba31529fd
---

*   {{< resource_link fab29380-eb66-91e4-e3ce-4dfce3f50fbe "\<Zero Stability and the Dahlquist Equivalence Theorem" >}}
*   {{< resource_link fab29380-eb66-91e4-e3ce-4dfce3f50fbe "1.5.1Consistency" >}}
*   {{< resource_link 69a13333-afb5-90ee-d339-c7fba31529fd "1.5.2Stability" >}}
*   {{< resource_link e726e961-fd26-9620-907a-1248b173744d "1.5.3Dahlquist Equivalence Theorem" >}}
*   {{< resource_link e726e961-fd26-9620-907a-1248b173744d "\>Dahlquist Equivalence Theorem" >}}

1.5.2 Stability
---------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.9" "#anchorMO19" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.10" "#anchorMO110" >}}

The remaining issue to determine is whether the solutions to the multi-step method can grow unbounded as \\({\\Delta t}\\rightarrow 0\\) for finite time \\(T\\). Consider again the \\(s\\)-step multi-step method:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} + \\sum \_{i=1}^ s \\alpha \_ i v^{n+1-i} = {\\Delta t}\\sum \_{i=0}^ s \\beta \_ i f^{n+1-i}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.76)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In the limit of \\({\\Delta t}\\rightarrow 0\\), the multi-step approximation will satisfy the following recurrence relationship,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} + \\sum \_{i=1}^ s \\alpha \_ i v^{n+1-i} = 0. \\label{equ:stability\_ recurrence}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.77)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This recurrence relationship can be viewed a providing the characteristic or unforced behavior of the multi-step method. In terms of stability, the question is whether or not the solutions to Equation [1.77](javascript: void(0)) can grow unbounded.

Definition of (Zero) Stability
------------------------------

A multi-step method is stable (also known as zero stable) if all solutions to

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} + \\sum \_{i=1}^ s \\alpha \_ i v^{n+1-i} = 0,\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.78)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

are bounded as \\(n\\rightarrow \\infty\\).

To determine if a method if stable, we assume that the solution to the recurrence has the following form,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^ n = v^0 z^ n,\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.79)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where the superscript in the \\(z^ n\\) term is in fact a power. Note: \\(z\\) can be a complex number. If the recurrence relationship has solutions with \\(|z|>1\\), then the multi-step method would be unstable. For our purposes, a multi-step method with a root of \\(|z|=1\\) is zero-stable provided the root is not repeated. (Note that in general, we need to be careful with the case of \\(|z|=1\\).)

Stability of Most Accurate Two-Step Method
------------------------------------------

In Section {{< resource_link 58553753-c9cc-c012-f030-d87844ae8db5 "1.3.4" >}} , the most accurate two-step, explicit method was found to be,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} + 4v^ n - 5v^{n-1} = {\\Delta t}\\left(4f^ n + 2f^{n-1}\\right).\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.80)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We will determine if this algorithm is stable. The recurrence relationship is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} + 4v^ n - 5v^{n-1} = 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.81)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, substitution of \\(v^ n = v^0 z^ n\\) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[z^{n+1} + 4z^ n - 5z^{n-1} = 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.82)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Factoring this relationship gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[z^{n-1}\\left(z^2 + 4z - 5\\right) = z^{n-1}(z-1)(z+5) = 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.83)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the recurrence relationship has roots at \\(z=1\\), \\(z = -5\\), and \\(z=0\\) (\\(n-1\\) of these roots). The root at \\(z=-5\\) will grow unbounded as \\(n\\) increases so this method is not stable. By the Dahlquist Equivalence Theorem, this means the method is not convergent (even though it has local accuracy \\(p=3\\) and is therefore consistent).

To demonstrate the lack of convergence for this method (due to its lack of stability), we again consider the solution of \\(u\_ t = -u^2\\) with \\(u(0) = 1\\). These results are shown in Figure {{< resource_link 4aa54903-d378-e7e2-8ba3-c43a0f333781 "1.7" >}}.

{{< resource 4aa54903-d378-e7e2-8ba3-c43a0f333781 >}}

**Figure 1.7**: Most-accurate explicit, two-step multi-step method applied to \\(\\dot{u} = -u^2\\) with \\(u(0) = 1\\) with \\({\\Delta t}= 0.1\\) (upper plot) and \\(0.05\\) (lower plot).

These results clearly show the instability. Note that the solution oscillates as is expected since the large parasitic root is negative (\\(z = -5\\)). Furthermore, decreasing \\({\\Delta t}\\) from \\(0.1\\) to \\(0.05\\) only causes the instability to manifest itself in shorter time (though the same number of steps). Clearly, though the method is consistent, it will not converge because of this instability.

BackZero Stability and the Dahlquist Equivalence Theorem ContinueDahlquist Equivalence Theorem