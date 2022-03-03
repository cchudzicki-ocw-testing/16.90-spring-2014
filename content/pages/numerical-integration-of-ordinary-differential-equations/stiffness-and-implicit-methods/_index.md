---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 1: Numerical Integration of Ordinary Differential Equations'
parent_type: CourseSection
parent_uid: 5cae4847-c59a-a247-c767-3c0c6b0abef1
title: 1.7 Stiffness and Implicit Methods
uid: 935324e3-1ab2-cb57-9059-0ba1f034fcd5
---

*   {{< resource_link 64bbf174-0326-6a46-283d-2d2450cf7589 "\<Imaginary Eigenvalues" >}}
*   {{< resource_link 935324e3-1ab2-cb57-9059-0ba1f034fcd5 "1.7.1Stiffness" >}}
*   {{< resource_link 900cc931-acfb-c435-72d7-f303ce81ef83 "1.7.2Spectral Condition Number" >}}
*   {{< resource_link 543e8406-3445-482c-0202-05c77ce31e71 "1.7.3Implicit Methods for Linear Systems of ODEs" >}}
*   {{< resource_link b363c2d0-1814-cf4c-0cb3-6fe540840d02 "1.7.4Newton-Raphson Implement Implicit Methods on Nonlinear Problems" >}}
*   {{< resource_link 84564160-240c-f3be-e329-df42818d2eaa "1.7.5Apply Newton-Rhapson" >}}
*   {{< resource_link 900cc931-acfb-c435-72d7-f303ce81ef83 "\>Spectral Condition Number" >}}

1.7.1 Stiffness
---------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.2" "#anchorMO12" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.9" "#anchorMO19" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.11" "#anchorMO111" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.12" "#anchorMO112" >}}

Stiffness is a general (though somewhat fuzzy) term to describe systems of equations which exhibit phenoma at widely-varying scales. For the ODE's we have been studying, this means widely-varying timescales.

One way for stiffness to arise is through a difference in timescales between a forcing timescale and any characteristic timescales of the unforced system. For example, consider the following problem:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u\_ t + 1000 u = 100\\sin t, \\qquad u(0) = 1. \\label{equ:forced\_ stiff}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.109)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The forcing term oscillates with a frequency of \\(1\\). By comparison, the unforced problem decays very rapidly since the eigenvalue is \\(\\lambda =-1000\\). Thus, the timescales are different by a factor of 1000.

Suppose we are only interested in the long time behavior of \\(u(t)\\), not the initial transient. We would like to take a timestep that would be set by the requirements to resolve the \\(\\sin t\\) forcing. For example, one might expect that setting \\({\\Delta t}= 2\\pi /100\\) (which would result in 100 timesteps per period of the forcing) would be sufficient to have reasonable accuracy. However, if the method does not have a large eigenvalue stability region, this may not be possible. In this case, the \\({\\Delta t}\\) set by stability requirements is much smaller than what we need for accuracy. A small \\({\\Delta t}\\) means that many iterations are needed, which makes the simulation computationally expensive. For example, if a forward Euler method is applied to this problem, eigenvalue stability would limit the \\({\\Delta t}\\leq 0.002\\) (since the eigenvalue is \\(\\lambda = -1000\\) and the forward Euler stability region crosses the real axis at -2). The results from simulations for a variety of \\({\\Delta t}\\) using forward Euler are shown in Figure {{< resource_link 799fbd6f-42df-695d-64e6-b06528802e94 "1.12" >}}. For \\({\\Delta t}= 0.001\\), the solution is well behaved and looks realistic. For \\({\\Delta t}= 0.0019\\), the approach of eigenvalue instability is evident as there are oscillations during the first few iterations which eventually decay. For \\({\\Delta t}= 0.002\\), the oscillations no longer decay but remain throughout the entire simulation. Finally, for \\({\\Delta t}= 0.0021\\), the oscillations grow unbounded. A zoomed image of these results concentrating on the initial time behavior is shown in Figure {{< resource_link d07c23e6-43e4-df4c-1d71-72833d2ea8a3 "1.13" >}}.

{{< resource 799fbd6f-42df-695d-64e6-b06528802e94 >}}

**Figure 1.12**: Forward Euler solution for \\(u\_ t + 1000 u = 100\\sin t\\) with \\(u(0) = 1\\) at \\({\\Delta t}= 0.001\\), 0.0019, 0.002, and 0.0021.

{{< resource d07c23e6-43e4-df4c-1d71-72833d2ea8a3 >}}

**Figure 1.13**: Forward Euler solution for \\(u\_ t + 1000 u = 100\\sin t\\) with \\(u(0) = 1\\) at \\({\\Delta t}= 0.001\\), 0.0019, 0.002, and 0.0021. Same results as in Figure {{< resource_link 799fbd6f-42df-695d-64e6-b06528802e94 "1.12" >}} just showing the small \\(t\\) behavior in more detail.

A more efficient approach to numerically integrating this stiff problem would be to use a method with eigenvalue stability for large negative real eigenvalues. Implicit methods often have excellent stability along the negative real axis. Recall from Lecture 3 that an implicit method is one in which the new value \\(v^{n+1}\\) is an implicit function of itself through the forcing function \\(f\\). The simplest implicit method is the backward Euler method,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} = v^ n + {\\Delta t}f(v^{n+1},t^{n+1}). \\label{equ:be}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.110)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The backward Euler method is first order accurate (\\(p=1\\)). The amplification factor for this method is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[g = \\frac{1}{1 - \\lambda {\\Delta t}} \\label{equ:be\_ amp}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.111)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

When \\(\\lambda\\) is negative real, then \\(g \< 1\\) for all \\({\\Delta t}\\). The eigenvalue stability region for the backward Euler method is shown in Figure {{< resource_link 990b5085-d189-e06d-5f7f-7e0dc9ef7aa8 "1.14" >}}.

{{< resource 990b5085-d189-e06d-5f7f-7e0dc9ef7aa8 >}}

**Figure 1.14**: Backward Euler stability region

Only the small circular portion in the right-half plane is unstable while the entire left-half plane is stable. Results from the application of the backward Euler method to Equation [1.109](javascript: void(0)) are shown in Figure {{< resource_link da288cb5-2b8f-04bb-4607-b8e1a7bcdfdd "1.15" >}}.

{{< resource da288cb5-2b8f-04bb-4607-b8e1a7bcdfdd >}}

**Figure 1.15**: Backward Euler solution for \\(u\_ t + 1000 u = 100\\sin t\\) with \\(u(0) = 1\\) at \\({\\Delta t}= 0.0005\\), 0.005, 0.05, and 0.5.

The excellent stability properties of this method are clearly seen as the solution looks acceptable for all of the tested \\({\\Delta t}\\). Clearly, for the larger \\({\\Delta t}\\), the initial transient is not accurately simulated, however, it does not effect the stability. Thus, as long as the initial transient is not desired, the backward Euler method will likely be a more effective solution strategy than the forward Euler method for this problem.

Another popular implicit method is trapezoidal integration,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} = v^ n + \\frac{1}{2}{\\Delta t}\\left\[f(v^{n+1},t^{n+1})+f(v^ n,t^ n)\\right\]. \\label{equ:trap}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.112)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Trapezoidal integration is second-order accurate (\\(p=2\\)). The amplification factor is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[g = \\frac{1 + \\frac{1}{2}\\lambda {\\Delta t}}{1 - \\frac{1}{2}\\lambda {\\Delta t}}. \\label{equ:trap\_ amp}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.113)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The stability boundary for trapezoidal integration lies on the imaginary axis (see Figure {{< resource_link fbebc2ef-28a6-8b77-ed1c-3f50c18d74ab "1.16" >}}).

{{< resource fbebc2ef-28a6-8b77-ed1c-3f50c18d74ab >}}

**Figure 1.16**: Trapezoidal integration stability region

Again, this method is stable for the entire left-half plane thus it will work well for stiff problems.

{{< resource fbc8923a-10d7-61d5-017d-010fde37e96e >}}

**Figure 1.17**: Comparison of error for forward Euler, backward Euler, and trapezoidal integration versus \\({\\Delta t}\\) for \\(u\_ t + 1000 u = 100\\sin t\\) with \\(u(0) = 1\\).

The accuracy of the forward Euler, backward Euler, and trapezoidal integration methods are compared in Figure {{< resource_link fbc8923a-10d7-61d5-017d-010fde37e96e "1.17" >}} for Equation [1.109](javascript: void(0)). The error is computed as the maximum across all timesteps of the difference between numerical and exact solutions,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[E = \\max \_{n=\[0,T/{\\Delta t}\]} |v^ n - u(n{\\Delta t})|.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.114)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

These results show that the forward Euler method is first order accurate (since the slope on the log-log scaling is 1) once the \\({\\Delta t}\\) is small enough to have eigenvalue stability (for \\({\\Delta t}> 0.002\\) the algorithm is unstable and the errors are essentially unbounded). In contrast, the two implicit methods have reasonable errors for all \\({\\Delta t}\\)'s. As the \\({\\Delta t}\\) become small, the slope of the backward Euler and trapezoidal methods become essentially 1 and 2 (indicating first and second order accuracy). Clearly, if high accuracy is required, the trapezoidal method will require fewer timesteps to achieve this accuracy.

Stiffness from PDE discretization of diffusion problem
------------------------------------------------------

One of the more common ways for a stiff system of ODE's to arise is in the discretization of time-dependent partial differential equations (PDE's). For example, consider a one-dimensional heat diffusion problem that is modeled by the following PDE for the temperature, \\(T\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[T\_ t = \\frac{k}{\\rho c\_ p}T\_{xx}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.115)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\rho\\), \\(c\_ p\\), and \\(k\\) are the density, specific heat, and thermal conductivity of the material, respectively. Suppose the physical domain for of length \\(L\\) from \\(x=0\\) to \\(x=L\\). A finite difference approximation in \\(x\\) might divide the physical domain into a set of equally spaced nodes with distance \\(h = L/(N-1)\\) where \\(N\\) is the total number of nodes including the endpoints. So, node \\(i\\) would be located at \\(x\_ i = ih\\). Then, at each node, \\(T\_{xx}\\) is approximated using a finite difference derivative. For example, at node \\(i\\) we might use the following approximation,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\left.T\_{xx}\\right|\_ i = \\frac{T\_{i+1} - 2 T\_ i + T\_{i-1}}{h^2}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.116)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Using this in the heat diffusion equation, we can find the time rate of change at node \\(i\\) as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\left.T\_ t\\right|\_ i = \\frac{k}{\\rho c\_ p}\\frac{T\_{i+1} - 2 T\_ i + T\_{i-1}}{h^2}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.117)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the \\(T\_ t\\) at node \\(i\\) depends on the values of \\(T\\) at nodes \\(i-1\\), \\(i\\), and \\(i+1\\) in a linear manner. Since each node in the interior of the domain will satisfy the same equation, we can put the finite difference discretization of the heat diffusion problem into our standard system of ODE's form,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u\_ t = A u + b, \\qquad u = \[T\_2, T\_3, T\_4, \\ldots , T\_{N-1}\]^ T,\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.118)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(A\\) will be a tri-diagonal matrix (i.e. only the main diagonal and the two neighboring diagonals will be non-zero) since the finite difference approximation only depends on the neighboring nodes. The vector \\(b\\) will depend on the specific boundary conditions.

The question is how do the eigenvalues of \\(A\\) behave, in particular, as the node spacing \\(h\\) is decreased. To look at this, we arbitrarily choose,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{k}{\\rho c\_ p} = 1 \\qquad L = 1\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.119)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

since the magnitudes of these parameters will scale the magnitude of the eigenvalues of \\(A\\) by the same value but not alter the ratio of eigenvalues (the ratio is only altered by the choice of \\(h/L\\)). Figure {{< resource_link 1372ae81-aa85-cd3e-5698-1112af79fed1 "1.18" >}} shows the locations of the eigenvalues for \\(h/L = 0.1\\) and \\(h/L = 0.05\\).

{{< resource 1372ae81-aa85-cd3e-5698-1112af79fed1 >}}

**Figure 1.18**: Eigenvalues for discretization of one-dimenionsal diffusion equation for \\(h/L = 0.1\\) and \\(h/L = 0.05\\).

The eigenvalues are negative real numbers. The smallest magnitude eigenvalues appear to be nearly unchanged by the different values of \\(h\\). However, the largest magnitude eigenvalues appear to have increased by a factor of \\(4\\) from approximately \\(-400\\) to \\(-1600\\) when \\(h\\) decreased by a factor of \\(2\\). This suggests that the ratio of largest-to-smallest magnitude eigenvalues (i.e. the spectral condition number) is \\(O(1/h^2)\\).

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}


\\(h/L\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\min |\\lambda |\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\max |\\lambda |\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\max |\\lambda |/\\min |\\lambda |\\)


{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}


0.001


{{< tdclose >}}
{{< tdopen >}}


9.87


{{< tdclose >}}
{{< tdopen >}}


3999990


{{< tdclose >}}
{{< tdopen >}}


405284


{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}


0.01


{{< tdclose >}}
{{< tdopen >}}


9.86


{{< tdclose >}}
{{< tdopen >}}


39990


{{< tdclose >}}
{{< tdopen >}}


4052


{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}


0.1


{{< tdclose >}}
{{< tdopen >}}


9.79


{{< tdclose >}}
{{< tdopen >}}


390


{{< tdclose >}}
{{< tdopen >}}


40


{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

**Table 1**: Minimum and maximum magnitude eigenvalues for one-dimensional diffusion

The table above confirms this depends for a range of \\(h/L\\) values and also confirms that the smallest eigenvalue changes very little as \\(h\\) decreases.

BackImaginary Eigenvalues ContinueSpectral Condition Number