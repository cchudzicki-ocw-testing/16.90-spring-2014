---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.11 The Finite Element Method for Two-Dimensional Diffusion
parent_type: CourseSection
parent_uid: c782bcc9-abb3-f6bc-c638-027dfffdc386
title: 2.11 The Finite Element Method for Two-Dimensional Diffusion
uid: 16176028-e869-5612-f636-568d503833fc
---

*   {{< resource_link c782bcc9-abb3-f6bc-c638-027dfffdc386 "\<The Finite Element Method for Two-Dimensional Diffusion" >}}
*   {{< resource_link c782bcc9-abb3-f6bc-c638-027dfffdc386 "2.11.1Overview" >}}
*   {{< resource_link 16176028-e869-5612-f636-568d503833fc "2.11.2Reference Element and Linear Elements" >}}
*   {{< resource_link 6075ecc5-d133-cbcb-277c-06977e6970ea "2.11.3Differentiation using the Reference Element" >}}
*   {{< resource_link d29ce1ed-3626-60b8-be9b-f2741bbc6ee9 "2.11.4Construction of the Stiffness Matrix" >}}
*   {{< resource_link cd2d971f-e847-d266-f0b1-555caab639d4 "2.11.5Integration in the Reference Element" >}}
*   {{< resource_link 6075ecc5-d133-cbcb-277c-06977e6970ea "\>Differentiation using the Reference Element" >}}

2.11.2 Reference Element and Linear Elements
--------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.15" "#anchorMO215" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.16" "#anchorMO216" >}}

In multiple dimensions, a common practice in defining the polynomial functions within an element is to transform each element into a canonical, or so-called “reference" element. Figure {{< resource_link 5dbd3d5d-6a25-4d1e-6d4b-608d670298d7 "2.47" >}} shows the mapping commonly used for triangular elements which maps a generic triangle in \\((x,y)\\) into a right triangle in \\((\\xi \_1, \\xi \_2)\\).

{{< resource 5dbd3d5d-6a25-4d1e-6d4b-608d670298d7 >}}

**Figure 2.47**: Transformation of a generic triangular element in \\((x,y)\\) into the reference element in \\((\\xi \_1,\\xi \_2)\\).

In the reference element space, the nodal basis for linear polynomials will be one at one of the nodes, and reduce linearly to zero at the other nodes. These functions are

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\phi \_1(\\xi \_1, \\xi \_2)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 1 - \\xi \_1 - \\xi \_2, \\label{equ:phi1\_2d}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.262)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\phi \_2(\\xi \_1, \\xi \_2)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\xi \_1, \\label{equ:phi2\_2d}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.263)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\phi \_3(\\xi \_1, \\xi \_2)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\xi \_2. \\label{equ:phi3\_2d}\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.264)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Then, within the element, the solution \\(\\tilde{T}\\) in the \\((\\xi \_1,\\xi \_2)\\) space is the combination of these three basis functions multiplied by the corresponding nodal coefficients,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\tilde{T}(\\xi \_1,\\xi \_2) = \\sum \_{j=1}^{3} a\_ j \\phi \_ j(\\xi \_1,\\xi \_2). \\label{equ:Txi}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.265)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Using Equation ([2.265](javascript: void(0))), the value of \\(\\tilde{T}\\) can be found at any \\((\\xi \_1,\\xi \_2)\\). To find the \\((x,y)\\) locations in terms of the \\((\\xi \_1, \\xi \_2)\\), we can expand them using the nodal locations and the nodal basis functions, i.e.,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\vec{x}(\\xi \_1,\\xi \_2) = \\sum \_{j=1}^{3} \\vec{x}\_ j \\phi \_ j(\\xi \_1,\\xi \_2).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.266)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since the \\(\\phi \_ i(\\xi \_1,\\xi \_2)\\) are linear functions of \\(\\xi \_1\\) and \\(\\xi \_2\\), this amounts to a linear transformation between \\((\\xi \_1,\\xi \_2)\\) and \\((x,y)\\). Specifically, substituting the nodal basis functions gives

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\vec{x}(\\xi \_1,\\xi \_2)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\vec{x}\_1 \\left(1 - \\xi \_1 - \\xi \_2\\right) + \\vec{x}\_2\\xi \_1 + \\vec{x}\_3\\xi \_2,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.267)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\Rightarrow \\vec{x}(\\xi \_1,\\xi \_2)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\vec{x}\_1 + \\left(\\vec{x}\_2-\\vec{x}\_1\\right)\\xi \_1 + \\left(\\vec{x}\_3-\\vec{x}\_1\\right)\\xi \_2.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.268)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This can be written in a matrix notation as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\left(\\begin{array}{c} x \\\\ y \\end{array}\\right) = \\left(\\begin{array}{c} x\_1 \\\\ y\_1 \\end{array}\\right) + \\left(\\begin{array}{cc} x\_2-x\_1 & x\_3-x\_1 \\\\ y\_2-y\_1 & y\_3-y\_1\\end{array}\\right) \\left(\\begin{array}{c} \\xi \_1 \\\\ \\xi \_2 \\end{array}\\right) \\label{equ:xi\_ to\_ x}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.269)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This equation can be inverted to also determine \\((\\xi \_1,\\xi \_2)\\) as a function of \\((x,y)\\),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\left(\\begin{array}{c} \\xi \_1 \\\\ \\xi \_2 \\end{array}\\right) = \\left(\\begin{array}{cc} x\_2-x\_1 & x\_3-x\_1 \\\\ y\_2-y\_1 & y\_3-y\_1\\end{array}\\right)^{-1} \\left(\\begin{array}{c} x-x\_1 \\\\ y-y\_1 \\end{array}\\right) \\label{equ:x\_ to\_ xi}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.270)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

BackThe Finite Element Method for Two-Dimensional Diffusion ContinueDifferentiation using the Reference Element