---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.8 Multi-Step Methods
parent_type: CourseSection
parent_uid: 67717326-dffb-7444-5162-101fd9a9ec91
title: 1.8 Multi-Step Methods
uid: 75e73977-a306-f553-2134-b4e0a24fdb81
---

*   {{< resource_link 67717326-dffb-7444-5162-101fd9a9ec91 "\<Multi-Step Methods" >}}
*   {{< resource_link 67717326-dffb-7444-5162-101fd9a9ec91 "1.8.1Adams-Bashforth Methods" >}}
*   {{< resource_link 75e73977-a306-f553-2134-b4e0a24fdb81 "1.8.2Adams-Moulton Methods" >}}
*   {{< resource_link 998bd383-00b6-8dbd-2d38-c251f8262e37 "1.8.3Backwards Differentiation Methods" >}}
*   {{< resource_link f02cecfe-1cd4-8c17-eeff-25be1aaa895d "1.8.4Backwards Differentiation Excercise" >}}
*   {{< resource_link 998bd383-00b6-8dbd-2d38-c251f8262e37 "\>Backwards Differentiation Methods" >}}

1.8.2 Adams-Moulton Methods
---------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.12" "#anchorMO112" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.15" "#anchorMO115" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.17" "#anchorMO117" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.18" "#anchorMO118" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 1.19" "#anchorMO119" >}}

Adams-Moulton methods are implicit methods of the form,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} - v^{n} = {\\Delta t}\\sum \_{i=0}^ s \\beta \_ i f^{n+1-i}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.137)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

These methods use the same time derivative approximation as the Adams-Bashforth methods, however they include the \\(n+1\\) value of \\(f\\).

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}


\\(p\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\beta \_0\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\beta \_1\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\beta \_2\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\beta \_3\\)


{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}


1


{{< tdclose >}}
{{< tdopen >}}


1


{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}


2


{{< tdclose >}}
{{< tdopen >}}


\\(\\frac{1}{2}\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\frac{1}{2}\\)


{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}


3


{{< tdclose >}}
{{< tdopen >}}


\\(\\frac{5}{12}\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\frac{8}{12}\\)


{{< tdclose >}}
{{< tdopen >}}


\\(-\\frac{1}{12}\\)


{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}


4


{{< tdclose >}}
{{< tdopen >}}


\\(\\frac{9}{24}\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\frac{19}{24}\\)


{{< tdclose >}}
{{< tdopen >}}


\\(-\\frac{5}{24}\\)


{{< tdclose >}}
{{< tdopen >}}


\\(\\frac{1}{24}\\)


{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

**Table 3**: Coefficients for Adams-Moulton methods. Note: the \\(p=1\\) method is the backward Euler method, and the \\(p=2\\) method is the Trapezoidal method.

The coefficients for the first through fourth order methods are given in the table above.

{{< resource c5b34db6-e905-9a95-6bed-1aab4aa2492b >}}

**Figure 1.20**: Adams-Moulton stability regions for \\(p=1\\) through \\(p=4\\) methods. Note: \\(p=1\\) is stable outside of contour, the \\(p=2\\) integrator is stable in the left-half plane, and \\(p\\geq 3\\) are stable inside their respective contours.

The stability boundary for these methods are shown in Figure {{< resource_link c5b34db6-e905-9a95-6bed-1aab4aa2492b "1.20" >}}. While the stability regions are larger than the Adams-Bashforth methods, for \\(p>2\\) the methods have bounded stability regions. Thus, they will not be appropriate for stiff problems.

BackMulti-Step Methods ContinueBackwards Differentiation Methods