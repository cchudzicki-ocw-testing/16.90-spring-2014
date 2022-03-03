---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 2: Numerical Methods for Partial Differential Equations'
parent_type: CourseSection
parent_uid: 125c58ac-6a34-5a7c-bba8-de2d3160cb8b
title: 2.5 Introduction to Finite Volume Methods
uid: 3d8df8b8-2291-7094-b5a6-9893808a75cc
---

*   {{% resource_link 7d8e6a54-9392-cde6-ff4d-914e606da194 "\<Boundary Conditions for Finite Differences" %}}
*   {{% resource_link 3d8df8b8-2291-7094-b5a6-9893808a75cc "2.5.1Finite Volume Method in 1-D" %}}
*   {{% resource_link 767b5c96-4bd2-394b-92da-ca9fa25f2e1e "2.5.2Finite Volume Method Applied to 1-D Convection" %}}
*   {{% resource_link d4283096-1401-99d2-0c85-a833f3518826 "2.5.3Finite Volume Method in 2-D" %}}
*   {{% resource_link a9d8dcc7-e873-f01e-6dc3-6f07884b2f23 "2.5.4Finite Volume Method for 2-D Convection on a Rectangular Mesh" %}}
*   {{% resource_link eaeacad2-dafd-9383-3c0e-0227dade769c "2.5.5Finite Volume Method for Nonlinear Systems" %}}
*   {{% resource_link 767b5c96-4bd2-394b-92da-ca9fa25f2e1e "\>Finite Volume Method Applied to 1-D Convection" %}}

2.5.1 Finite Volume Method in 1-D
---------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.1" "#anchorMO21" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.3" "#anchorMO23" %}}

The basis of the finite volume method is the integral convervation law. The essential idea is to divide the domain into many control volumes and approximate the integral conservation law on each of the control volumes. For example, as shown in Figure {{% resource_link 29ce5f24-2c2f-2f7d-b268-c01533ff6c8d "2.13" %}}, cell \\(i\\) lies between the points at \\(x\_{i-\\frac{1}{2}}\\) and \\(x\_{i+\\frac{1}{2}}\\). Note that the points do not have to be equally-spaced.

{{< resource 29ce5f24-2c2f-2f7d-b268-c01533ff6c8d >}}

**Figure 2.13**: Mesh and notation for one-dimensional finite volume method.

The one-dimensional form of Equation [2.1](javascript: void(0)) is

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{{\\rm d}}{{\\rm d}t}\\int \_{x\_ L}^{x\_ R} U\\, dx + \\left.F(U)\\right|\_{x\_ R} - \\left.F(U)\\right|\_{x\_ L} = \\int \_{x\_ L}^{x\_ R} S(U,t)\\, dx. \\label{equ:conservation\_1d}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.99)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, applying this to control volume \\(i\\) (and recalling that \\(S=0\\) for convection) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{{\\rm d}}{{\\rm d}t}\\int \_{x\_{i-\\frac{1}{2}}}^{x\_{i+\\frac{1}{2}}} U\\, dx + \\left. F(U)\\right|\_{x\_{i+\\frac{1}{2}}} - \\left.F(U)\\right|\_{x\_{i-\\frac{1}{2}}} = 0. \\label{equ:conservation\_1d\_ cv}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.100)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Next, we define the mean value of \\(U\\) in control volume \\(i\\) as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U\_ i \\equiv \\frac{1}{\\Delta x\_ i} \\int \_{x\_{i-\\frac{1}{2}}}^{x\_{i+\\frac{1}{2}}} U\\, dx, \\quad \\mbox{where} \\quad \\Delta x\_ i \\equiv x\_{i+\\frac{1}{2}} - x\_{i-\\frac{1}{2}}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.101)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, Equation [2.100](javascript: void(0)) becomes,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\Delta x\_ i \\frac{{\\rm d}U\_ i}{{\\rm d}t} + \\left. F(U)\\right|\_{x\_{i+\\frac{1}{2}}} - \\left.F(U)\\right|\_{x\_{i-\\frac{1}{2}}} = 0. \\label{equ:conservation\_1d\_ cv\_ final}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.102)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

At this point, no approximations have been made thus Equation [2.102](javascript: void(0)) is exact. Now, we make the first approximation. Specifically, we assume that the solution in each control volume is constant,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U(x,t) = U\_ i(t) \\quad \\mbox{for} \\quad x\_{i-\\frac{1}{2}} \< x \< x\_{i+\\frac{1}{2}}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.103)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the finite volume approximation will be piecewise constant as shown in Figure {{% resource_link da5c14dd-5327-cb2c-294c-1017da9038bc "2.14" %}}.

{{< resource da5c14dd-5327-cb2c-294c-1017da9038bc >}}

**Figure 2.14**: Piecewise constant solution for one-dimensional finite volume method.

With this assumed form of the solution, the next issue is to determine the flux at \\(i\\pm \\frac{1}{2}\\) at a time \\(t\\). This can be done with the knowledge that the solution convects with the velocity \\(u(t)\\). Thus, for the initial instant after \\(t\\) (which we denote as \\(t^{+} = t + \\epsilon\\) where \\(\\epsilon\\) is an infinitesimal, positive number):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U(x\_{i+\\frac{1}{2}},t^{+}) = \\left\\{ \\begin{array}{cc} U\_{i}(t) & \\mbox{if } u(t)>0 \\\\ U\_{i+1}(t) & \\mbox{if } u(t)\<0 \\end{array}\\right.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.104)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The flux can be calculated directly from this value of \\(U\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[F(x\_{i+\\frac{1}{2}},t^{+}) = \\left\\{ \\begin{array}{cc} u(t) U\_{i}(t) & \\mbox{if } u(t)>0 \\\\ u(t) U\_{i+1}(t) & \\mbox{if } u(t)\<0 \\end{array}\\right.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.105)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

An alternative way to write this flux which is valid regardless of the sign of \\(u(t)\\) is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[F(x\_{i+\\frac{1}{2}},t^{+}) = \\frac{1}{2}u(t)\\left\[U\_{i+1}(t) + U\_{i}(t)\\right\] - \\frac{1}{2}|u(t)|\\left\[U\_{i+1}(t) - U\_{i}(t)\\right\]. \\label{equ:upwindflux\_ convection1d\_ continuous}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.106)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This flux, which uses the upstream value of \\(U\\) to determine the flux, is known as an ‘upwind' flux. When \\(U\\) is positive, the ‘upwind' direction is the negative \\(x\\) direction because the solution moves towards the positive \\(x\\) direction as \\(t\\) increases. When \\(U\\) is negative, the ‘upwind' direction is the positive \\(x\\) direction because the solution moves towards the negative \\(x\\) direction as \\(t\\) increases.

The final step in arriving at a full-discrete approximation for one-dimensional convection is to discretize Equation [2.102](javascript: void(0)) in time. This can be done choosing any of the ODE integration methods we studied previously. For simplicity, we choose the forward Euler method so that the final fully-discrete form of the finite volume method is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\Delta x\_ i \\frac{U\_ i^{n+1} - U\_ i^ n}{{\\Delta t}} + F\_{i+\\frac{1}{2}}^{n} - F\_{i-\\frac{1}{2}}^ n = 0, \\label{equ:conservation\_1d\_ FVM}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.107)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where we use the notation,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[F\_{i+\\frac{1}{2}}^ n = \\frac{1}{2}u^ n\\left(U\_{i+1}^ n + U\_{i}^ n\\right) - \\frac{1}{2}|u^ n|\\left(U\_{i+1}^ n - U\_{i}^ n\\right). \\label{equ:upwindflux\_ convection1d}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.108)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

BackBoundary Conditions for Finite Differences ContinueFinite Volume Method Applied to 1-D Convection