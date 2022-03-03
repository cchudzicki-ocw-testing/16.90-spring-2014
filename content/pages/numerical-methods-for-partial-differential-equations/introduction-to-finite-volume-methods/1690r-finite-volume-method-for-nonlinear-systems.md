---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.5 Introduction to Finite Volume Methods
parent_type: CourseSection
parent_uid: 3d8df8b8-2291-7094-b5a6-9893808a75cc
title: 2.5 Introduction to Finite Volume Methods
uid: eaeacad2-dafd-9383-3c0e-0227dade769c
---

*   {{% resource_link a9d8dcc7-e873-f01e-6dc3-6f07884b2f23 "\<Finite Volume Method for 2-D Convection on a Rectangular Mesh" %}}
*   {{% resource_link 3d8df8b8-2291-7094-b5a6-9893808a75cc "2.5.1Finite Volume Method in 1-D" %}}
*   {{% resource_link 767b5c96-4bd2-394b-92da-ca9fa25f2e1e "2.5.2Finite Volume Method Applied to 1-D Convection" %}}
*   {{% resource_link d4283096-1401-99d2-0c85-a833f3518826 "2.5.3Finite Volume Method in 2-D" %}}
*   {{% resource_link a9d8dcc7-e873-f01e-6dc3-6f07884b2f23 "2.5.4Finite Volume Method for 2-D Convection on a Rectangular Mesh" %}}
*   {{% resource_link eaeacad2-dafd-9383-3c0e-0227dade769c "2.5.5Finite Volume Method for Nonlinear Systems" %}}
*   {{% resource_link ce70b6b2-dea9-62c9-1d8e-4789958e4499 "\>Upwinding and the CFL Condition" %}}

2.5.5 Finite Volume Method for Nonlinear Systems
------------------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.1" "#anchorMO21" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.3" "#anchorMO23" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.4" "#anchorMO24" %}}

The basic finite volume approach can be extended to nonlinear systems of equations such as the Euler equations. The main issue in this extension is how to calculate an upwind flux when there is a system of equations. In one dimension, the basic finite volume discretization remains the same as given by Equation [2.108](javascript: void(0)),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\Delta x\_ i \\frac{U\_ i^{n+1} - U\_ i^ n}{{\\Delta t}} + F\_{i+\\frac{1}{2}}^{n} - F\_{i-\\frac{1}{2}}^ n = 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.117)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The flux, however, must upwind (to some degree) all of the states in the equation. One relatively simple way in which this can be done is using what is known as the local Lax-Friedrichs flux. In this case, the flux is given by,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[F\_{i+\\frac{1}{2}}(U\_ i, U\_{i+1}) = \\frac{1}{2}\\left\[F(U\_{i+1}) + F(U\_{i})\\right\] - \\frac{1}{2}s\_{\\max }\\left(U\_{i+1} - U\_{i}\\right), \\label{equ:upwindflux\_ laxfriedrichs}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.118)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(s\_{\\max }\\) is the maximum speed of propagation of any small disturbance for either state \\(U\_ i\\) or \\(U\_{i+1}\\).

Lax-Friedrichs Flux for 1-D Euler Equations
-------------------------------------------

For the one-dimensional Euler equations, there are three equations which are approximated, i.e. conservation of mass, conservation of \\(x\\)-momentum, and conservation of energy. A small perturbation analysis can be performed which shows that the three speeds of propagation for this set of equations are \\(u\\), \\(u-a\\), and \\(u+a\\) where \\(u\\) is the flow velocity and \\(a\\) is the speed of sound. Thus, the maximum speed will always be \\(|u| + a\\) and the corresponding value of \\(s\_{\\max }\\) for the Lax-Friedrichs flux is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[s\_{\\max } = \\max \\left(|u|\_{i} + a\_{i}, \\, |u|\_{i+1} + a\_{i+1}\\right).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.119)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

BackFinite Volume Method for 2-D Convection on a Rectangular Mesh ContinueUpwinding and the CFL Condition