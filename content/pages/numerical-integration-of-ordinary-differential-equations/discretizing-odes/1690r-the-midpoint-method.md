---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.2 Discretizing ODEs
parent_type: CourseSection
parent_uid: f239c31a-53e6-28b3-a06a-8e6fff5ed57c
title: 1.2 Discretizing ODEs
uid: ae250ef9-53d1-78da-8810-f88b0aaa6408
---

*   {{% resource_link 9b1b577d-12e2-e60d-75d3-f8fb6ed609d5 "\<The Forward Euler Method" %}}
*   {{% resource_link f239c31a-53e6-28b3-a06a-8e6fff5ed57c "1.2.1First-Order ODEs" %}}
*   {{% resource_link 18e3e2fd-45b7-38b5-b9bb-4940200d150a "1.2.2An Example of First Order ODE" %}}
*   {{% resource_link 0baef83e-dfb4-b312-66ed-4f9fe5c876ba "1.2.3Discretization" %}}
*   {{% resource_link 9b1b577d-12e2-e60d-75d3-f8fb6ed609d5 "1.2.4The Forward Euler Method" %}}
*   {{% resource_link ae250ef9-53d1-78da-8810-f88b0aaa6408 "1.2.5The Midpoint Method" %}}
*   {{% resource_link a3fbfbbd-e140-393b-aed5-af945a9316f9 "\>Order of Accuracy" %}}

1.2.5 The Midpoint Method
-------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.5" "#anchorMO15" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.6" "#anchorMO16" %}}

Now, let's look at another integration method known as the midpoint method. For this method, we will use a slightly different point of view to derive it. Specifically, let's start from the definition of a derivative,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u\_ t(t) = \\lim \_{{\\Delta t}\\rightarrow 0} \\frac{u(t+{\\Delta t}) - u(t-{\\Delta t})}{2{\\Delta t}}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.31)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Now, instead of taking the limit, assume a finite \\({\\Delta t}\\). Then, we end up with an approximation to \\(du/dt\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u\_ t(t) \\approx \\frac{u(t+{\\Delta t}) - u(t-{\\Delta t})}{2{\\Delta t}} \\qquad \\mbox{for small } {\\Delta t}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.32)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, we can re-arrange this to the following estimate for \\(u(t+{\\Delta t})\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u(t+{\\Delta t}) \\approx u(t-{\\Delta t}) + 2{\\Delta t}u\_ t(t) \\label{equ:mp\_ approx}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.33)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, following the same process as in the forward Euler method, we arrive at the midpoint method,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} = v^{n-1} + 2{\\Delta t}f(v^ n, t^ n) \\qquad \\mbox{for} \\qquad n \\geq 1. \\label{equ:mp}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.34)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

However, because of the use of \\(v^{n-1}\\), the midpont method can only be applied for \\(n \\geq 1\\). Thus, for the first timestep a different numerical method must be applied (e.g. the forward Euler method).

We will now solve the falling ice problem using the midpoint method. Using the same values of \\({\\Delta t}\\) and \\(T\\) as before, the results are shown in Figure {{% resource_link aabcb5a5-6cc7-a1aa-bf4b-4d66ea7116d6 "1.3" %}}.

{{< resource aabcb5a5-6cc7-a1aa-bf4b-4d66ea7116d6 >}}

**Figure 1.3**: Behavior of velocity, Reynolds number, and drag coefficient as a function of time for an ice particle falling through the atmosphere. Simulation performed using the midpoint method with \\({\\Delta t}= 0.25\\, sec\\).

Clearly, something has gone wrong here as the results show non-physical oscillations. Perhaps the oscillations will disappear if we take a smaller timestep. To test out this hypothesis, let's re-run the midpoint method with \\({\\Delta t}= 0.025\\, sec\\) which is one-tenth the previous timestep. Those results are shown in Figure {{% resource_link 415431b8-629e-b6a5-21b8-3d83f0b2d5ed "1.4" %}}. Unfortunately, while the results are better, the oscillations are clearly still present. For this problem, clearly the forward Euler method is a better choice than the midpoint method. We will see why this has happened in a few lectures.

{{< resource 415431b8-629e-b6a5-21b8-3d83f0b2d5ed >}}

**Figure 1.4**: Behavior of velocity, Reynolds number, and drag coefficient as a function of time for an ice particle falling through the atmosphere. Simulation performed using the midpoint method with \\({\\Delta t}= 0.025\\, sec\\).

BackThe Forward Euler Method ContinueOrder of Accuracy