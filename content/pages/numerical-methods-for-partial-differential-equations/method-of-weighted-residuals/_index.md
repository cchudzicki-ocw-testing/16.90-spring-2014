---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 2: Numerical Methods for Partial Differential Equations'
parent_type: CourseSection
parent_uid: 125c58ac-6a34-5a7c-bba8-de2d3160cb8b
title: 2.8 Method of Weighted Residuals
uid: bda18124-71a5-87a7-513f-cb81480a1e18
---

*   {{< resource_link cb633bb1-3925-0ab5-7f90-8bb74bb848bb "\<Stability Exercises" >}}
*   {{< resource_link bda18124-71a5-87a7-513f-cb81480a1e18 "2.8.1Functional Approximation of the Solution" >}}
*   {{< resource_link 06f65fc2-70a3-d410-b331-d186ad67852a "2.8.2The Collocation Method" >}}
*   {{< resource_link 2bb791a5-f105-8421-b20e-147e46034287 "2.8.3The Method of Weighted Residuals" >}}
*   {{< resource_link b85dba09-9fd2-582c-61f1-a5573f5c79a5 "2.8.4Galerkin Method with New Basis" >}}
*   {{< resource_link 06f65fc2-70a3-d410-b331-d186ad67852a "\>The Collocation Method" >}}

2.8.1 Functional Approximation of the Solution
----------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.12" "#anchorMO212" >}}

In this lecture, we introduce the method of weighted residuals, which provides a general formulation for the finite element method. To begin, let's focus on the particular problem of steady heat diffusion in a rod. This problem can be modeled as a one-dimensional PDE for the temperature, \\(T\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\left(k T\_ x\\right)\_ x = -f, \\label{equ:steady\_ dif1d}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.149)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(k(x)\\) is the thermal conductivity of the material and \\(f(x)\\) is the heat source (per unit length). Note that both \\(k\\) and \\(f\\) could be functions of \\(x\\). Also, let the physical domain for the problem be from \\(x=-L/2\\) to \\(x=L/2\\).

Steady Heat Diffusion
---------------------

Suppose that the rod has a length of \\(L=2\\), the thermal conductivity is constant, \\(k=1\\), and the heat source is \\(f(x) = 50 e^ x\\). Assume that the temperature at the ends of the rod are to be maintained at \\(T(\\pm 1) = 100\\). Equation ([2.149](javascript: void(0))) can be integrated twice to obtain:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left(k T\_ x\\right)\_ x\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -f,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.150)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle T\_{xx}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -50 e^ x,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.151)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle T\_ x\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -50 e^ x + a,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.152)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle T\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -50 e^ x + ax + b.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.153)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Now, applying boundary conditions so that \\(T(\\pm 1) = 100\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -50 e^{1} + a + b\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 100,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.154)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -50 e^{-1} - a + b\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 100.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.155)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This is a \\(2\\times 2\\) system which can be solved for \\(a\\) and \\(b\\) to find

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle a\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 50 \\sinh (1)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.156)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle b\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 100 + 50 \\cosh (1),\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.157)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\cosh (y) = (e^ y + e^{-y})/2\\) and \\(\\sinh (y) = (e^ y - e^{-y})/2\\). Thus, the exact solution to this problem is

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[T = -50 e^ x + 50 x \\sinh (1) + 100 + 50 \\cosh (1). \\label{equ:steady\_ dif1d\_ Texact}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.158)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

A plot of this solution is shown in Figure {{< resource_link f90ed9a8-1faa-f78e-944f-e334d03d528a "2.25" >}}.

{{< resource f90ed9a8-1faa-f78e-944f-e334d03d528a >}}

**Figure 2.25**: Temperature distribution for \\(f = 50 e^ x\\), \\(L = 2\\), and \\(k=1\\).

A common approach to approximating the solution to a PDE such as heat diffusion is to use a series of weighted functions. For example, for the temperature in the steady heat diffusion example we might assume that,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tilde{T}(x) = 100 + \\sum \_{j=1}^{N} a\_ j \\phi \_ j(x),\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.159)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\tilde{T}(x)\\) is the approximation of \\(T(x)\\), \\(N\\) is the number of terms (functions) in the approximation, \\(\\phi \_ j(x)\\) are the (known) functions, and \\(a\_ j\\) are the unknown function weights. The functions \\(\\phi \_ j(x)\\) are often called _basis functions_. They are usually designed to satisfy the boundary conditions. So, in this example where the temperature is 100 at \\(x = \\pm 1\\), then \\(\\phi \_ j(\\pm 1) = 0\\) (don't forget that \\(\\tilde{T}\\) was defined to include the constant term of 100).

The question remains what functions (and how many) to choose for \\(\\phi \_ j(x)\\). While many good choices exist, we will use polynomials in \\(x\\) because polynomial approximations are used extensively in finite element methods (our main interest). For this problem, the following ideas can be used to determine the form of the \\(\\phi \_ j(x)\\):

*   First, we note that requiring \\(\\phi \_ j(\\pm 1) = 0\\) places two conditions on each \\(\\phi \_ j(x)\\). These two conditions can be satisfied with a linear function of \\(x\\), but the linear function which equals 0 at \\(x = \\pm 1\\) is simply \\(0\\). Since this does not add anything to the solution even after multiplying by a weight, the first non-trivial function would be a quadratic function.
    
*   A quadratic function can be designed to satisy the boundary conditions in the following manner,
    
    {{< tableopen >}}
    {{< tropen >}}
    {{< tdopen >}}
    \\\[\\phi \_1(x) = (1+x)(1-x).\\\]
    {{< tdclose >}}
    {{< tdopen >}}
    (2.160)
    {{< tdclose >}}
    
    {{< trclose >}}
    
    {{< tableclose >}}
    
    By including factors which go to zero at the end points, we have constructed a quadratic function which will satisfy the required boundary conditions. A plot of \\(\\phi \_1(x)\\) is shown in Figure {{< resource_link 8f627342-6ba2-9329-00d2-8b286275f277 "2.26" >}}.
    
*   Suppose we wanted to include a cubic polynomial in the approximation, then one way we could do this is multiply \\(\\phi \_1(x)\\) by \\(x\\).
    
    {{< tableopen >}}
    {{< tropen >}}
    {{< tdopen >}}
    \\\[\\phi \_2(x) = x\\phi \_1(x) = x (1+x) (1-x).\\\]
    {{< tdclose >}}
    {{< tdopen >}}
    (2.161)
    {{< tdclose >}}
    
    {{< trclose >}}
    
    {{< tableclose >}}
    
    Since \\(\\phi \_1(x)\\) goes to zero at the end points, then so will \\(\\phi \_2(x)\\). A plot of \\(\\phi \_2(x)\\) is shown in Figure {{< resource_link 8f627342-6ba2-9329-00d2-8b286275f277 "2.26" >}}. There are actually some better ways to choose these higher-order polynomials then simply multiplying the lowest order polynomial by powers of \\(x\\). The problem with the current approach is that if the number of terms were large (so that the powers of \\(x\\) would be large), then the set of polynomials (i.e., \\(\\phi \_ j(x)\\)) become very poorly conditioned resulting in many numerical difficulties. We will not discuss issues of conditioning but more advanced texts on finite element methods or related subjects can be consulted. For low order polynomial approximations, the issues of conditioning do not play an important role.
    
    {{< resource 8f627342-6ba2-9329-00d2-8b286275f277 >}}
    
    **Figure 2.26**: \\(\\phi \_1(x)\\) and \\(\\phi \_2(x)\\) for example heat diffusion problem.
    

Having selected a set of functions, we must now develop a way to determine values of \\(a\_ j\\) that will lead to a good approximation of the actual \\(T(x)\\). While several ways exist to do this, we will focus on two methods in these introductory notes: the collocation method and the method of weighted residuals.

BackStability Exercises ContinueThe Collocation Method