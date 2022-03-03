---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 2.3 Introduction to Finite Difference Methods
parent_type: CourseSection
parent_uid: 02467893-75dd-44cc-fcac-58f1a4ee9702
title: 2.3 Introduction to Finite Difference Methods
uid: 431a74fb-7dca-19ce-0c6f-e4b6a0a6446d
---

*   {{< resource_link 2687d50f-29a8-875f-7b1d-d6bf668d5db7 "\<Finite Difference Methods" >}}
*   {{< resource_link 02467893-75dd-44cc-fcac-58f1a4ee9702 "2.3.1Finite Difference Approximations" >}}
*   {{< resource_link 2687d50f-29a8-875f-7b1d-d6bf668d5db7 "2.3.2Finite Difference Methods" >}}
*   {{< resource_link 431a74fb-7dca-19ce-0c6f-e4b6a0a6446d "2.3.3Finite Difference Method Applied to 1-D Convection" >}}
*   {{< resource_link 31ee5fcb-1e6b-78ca-5cb4-d3cb7c073c22 "2.3.4Forward Time-Backward Space FTBS" >}}
*   {{< resource_link 31ee5fcb-1e6b-78ca-5cb4-d3cb7c073c22 "\>Forward Time-Backward Space FTBS" >}}

2.3.3 Finite Difference Method applied to 1-D Convection
--------------------------------------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.2" "#anchorMO22" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.3" "#anchorMO23" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.9" "#anchorMO29" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 2.10" "#anchorMO210" >}}

In this example, we solve 1-D convection,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial U}{\\partial t} + u\\frac{\\partial U}{\\partial x} = 0,\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.58)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

using a central difference spatial approximation with a forward Euler time integration,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{U\_ i^{n+1}-U\_ i^ n}{{\\Delta t}} + u\_{i}^ n\\delta \_{2x} U^ n\_{i} = 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.59)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note: this approximation is the Forward Time-Central Space method from Equation ([2.57](javascript: void(0))) with the diffusion terms removed.

Specifically, we will use a constant velocity \\(u=1\\) and set the initial condition to be a _Gaussian disturbance_:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U\_0(x) = 0.75e^{-\\left(\\frac{x-0.5}{0.1}\\right)^2}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.60)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

We consider the domain \\(\\Omega =\[0.1\]\\), with periodic boundary conditions. A MATLAB{{< sup "®" >}} script that implements this algorithm is:

% This MATLAB script solves the one-dimensional convection
% equation using a finite difference algorithm.  The
% discretization uses central differences in space and forward
% Euler in time.

clear all;
close all;

% Number of points
Nx = 50;
x = linspace(0,1,Nx+1)
dx = 1/Nx;

%velocity
u=1;

% Set final time
tfinal = 10.0;

% Set timestep
dt = 0.001;

% Set initial condition
Uo = 0.75\*exp(-((x-0.5)/0.1).^2)';
t = 0;

U = Uo;

% Loop until t > tfinal
while (t \< tfinal)
    % Forward Euler Step
    U(2:end) = U(2:end) - dt\*u\*centraldiff(U(2:end));
    U(1) = U(end); % enforce periodicity

    % Increment time
    t = t + dt;

    % Plot current solution
    clf
    plot(x,Uo,'b\*');
    hold on;
    plot(x,U,'\*','color',\[0 0.5 0\]);
    xlabel('x','fontsize',16); ylabel('U','fontsize',16);
    title(sprintf('t = %f\\n',t));
    axis(\[0, 1, -0.5, 1.5\]);
    grid on;
    drawnow;
end

Figures {{< resource_link ffbc64a3-1c9b-60e4-3abc-12f2e869fcbc "2.10" >}}, {{< resource_link e13e7724-6319-75c6-c173-a8de99434b2f "2.11" >}}, and {{< resource_link 4d259a41-0f31-1517-35aa-6f0d1fa5bcf5 "2.12" >}} plot the finite difference solution at times \\(t=0.25, t=0.5\\) and \\(t=1.0\\). The exact solution for this problem has \\(U(x,t) = U\_0(x)\\) for any integer time \\((t=1,2, \\ldots ).\\). When the numerical method is run, the Gaussian disturbance is convected across the domain, however small oscillations are observed at \\(t=0.5\\) which begin to pollute the numerical solution. Eventually, these oscillations grow until the entire solution is contaminated. We will later show that the \\(FTCS\\) algorithm is unstable for any \\(\\Delta t\\) for pure convection. Thus, what we are observing is an instability that can be predicted through some analysis.

{{< resource ffbc64a3-1c9b-60e4-3abc-12f2e869fcbc >}}

**Figure 2.10**: Forward Time-Central Space method for 1-D convection at \\(t=0.25\\)

{{< resource e13e7724-6319-75c6-c173-a8de99434b2f >}}

**Figure 2.11**: Forward Time-Central Space method for 1-D convection at \\(t=0.5\\)

{{< resource 4d259a41-0f31-1517-35aa-6f0d1fa5bcf5 >}}

**Figure 2.12**: Forward Time-Central Space method for 1-D convection at \\(t=1.0\\)

BackFinite Difference Methods ContinueForward Time-Backward Space FTBS