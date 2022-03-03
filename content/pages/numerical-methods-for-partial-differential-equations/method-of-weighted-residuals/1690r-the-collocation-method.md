---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.8 Method of Weighted Residuals
parent_type: CourseSection
parent_uid: bda18124-71a5-87a7-513f-cb81480a1e18
title: 2.8 Method of Weighted Residuals
uid: 06f65fc2-70a3-d410-b331-d186ad67852a
---

*   {{% resource_link bda18124-71a5-87a7-513f-cb81480a1e18 "\<Method of Weighted Residuals" %}}
*   {{% resource_link bda18124-71a5-87a7-513f-cb81480a1e18 "2.8.1Functional Approximation of the Solution" %}}
*   {{% resource_link 06f65fc2-70a3-d410-b331-d186ad67852a "2.8.2The Collocation Method" %}}
*   {{% resource_link 2bb791a5-f105-8421-b20e-147e46034287 "2.8.3The Method of Weighted Residuals" %}}
*   {{% resource_link b85dba09-9fd2-582c-61f1-a5573f5c79a5 "2.8.4Galerkin Method with New Basis" %}}
*   {{% resource_link 2bb791a5-f105-8421-b20e-147e46034287 "\>The Method of Weighted Residuals" %}}

2.8.2 The Collocation Method
----------------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.12" "#anchorMO212" %}}, {{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.13" "#anchorMO213" %}} 

One approach to determine the \\(N\\) unknown values of \\(a\_ j\\) would be to enforce the governing PDE at \\(N\\) spatial points in the domain (i.e., to make sure that the the approximate solution exactly satisfies the PDE at \\(N\\) points). Note that in general, the exact solution will not be a linear combination of the \\(\\phi \_ j(x)\\), so it will not be possible for our approximate solution to satisfy the PDE at every point in the domain. To see this, let's substitute our approximate solution \\(\\tilde{T}(x)= 100 + a\_1 \\phi \_1(x) + a\_2 \\phi \_2(x)\\) into Equation  [2.149](javascript: void(0)). First, let's derive an expression for \\(\\tilde{T}\_{xx}\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\tilde{T}\_{xx}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{\\partial ^2}{\\partial x^2}\\left\[a\_1 \\phi \_1(x) + a\_2 \\phi \_2(x)\\right\],\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.162)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle (\\phi \_1)\_{xx}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -2,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.163)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle (\\phi \_2)\_{xx}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -6x,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.164)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\Rightarrow \\tilde{T}\_{xx}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -2 a\_1 - 6 a\_2 x.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.165)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Next, we define a residual for Equation  [2.149](javascript: void(0)),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[R(\\tilde{T},x) \\equiv \\left(k \\tilde{T}\_ x\\right)\_ x + f.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.166)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The residual tells us by how much the approximate solution does not satisfy the governing PDE. If the solution \\(\\tilde{T}\\) were exact, then \\(R = 0\\) for all \\(x\\). Now, substitution of our chosen \\(\\tilde{T}\\) into the residual (recall \\(k=1\\) and \\(f=50 e^ x\\) in this example) gives

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[R(\\tilde{T},x) = -2 a\_1 - 6 a\_2 x + 50 e^ x. \\label{equ:steady\_ dif1d\_ residual}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.167)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Clearly, since \\(a\_1\\) and \\(a\_2\\) are constants (i.e., they do not depend on \\(x\\)), there is no way for this residual to be zero for all \\(x\\).

By setting the residual to be zero at \\(N\\) different points \\(x\\), we will obtain \\(N\\) equations that we can solve to determine the \\(N\\) unknown coefficients. The question remains, where should the \\(N\\) points be selected? The points at which the governing equation will be enforced are known as the collocation points. For our example with \\(N=2\\) , we will choose the relatively simple approach of equally subdividing the domain with \\(N=2\\) interior collocation points. For this domain from \\(-1 \\leq x \\leq 1\\), the equi-distant collocation points would be at \\(x = \\pm 1/3\\). Thus, the two conditions for determining \\(a\_1\\) and \\(a\_2\\) are,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle R(\\tilde{T},-1/3)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.168)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle R(\\tilde{T},1/3)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.169)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

From Equation  [2.167](javascript: void(0)) this gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -2 a\_1 + 2 a\_2 + 50 e^{-1/3}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.170)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -2 a\_1 - 2 a\_2 + 50 e^{1/3}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.171)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Re-arranging this into a matrix form gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\left(\\begin{array}{rr} -2 & 2 \\\\ -2 & -2 \\end{array}\\right) \\left(\\begin{array}{c} a\_1 \\\\ a\_2 \\end{array}\\right) = \\left(\\begin{array}{l} -50 e^{-1/3} \\\\ -50 e^{1/3} \\end{array}\\right).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.172)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}
{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\Rightarrow \\left(\\begin{array}{c} a\_1 \\\\ a\_2 \\end{array}\\right) = \\left(\\begin{array}{l} 25 \\cosh (1/3) \\\\ 25 \\sinh (1/3) \\end{array}\\right) = \\left(\\begin{array}{r} 26.402 \\\\ 8.489 \\end{array}\\right).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.173)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The results using this collocation method are shown in the figures below which include plots of \\(\\tilde{T}(x)\\), the error (i.e., \\(\\tilde{T}(x)-T(x)\\)), and the residual. Note that the residual is exactly zero at the collocation points (i.e., \\(x = \\pm 1/3\\)), though the approximation is not exact at these points (i.e., \\(\\tilde{T} \\neq T\\) at \\(x = \\pm 1/3\\)). This is because the residual \\(R(\\tilde{T},x)\\) measures a different thing to the error \\(\\tilde{T}(x)-T(x)\\). Remember, the residual tells us by how much the PDE is not satisfied at a given point, so it relates to the balance between the terms in the PDE (in our case between the term \\(\\left(k \\tilde{T}\_ x\\right)\_ x\\) and the heat source term \\(f(x)\\)). Even if the PDE is satisfied at a particular point (i.e., the residual is zero at that point), the solution might not be exact at that point.

{{< resource be79de8a-fd6a-2448-1e8b-d7a8e5263dae >}}

**Figure 2.27**: Comparison of \\(T\\) (solid) and \\(\\tilde{T}\\) (dashed) for collocation method.

{{< resource 04da6a92-4cd8-492f-8863-77514ebad64a >}}

**Figure 2.28**: Error \\(\\tilde{T}-T\\) for collocation method.

{{< resource 1782a5cc-3b7a-29ee-273b-6ad9d5b46495 >}}

**Figure 2.29**: Residual \\(R(\\tilde{T},x)\\) for collocation method.

BackMethod of Weighted Residuals ContinueThe Method of Weighted Residuals