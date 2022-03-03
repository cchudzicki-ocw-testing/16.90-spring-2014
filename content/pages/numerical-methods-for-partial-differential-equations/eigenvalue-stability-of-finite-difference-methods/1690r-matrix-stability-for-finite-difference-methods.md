---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.7 Eigenvalue Stability of Finite Difference Methods
parent_type: CourseSection
parent_uid: 935b6a61-8d7d-2772-6ca1-df78ee864834
title: 2.7 Eigenvalue Stability of Finite Difference Methods
uid: 3e2eea01-ee64-f3f7-264f-4d9e57b3b622
---

*   {{< resource_link 935b6a61-8d7d-2772-6ca1-df78ee864834 "\<Eigenvalue Stability of Finite Difference Methods" >}}
*   {{< resource_link 935b6a61-8d7d-2772-6ca1-df78ee864834 "2.7.1Fourier Analysis of PDEs" >}}
*   {{< resource_link 3e2eea01-ee64-f3f7-264f-4d9e57b3b622 "2.7.2Matrix Stability for Finite Difference Methods" >}}
*   {{< resource_link c4a73127-b3ff-feee-5cd9-2e3e6319d356 "2.7.3Circulant Matrices" >}}
*   {{< resource_link cb633bb1-3925-0ab5-7f90-8bb74bb848bb "2.7.4Stability Exercises" >}}
*   {{< resource_link c4a73127-b3ff-feee-5cd9-2e3e6319d356 "\>Circulant Matrices" >}}

2.7.2 Matrix Stability for Finite Difference Methods
----------------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.2" "#anchorMO22" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.9" "#anchorMO29" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.10" "#anchorMO210" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.11" "#anchorMO211" >}}

As we saw in Section {{< resource_link 2687d50f-29a8-875f-7b1d-d6bf668d5db7 "2.3.2" >}}, finite difference (or finite volume) approximations can potentially be written in a semi-discrete form as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{{\\rm d}U}{{\\rm d}t} = AU + b. \\label{equ:semidiscrete}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.133)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

While there are some PDE discretization methods that cannot be written in that form, the majority can be. So, we will take the semi-discrete Equation ([2.133](javascript: void(0))) as our starting point. Note: the term semi-discrete is used to signify that the PDE has only been discretized in space.

Let \\(U(t)\\) be the exact solution to the semi-discrete equation. Then, consider perturbation \\(e(t)\\) to the exact solution such that the perturbed solution, \\(V(t)\\), is:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[V(t) = U(t) + e(t).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.134)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The questions that we wish to resolve are: (1) can the perturbation \\(e(t)\\) grow in time for the semi-discrete problem, and (2) what the stability limits are on the timestep for a chosen time integration method.

First, we substitute \\(V(t)\\) into Equation ([2.133](javascript: void(0))),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{{\\rm d}V}{{\\rm d}t}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle AV + b\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.135)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{{\\rm d}(U+e)}{{\\rm d}t}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle A(U+e) + b\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.136)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{{\\rm d}e}{{\\rm d}t}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle A e.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.137)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the perturbation must satisfy the homogeneous equation, \\(e\_ t = A e\\). Having studied the behavior of linear system of equations in Section {{< resource_link e8dbfb22-04cb-6fc4-431e-0b32e5ea65da "1.6.2" >}}, we know that \\(e(t)\\) will grow unbounded as \\(t \\rightarrow \\infty\\) if any of the real parts of the eigenvalues of \\(A\\) are positive.

The problem is that determining the eigenvalues of \\(A\\) can be non-trivial. In fact, for a general problem finding the eigenvalues of \\(A\\) can be about as hard as solving the specific problem. So, while the matrix stability method is quite general, it can also require a lot of time to perform. Still, the matrix stability method is an indispensible part of the numerical analysis toolkit.

As we saw in the eigenvalue analysis of ODE integration methods, the integration method must be stable for all eigenvalues of the given problem. One manner that we can determine whether the integrator is stable is by plotting the eigenvalues scaled by the timestep in the complex \\(\\lambda {\\Delta t}\\) plane and overlaying the stability region for the desired ODE integrator. Then, \\({\\Delta t}\\) can be adjusted to attempt to bring all eigenvalues into the stability region for the desired ODE integrator.

Matrix Stability of FTCS for 1-D convection
-------------------------------------------

Earlier, we used a forward time, central space (FTCS) discretization for 1-d convection,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{U\_ i^{n+1}-U\_ i^ n}{{\\Delta t}} + u\_{i}^ n\\delta \_{2x} U^ n\_{i} = 0. \\label{equ:con1d\_ ftcs}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.138)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since this method is explicit, the matrix \\(A\\) does not need to be constructed directly, rather Equation ([2.138](javascript: void(0))) can be used to find the new values of \\(U\\) at each point \\(i\\). However, if we are interested in calculating the eigenvalues to analyze the eigenvalue stability, then the \\(A\\) matrix is required. The following script does exactly that (i.e. calculates \\(A\\), determines the eigenvalues of \\(A\\), and then plots the eigenvalues scaled by \\({\\Delta t}\\) overlayed with the forward Euler stability region). The script can set either the inflow/outflow boundary conditions described in Example {{< resource_link 431a74fb-7dca-19ce-0c6f-e4b6a0a6446d "2.3.3" >}}, or can set periodic boundary conditions. We will look at the eigenvalues of both cases.

% This MATLAB script calculates the eigenvalues of
% the one-dimensional convection equation discretized by
% finite differences.  The discretization uses central
% differences in space and forward Euler in time.
%
% Periodic bcs are set if periodic\_flag == 1.
%
% Otherwise, an inflow (dirichlet) bc is set and at
% the outflow a one-sided (backwards) difference is used.
%

clear all;

periodic\_flag = 1;

% Set-up grid
xL = -4;
xR =  4;
Nx = 21; % number of points
x = linspace(xL,xR,Nx);

% Calculate cell size in control volumes (assumed equal)
dx = x(2) - x(1);

% Set velocity
u = 1;

% Set timestep
CFL = 1;
dt = CFL\*dx/abs(u);

% Set bc state at left (assumes u>0)
UL = exp(-xL^2);

% Allocate matrix to hold stiffness matrix (A).
%
A = zeros(Nx-1,Nx-1);

% Construct A except for first and last row
for i = 2:Nx-2,
  A(i,i-1) =  u/(2\*dx);
  A(i,i+1) = -u/(2\*dx);
end

if (periodic\_flag == 1), % Periodic bcs

  A(1   ,2   ) = -u/(2\*dx);
  A(1   ,Nx-1) =  u/(2\*dx);
  A(Nx-1,1   ) = -u/(2\*dx);
  A(Nx-1,Nx-2) =  u/(2\*dx);

else % non-periodic bc's

  % At the first interior node, the i-1 value is known (UL).
  % So, only the i+1 location needs to be set in A.
  A(1,2) = -u/(2\*dx);

  % Outflow boundary uses backward difference
  A(Nx-1,Nx-2) =  u/dx;
  A(Nx-1,Nx-1) = -u/dx;

end

% Calculate eigenvalues of A
lambda = eig(A);

% Plot lambda\*dt
plot(lambda\*dt,'\*');
xlabel('Real \\lambda\\Delta t');
ylabel('Imag \\lambda\\Delta t');

% Overlay Forward Euler stability region
th = linspace(0,2\*pi,101);
hold on;
plot(-1 + sin(th),cos(th));
hold off;
axis('equal');
grid on;

Figures {{< resource_link ed8092cb-f065-5e67-74b7-6b0a79d5a73d "2.21" >}} and {{< resource_link df1ad7e8-1a8d-557c-041c-41ba300c9d9a "2.22" >}} show plots of \\(\\lambda {\\Delta t}\\) for a CFL set to one. Recall that for this one-dimensional problem, the CFL number was defined as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\mathrm{CFL} = \\frac{|u|{\\Delta t}}{{\\scriptstyle \\Delta } x}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.139)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In the inflow/outflow boundary condition case (shown in Figure {{< resource_link ed8092cb-f065-5e67-74b7-6b0a79d5a73d "2.21" >}}) the eigenvalues lay slightly inside the negative real half-plane. As they move away from the origin, they approach the imaginary axis at \\(\\pm i\\). The periodic boundary conditions give purely imaginary eigenvalues but these also approach \\(\\pm i\\) as the move away from the origin. Note that the periodic boundary conditions actually give a zero eigenvalue so that the matrix \\(A\\) is actually singular (Why is this?). Regardless what we see is that for a \\(\\mathrm{CFL} = 1\\), some \\(\\lambda {\\Delta t}\\) exist which are outside of the forward Euler stability region. We could try to lower the timestep to bring all of the \\(\\lambda {\\Delta t}\\) into the stability region, however that will prove to be practically impossible since the extreme eigenvalues approach \\(\\pm \\alpha i\\) (i.e. they are purely imaginary). Thus, no finite value of \\({\\Delta t}\\) exists for which these eigenvalues can be brought inside the circular stability region of the forward Euler method (i.e. the FTCS is unstable for convection).

{{< resource ed8092cb-f065-5e67-74b7-6b0a79d5a73d >}}

**Figure 2.21**: \\(\\Lambda {\\Delta t}\\) distribution for one-dimensional convection example with Dirichlet boundary conditions. Note \\({\\Delta t}\\) set such that \\(CFL=1\\).

{{< resource df1ad7e8-1a8d-557c-041c-41ba300c9d9a >}}

**Figure 2.22**: \\(\\Lambda {\\Delta t}\\) distribution for one-dimensional convection example with periodic boundary conditions. Note \\({\\Delta t}\\) set such that \\(CFL=1\\).

We may also be interested in what happens to the eigenvalue spectrum of \\(A\\) when we change \\(\\Delta x\\) keeping the CFL constant. Figures {{< resource_link 14051c75-1e50-4e5a-f435-9109553002c2 "2.23" >}} and {{< resource_link e56ec9ad-37f6-5316-b90f-8ba4f9cea544 "2.24" >}} plot the eigenvalue spectrum for both periodic and Dirichlet boundary conditions refining \\(\\Delta x\\) by a factor of 10. For the periodic BC case, again we see purely imaginary eigenvalues approaching \\(\\pm i\\) (though, of course, we have more eigenvalues as \\(A\\) is now a larger system). For the Dirichlet case, the eigenvalues again lie slightly inside the negative real half-plane, though in this case closer to the imaginary axis than for the coarser system. In fact, the eigenvalues of the Dirichlet problem approach those of the periodic problem in the limit as \\(\\Delta x \\to 0\\).

{{< resource 14051c75-1e50-4e5a-f435-9109553002c2 >}}

**Figure 2.23**: \\(\\Lambda {\\Delta t}\\) distribution for one-dimensional convection example with Dirichlet boundary conditions. Note \\(\\Delta x=\\frac{1}{20}\\) and \\({\\Delta t}\\) set such that \\(CFL=1\\).

{{< resource e56ec9ad-37f6-5316-b90f-8ba4f9cea544 >}}

**Figure 2.24**: \\(\\Lambda {\\Delta t}\\) distribution for one-dimensional convection example with periodic boundary conditions. Note \\(\\Delta x = \\frac{1}{20}\\) and \\({\\Delta t}\\) set such that \\(CFL=1\\).

BackEigenvalue Stability of Finite Difference Methods ContinueCirculant Matrices