---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.7 Stiffness and Implicit Methods
parent_type: CourseSection
parent_uid: 935324e3-1ab2-cb57-9059-0ba1f034fcd5
title: 1.7 Stiffness and Implicit Methods
uid: b363c2d0-1814-cf4c-0cb3-6fe540840d02
---

*   {{% resource_link 543e8406-3445-482c-0202-05c77ce31e71 "\<Implicit Methods for Linear Systems of ODEs" %}}
*   {{% resource_link 935324e3-1ab2-cb57-9059-0ba1f034fcd5 "1.7.1Stiffness" %}}
*   {{% resource_link 900cc931-acfb-c435-72d7-f303ce81ef83 "1.7.2Spectral Condition Number" %}}
*   {{% resource_link 543e8406-3445-482c-0202-05c77ce31e71 "1.7.3Implicit Methods for Linear Systems of ODEs" %}}
*   {{% resource_link b363c2d0-1814-cf4c-0cb3-6fe540840d02 "1.7.4Newton-Raphson Implement Implicit Methods on Nonlinear Problems" %}}
*   {{% resource_link 84564160-240c-f3be-e329-df42818d2eaa "1.7.5Apply Newton-Rhapson" %}}
*   {{% resource_link 84564160-240c-f3be-e329-df42818d2eaa "\>Apply Newton-Rhapson" %}}

1.7.4 Newton-Raphson: Implement Implicit Methods on Nonlinear Problems
----------------------------------------------------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.3" "#anchorMO13" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.4" "#anchorMO14" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.12" "#anchorMO112" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.13" "#anchorMO113" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.14" "#anchorMO114" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.19" "#anchorMO119" %}}

When the ODE's are nonlinear, implicit methods require the solution of a nonlinear system of algebraic equations at each iteration. To see this, consider the use of the trapezoidal method for a nonlinear problem,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} = v^ n + \\frac{1}{2}{\\Delta t}\\left\[f(v^{n+1},t^{n+1})+f(v^ n,t^ n)\\right\].\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.127)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We can define the following residual vector for the trapezoidal method,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[R(w) \\equiv w - v^ n -\\frac{1}{2}{\\Delta t}\\left\[f(w,t^{n+1})+f(v^ n,t^ n)\\right\].\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.128)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, \\(v^{n+1}\\) for the trapezoidal method is given by the solution of,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[R(v^{n+1}) = 0,\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.129)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

which is a nonlinear algebraic system of equations for \\(v^{n+1}\\).

One of the standard methods for solving a nonlinear system of algebraic equations is the Newton-Raphson method. It begins with an initial guess for \\(v^{n+1}\\) and solves a linearized version of \\(R=0\\) to find a correction to the initial guess for \\(v^{n+1}\\). So, define the current guess for \\(v^{n+1}\\) as \\(w^ m\\) where \\(m\\) indicates the sub-iteration in the Newton-Raphson method. Note, common useage is to call the iterations in the Newton-Raphson solution for \\(v^{n+1}\\) sub-iterations since these are iterations which occur within every time iteration from \\(n\\) to \\(n+1\\). To find the correction, \\(\\Delta w\\), where

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[w^{m+1} = w^ m + \\Delta w,\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.130)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

we linearize and solve the nonlinear residual equation,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle R(w^{m+1})\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0, \\nonumber\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.131)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle R(w^ m + \\Delta w)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0, \\nonumber\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.132)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle R(w^ m) + \\left.\\frac{\\partial R}{\\partial w}\\right|\_{w^ m} \\Delta w\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0, \\nonumber\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.133)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left.\\frac{\\partial R}{\\partial w}\\right|\_{w^ m} \\Delta w\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -R(w^ m). \\label{equ:NRsystem}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.134)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This last line is a linear system of equations for the correction since \\({\\partial R}/{\\partial w}\\) is a \\(d \\times d\\) matrix when the original ODE's are a system of \\(d\\) equations. For example, for the trapezoidal method,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\left.\\frac{\\partial R}{\\partial w}\\right|\_{w^ m} = I - \\frac{1}{2}{\\Delta t}\\left.\\frac{\\partial f}{\\partial w}\\right|\_{w^ m}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.135)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Usually, the initial guess for \\(v^{n+1}\\) is the previous iteration, i.e. \\(w^0 = v^ n\\). So, the entire iteration from \\(n\\) to \\(n+1\\) has the following form,

1.  Set initial guess: \\(w^0 = v^ n\\) and \\(m=0\\).
    
2.  Calculate residual \\(R(w^ m)\\) and linearization \\({\\partial R}/{\\partial w}|\_{w^ m}\\).
    
3.  Solve Equation [1.134](javascript: void(0)) for \\(\\Delta w\\).
    
4.  Update \\(w^{m+1} = w^ m + \\Delta w\\).
    
5.  Check if \\(R(w^{m+1})\\) is small. If not, set \\(m \\leftarrow m+1\\) and repeat steps 1 through 4.
    

BackImplicit Methods for Linear Systems of ODEs ContinueApply Newton-Rhapson