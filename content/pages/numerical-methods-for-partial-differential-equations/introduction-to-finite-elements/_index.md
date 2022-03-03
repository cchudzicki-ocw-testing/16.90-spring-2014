---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 2: Numerical Methods for Partial Differential Equations'
parent_type: CourseSection
parent_uid: 125c58ac-6a34-5a7c-bba8-de2d3160cb8b
title: 2.9 Introduction to Finite Elements
uid: 876be530-ac05-3384-5428-281b2b3c5b68
---

*   {{< resource_link b85dba09-9fd2-582c-61f1-a5573f5c79a5 "\<Galerkin Method with New Basis" >}}
*   {{< resource_link 876be530-ac05-3384-5428-281b2b3c5b68 "2.9.1Motivation" >}}
*   {{< resource_link cc8eecdb-7e89-e1db-ce16-2f90e5ff68fb "2.9.21-D Finite Element Mesh and Notation" >}}
*   {{< resource_link 03bb574d-085a-6995-0b35-3c2a70257228 "2.9.31-D Linear Elements and the Nodal Basis" >}}
*   {{< resource_link 2f262139-b40f-5261-66c9-51230f32cd54 "2.9.4Weak Form of the Weighted Residual" >}}
*   {{< resource_link c369789e-d0c6-3741-858a-5dcba10708e4 "2.9.5Calculation of the Finite Element Weighted Residual" >}}
*   {{< resource_link e47fb6af-9d83-9e3b-073e-b5053c6c2226 "2.9.6Calculation of the Stiffness Matrix" >}}
*   {{< resource_link cc8eecdb-7e89-e1db-ce16-2f90e5ff68fb "\>1-D Finite Element Mesh and Notation" >}}

2.9.1 Motivation
----------------

In this lecture, we introduce the finite element method (FEM). In its most general form, FEM is based on the method of weighted residuals. The application of the method of weighted residuals as described in Section {{< resource_link 2bb791a5-f105-8421-b20e-147e46034287 "2.8.3" >}} becomes difficult when the complexity of the problems increases, specifically in multiple dimensions and with varying properties (e.g., varying thermal conductivity in the heat diffusion problem). The heart of the difficulty in these applications is the construction of the weighted residual integrals. For the simple one-dimensional problem discussed in Section {{< resource_link 2bb791a5-f105-8421-b20e-147e46034287 "2.8.3" >}}, these integrals were relatively easy to do. However, the analogous integrals in multiple dimensions with complex geometries are very difficult to evaluate without some additional form of numerical approximation. For example, consider the heat transfer problem shown in Figure {{< resource_link 30aa9e68-44f1-625b-47ae-714b6219da8b "2.33" >}} and imagine the difficulty in constructing a set of functions which satisfy the boundary conditions and then integrating the weighted residuals of these functions over the entire domain.

{{< resource 30aa9e68-44f1-625b-47ae-714b6219da8b >}}

**Figure 2.33**: Heat transfer problem in a complex domain. Temperature at outer boundary is maintained at \\(T\_0\\). Temperature of all of the internal rectangles except one are maintained at \\(T\_1\\), while the remaining internal rectangle is maintained at \\(T\_2\\).

The finite element method offers one approach to approximating the solution and the weighted residual integrals in general situations and, therefore, makes possible the approximation of complex physical problems. The basic idea behind the finite element method is to discretize the domain into small cells (called elements in FEM) and use these elements to approximate the solution and evaluate the weighted residuals (an example mesh can be seen in Figure {{< resource_link 2d58de59-b4a6-d363-d7fd-d31cdddc6461 "2.34" >}}). Typically, in each element, the solution is approximated using polynomial functions. Then, the weighted residuals are evaluated an element at a time and the resulting system of equations is solved to determine the weighting coefficients on the polynomials in each element.

{{< resource 2d58de59-b4a6-d363-d7fd-d31cdddc6461 >}}

**Figure 2.34**: Mesh for heat transfer problem in a complex domain.

To introduce the basic concepts of the finite element method, we will first discuss the one-dimensional case. In future lectures, we will consider multiple dimensions and return to this complex heat transfer problem.

BackGalerkin Method with New Basis Continue1-D Finite Element Mesh and Notation