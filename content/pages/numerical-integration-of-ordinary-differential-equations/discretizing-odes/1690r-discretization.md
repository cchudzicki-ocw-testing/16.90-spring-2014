---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.2 Discretizing ODEs
parent_type: CourseSection
parent_uid: f239c31a-53e6-28b3-a06a-8e6fff5ed57c
title: 1.2 Discretizing ODEs
uid: 0baef83e-dfb4-b312-66ed-4f9fe5c876ba
---

*   {{% resource_link 18e3e2fd-45b7-38b5-b9bb-4940200d150a "\<An Example of First Order ODE" %}}
*   {{% resource_link f239c31a-53e6-28b3-a06a-8e6fff5ed57c "1.2.1First-Order ODEs" %}}
*   {{% resource_link 18e3e2fd-45b7-38b5-b9bb-4940200d150a "1.2.2An Example of First Order ODE" %}}
*   {{% resource_link 0baef83e-dfb4-b312-66ed-4f9fe5c876ba "1.2.3Discretization" %}}
*   {{% resource_link 9b1b577d-12e2-e60d-75d3-f8fb6ed609d5 "1.2.4The Forward Euler Method" %}}
*   {{% resource_link ae250ef9-53d1-78da-8810-f88b0aaa6408 "1.2.5The Midpoint Method" %}}
*   {{% resource_link 9b1b577d-12e2-e60d-75d3-f8fb6ed609d5 "\>The Forward Euler Method" %}}

1.2.3 Discretization
--------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.5" "#anchorMO15" %}}

When you plot the solution in MATLAB{{< sup "®" >}}, you are likely creating two vectors: one corresponding to points in time \\(t=\[t\_0, t\_1, \\ldots ,t\_ N\]\\) and another corresponding to the solution \\(\\mathbf{u}(t)= \[u(t\_0),u(t\_1),\\ldots ,u(t\_ N)\]\\) at those points in time. This process of representing a continuous function by a finite set of numbers is referred to as discretization. The main idea is illustrated in Figure {{% resource_link b427bd8c-9b82-4708-ff7a-f84a1dd2f56e "1.1" %}}. Instead of representing the function continuously, we represent it as a finite set of ordered pairs \\((t\_ n, u(t\_ n))\\).

{{< resource b427bd8c-9b82-4708-ff7a-f84a1dd2f56e >}}

**Figure 1.1**: Numerical solutions are represented as a finite set of ordered pairs (blue dots) representing the discretization of a continuous function.

When we solve mathematical problems on a computer, it will always be necessary to discretize them. For initial value problems, we will begin with the initial condition \\(u\_0\\) at time \\(t=0\\) and solve forward in time. First we select a time step \\({\\Delta t}>0\\) representing the length of the interval between any two adjacent time points \\(t\_ n\\) and \\(t\_{n+1}\\). Although it is not necessary to choose a constant \\({\\Delta t}\\) for the entire simulation, this is the approach we will take for this course. (You should be aware that state of the art numerical simulation codes adaptively select the time step, e.g., based on an estimate of the error.) Our numerical solution will then involve computing an approximation to the solution \\(u(t\_ n)\\) using information up to (and sometimes including, see implicit methods) time step \\(n\\).

BackAn Example of First Order ODE ContinueThe Forward Euler Method