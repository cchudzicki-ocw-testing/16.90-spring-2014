---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.9 Introduction to Finite Elements
parent_type: CourseSection
parent_uid: 876be530-ac05-3384-5428-281b2b3c5b68
title: 2.9 Introduction to Finite Elements
uid: 03bb574d-085a-6995-0b35-3c2a70257228
---

*   {{< resource_link cc8eecdb-7e89-e1db-ce16-2f90e5ff68fb "\<1-D Finite Element Mesh and Notation" >}}
*   {{< resource_link 876be530-ac05-3384-5428-281b2b3c5b68 "2.9.1Motivation" >}}
*   {{< resource_link cc8eecdb-7e89-e1db-ce16-2f90e5ff68fb "2.9.21-D Finite Element Mesh and Notation" >}}
*   {{< resource_link 03bb574d-085a-6995-0b35-3c2a70257228 "2.9.31-D Linear Elements and the Nodal Basis" >}}
*   {{< resource_link 2f262139-b40f-5261-66c9-51230f32cd54 "2.9.4Weak Form of the Weighted Residual" >}}
*   {{< resource_link c369789e-d0c6-3741-858a-5dcba10708e4 "2.9.5Calculation of the Finite Element Weighted Residual" >}}
*   {{< resource_link e47fb6af-9d83-9e3b-073e-b5053c6c2226 "2.9.6Calculation of the Stiffness Matrix" >}}
*   {{< resource_link 2f262139-b40f-5261-66c9-51230f32cd54 "\>Weak Form of the Weighted Residual" >}}

2.9.3 1-D Linear Elements and the Nodal Basis
---------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.16" "#anchorMO216" >}}

The finite element method typically uses polynomial functions inside each element. Furthermore, the approximation is usually required to be continuous from element to element. The simplest element which permits continuous functions would be to assume linear variations of \\(x\\) inside each element. This type of element is called a linear element (not too surprisingly). Using linear finite elements, a sample solution might look like that shown in Figure {{< resource_link 323c3e91-af36-839b-9733-a3e877688b1f "2.36" >}}.

{{< resource 323c3e91-af36-839b-9733-a3e877688b1f >}}

**Figure 2.36**: A linear element solution on a mesh with constant element size, \\(\\Delta x\_ j = 0.2\\).

A linear function can be described by two degrees of freedom. For example, a linear function within an element could be uniquely determined by the following combinations of information:

*   the function values at the two endpoints (i.e., nodes) of the element,
    
*   the function value at some point in the element and the function slope in the element.
    

For a mesh composed of \\(N\\) elements, a total of \\(N+1\\) degrees of freedom exist to describe a continuous, piecewise linear function. If the approximation were allowed to be discontinuous from element to element, then there would be \\(2N\\) degrees of freedom but continuity removes \\(N-1\\) degrees of freedom (one per internal node). Thus, the degrees of freedom to describe a solution over a domain discretized into \\(N\\) linear elements could be (among other choices),

*   the values of the function at the \\(N+1\\) nodes,
    
*   the value of the function at some point in the domain and the slopes in the \\(N\\) elements.
    

The first choice is the most common and leads to what is known as the **nodal basis**.

We now derive the nodal basis functions (i.e., the \\(\\phi \_ j(x)\\)) for linear elements. As discussed above, for \\(N\\) linear elements we have \\(N+1\\) degrees of freedom and therefore \\(N+1\\) basis functions, i.e.,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tilde{T}(x) = \\sum \_{j=1}^{N+1} a\_ j \\phi \_ j(x), \\label{equ:linelem\_ expansion}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.199)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(a\_ j\\) are the \\(N+1\\) degrees of freedom. For a nodal basis, we choose \\(a\_ j = \\tilde{T}(x\_ j)\\). Substituting this into Equation ([2.199](javascript: void(0))) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tilde{T}(x) = \\sum \_{j=1}^{N+1} \\tilde{T}(x\_ j) \\phi \_ j(x).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.200)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Now, evaluating this expansion at node \\(i\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\tilde{T}(x\_ i)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\sum \_{j=1}^{N+1} \\tilde{T}(x\_ j) \\phi \_ j(x\_ i),\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.201)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\Rightarrow \\phi \_ j(x\_ i)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\\{ \\begin{array}{cl} 1, & \\mbox{if } i = j, \\\\ 0, & \\mbox{if } i \\neq j. \\end{array}\\right.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.202)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Finally, since the solutions vary linearly over each element, this means that \\(\\phi \_ j(x)\\) is zero for \\(x \< x\_{j-1}\\) and \\(x > x\_{j+1}\\), increases linearly from zero to one from \\(x\_{j-1}\\) to \\(x\_{j}\\), and decreases linearly back to zero at \\(x\_{j+1}\\). \\(\\phi \_ j(x)\\) is shown in Figure {{< resource_link 80400448-ffd6-9327-116c-3a9c3fc923ac "2.37" >}}. The, specific function is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\phi \_ j(x) = \\left\\{ \\begin{array}{cl} 0, & \\mbox{for } x \< x\_{j-1}, \\\\\[0.1in\] \\frac{x-x\_{j-1}}{\\Delta x\_{j-1}}, & \\mbox{for } x\_{j-1} \< x \< x\_{j},\\\\\[0.1in\] \\frac{x\_{j+1} -x}{\\Delta x\_{j}}, & \\mbox{for } x\_{j} \< x \< x\_{j+1},\\\\\[0.1in\] 0, & \\mbox{for } x > x\_{j+1}. \\end{array}\\right. \\label{equ:phi\_ linear}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.203)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

{{< resource 80400448-ffd6-9327-116c-3a9c3fc923ac >}}

**Figure 2.37**: \\(\\phi \_ j(x)\\) for linear elements using a nodal basis.

Back1-D Finite Element Mesh and Notation ContinueWeak Form of the Weighted Residual