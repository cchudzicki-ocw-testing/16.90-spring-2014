---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 1: Numerical Integration of Ordinary Differential Equations'
parent_type: CourseSection
parent_uid: 5cae4847-c59a-a247-c767-3c0c6b0abef1
title: 1.6 Systems of ODE's and Eigenvalue Stability
uid: 36e637ce-d6ff-e05d-3606-0d537611ad2e
---

*   {{< resource_link e726e961-fd26-9620-907a-1248b173744d "\<Dahlquist Equivalence Theorem" >}}
*   {{< resource_link 36e637ce-d6ff-e05d-3606-0d537611ad2e "1.6.1Nonlinear Systems" >}}
*   {{< resource_link e8dbfb22-04cb-6fc4-431e-0b32e5ea65da "1.6.2Linear Constant Coefficient Systems" >}}
*   {{< resource_link 04ce95ca-3b3a-cc38-5d83-81923a3dd6fe "1.6.3Eigenvalue Stability for a Linear ODE" >}}
*   {{< resource_link 64bbf174-0326-6a46-283d-2d2450cf7589 "1.6.4Imaginary Eigenvalues" >}}
*   {{< resource_link e8dbfb22-04cb-6fc4-431e-0b32e5ea65da "\>Linear Constant Coefficient Systems" >}}

1.6.1 Nonlinear Systems
-----------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.1" "#anchorMO11" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.3" "#anchorMO13" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.6" "#anchorMO16" >}} 

For a system of ODE's, we have the same canonical form as for a scalar (see Equation [1.8](javascript: void(0))),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u\_ t = f(u,t), \\label{equ:ODEsystem\_ nonlinear}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.84)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

except that \\(u\\) and \\(f\\) are vectors of the same length, \\(d\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u = \[u\_1, u\_2, u\_3, \\cdots , u\_ d\]^ T \\qquad f = \[f\_1, f\_2, f\_3, \\cdots , f\_ d\]^ T\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.85)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Nonlinear Pendulum
------------------

One manner in which a system of ODE's occurs is for higher-order ODE's. A classic example of this is a second-order oscillator such as a pendulum. The nonlinear dynamics of a pendulum of length \\(L\\) satisfy the following second-order system of equations:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\theta \_{tt} + \\frac{g}{L}\\sin \\theta = 0. \\label{equ:nonpendulum}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.86)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

To transform this into a system of first-order equations, we define the angular rate, \\(\\omega\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\theta \_ t = \\omega .\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.87)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, Equation [1.86](javascript: void(0)) becomes,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\omega \_ t + \\frac{g}{L}\\sin \\theta = 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.88)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

For this example,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u = \\left(\\begin{array}{c} \\omega \\\\ \\theta \\end{array} \\right) \\qquad f = \\left(\\begin{array}{c} -\\frac{g}{L}\\sin \\theta \\\\ \\omega \\end{array} \\right)\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.89)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

A forward Euler method was used to simulate the motion of a pendulum (with \\(L\\) = 1 m, \\(g = 9.8\\) m/sec\\(^2\\)) released from rest at an angle of \\(45^\\circ\\) at a timestep of \\({\\Delta t}= 0.02\\) seconds. The results are shown in Figure {{< resource_link 68cea58b-b729-83ae-c648-90d3e3ab02ba "1.8" >}}. While the oscillatory motion is evident, the amplitude is growing which is not expected physically. This would indicate some kind of numerical stability problem. Note, however, that if a smaller \\({\\Delta t}\\) were used, the amplification would still be present but not as significant.

{{< resource 68cea58b-b729-83ae-c648-90d3e3ab02ba >}}

**Figure 1.8**: Forward Euler solution for nonlinear pendulum with \\(L\\) = 1 m, \\(g = 9.8\\) m/sec\\(^2\\), and \\({\\Delta t}= 0.02\\) seconds.

The same problem was also simulated using the midpoint method. These results are shown in Figure {{< resource_link 77efec06-ade3-ce91-9e41-a7fca9df929c "1.9" >}}. For this method and \\({\\Delta t}\\) choice, the oscillation amplitude is constant and indicates that the midpoint method is a better choice for this problem than the forward Euler method.

{{< resource 77efec06-ade3-ce91-9e41-a7fca9df929c >}}

**Figure 1.9**: Midpoint solution for nonlinear pendulum with \\(L\\) = 1 m, \\(g = 9.8\\) m/sec\\(^2\\), and \\({\\Delta t}= 0.02\\) seconds.

BackDahlquist Equivalence Theorem ContinueLinear Constant Coefficient Systems