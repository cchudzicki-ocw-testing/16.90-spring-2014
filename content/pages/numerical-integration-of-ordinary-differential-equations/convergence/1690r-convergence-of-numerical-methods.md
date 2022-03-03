---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.4 Convergence
parent_type: CourseSection
parent_uid: 99ee39b7-79f4-9afb-0849-103c798f1c50
title: 1.4 Convergence
uid: c1ab4737-a98d-26fb-dcee-7c83dfab47d4
---

*   {{< resource_link 99ee39b7-79f4-9afb-0849-103c798f1c50 "\<Convergence" >}}
*   {{< resource_link 99ee39b7-79f4-9afb-0849-103c798f1c50 "1.4.1Types of Errors" >}}
*   {{< resource_link c1ab4737-a98d-26fb-dcee-7c83dfab47d4 "1.4.2Convergence of Numerical Methods" >}}
*   {{< resource_link bc0d43fe-1169-e2be-34aa-cfba7fd50607 "1.4.3Rate of Convergence Global Order of Accuracy" >}}
*   {{< resource_link bc0d43fe-1169-e2be-34aa-cfba7fd50607 "\>Rate of Convergence Global Order of Accuracy" >}}

1.4.2 Convergence of Numerical Methods
--------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.7" "#anchorMO17" >}}

As the timestep is decreased, i.e. \\({\\Delta t}\\rightarrow 0\\), the approximation from a finite difference method should converge to the solution of the ODE. This concept is known as convergence and is stated mathematically as follows:

Definition of Convergence
-------------------------

A finite difference method for solving,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u\_ t = f(u,t) \\qquad \\mbox{with} \\qquad u(0) = u\_0\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.63)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

from \\(t=0\\) to \\(T\\) is convergent if

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\max \_{n=\[0,T/{\\Delta t}\]} |v^ n - u(n{\\Delta t})| \\rightarrow 0 \\qquad \\mbox{as} \\qquad {\\Delta t}\\rightarrow 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.64)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This is a mathematically precise definition; let's take a moment to investigate it a little more deeply. The first part of the statement is familiar by now; we are solving a first-order ODE of the form \\(u\_ t=f(u,t)\\) with given initial conditions. We assume that a method is defined to produce our numerical solution \\(v^ n\\) for \\(n=1,2,\\ldots ,T / {\\Delta t}\\) (we assign \\(v^0=u^0\\)); e.g., the forward Euler method.

In words, the convergence statement is as follows: If we shrink the time step smaller and smaller, the largest absolute error between the numerical solution and the exact solution will also get smaller and smaller. For any numerical solution, the absolute error can be measured at each of the time indices \\(n=0,1,\\ldots , T / {\\Delta t}\\): that is given by \\(|v^ n-u^ n|\\).

Thus, for any numerical solution, we can also define the maximum absolute error over those time indices: that is written \\(\\max \_{n \\in \\{ 0,1,\\ldots ,T/{\\Delta t}\\} }|v^ n-u^ n|\\). This is the worst case error for the numerical solution. If we drive the largest absolute error to zero, it is implied that the error at each time index will also be driven to zero. To summarize, our convergence statement says that in the limit \\({\\Delta t}\\to 0\\), the numerical solution collapses onto the exact solution and the error goes to zero at all time indices.

It is important to note that in the limit \\({\\Delta t}\\to 0\\), the last time index \\(T/{\\Delta t}\\to \\infty\\) even for finite \\(T\\); the time interval between adjacent numerical solution points \\((t^ n,v^ n)\\) and \\((t^{n+1},v^{n+1})\\) is also shrinking to zero. So not only does our numerical solution approach zero error at the time steps \\(t^0,t^1,\\ldots ,\\) these time steps are getting closer and closer together so that the ordered pairs \\((t^0,v^0)\\);\\((t^1,v^1)\\),... make up the entirety of the exact continuous solution \\(u(t)\\).

While convergence is a clear requirement for a good numerical method, the rate at which the method converges is also important. This rate is known as the global order of accuracy and is discussed in the next section.

BackConvergence ContinueRate of Convergence Global Order of Accuracy