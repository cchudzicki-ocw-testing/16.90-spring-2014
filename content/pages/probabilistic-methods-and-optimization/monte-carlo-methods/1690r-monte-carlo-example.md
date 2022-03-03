---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 3.3 Monte Carlo Methods
parent_type: CourseSection
parent_uid: 2733fa33-374f-cb88-814c-413cb75b3483
title: 3.3 Monte Carlo Methods
uid: 2ff49897-a168-59d4-5d17-feb89ff6fae6
---

*   {{< resource_link e4ed709d-1333-d460-e932-cde246cff19f "\<Monte Carlo Analysis" >}}
*   {{< resource_link 2733fa33-374f-cb88-814c-413cb75b3483 "3.3.1Introduction" >}}
*   {{< resource_link e4ed709d-1333-d460-e932-cde246cff19f "3.3.2Monte Carlo Analysis" >}}
*   {{< resource_link 2ff49897-a168-59d4-5d17-feb89ff6fae6 "3.3.3Monte Carlo Example" >}}
*   {{< resource_link 91c4e401-232c-3823-cf38-1f612b323bb6 "3.3.4Inversion Method for Sampling" >}}
*   {{< resource_link 91c4e401-232c-3823-cf38-1f612b323bb6 "\>Inversion Method for Sampling" >}}

3.3.3 Monte Carlo Example
-------------------------

{{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.3" "#anchorMO33" >}}, {{< resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.5" "#anchorMO35" >}}

To demonstrate the Monte Carlo simulation method in more detail, let's consider the specific case where the thermal barrier coating in the previous turbine blade example is known to be uniformly distributed from \\(0.00025m \< L\_{TBC} \< 0.00075m\\) as shown from the probability density function (PDF) of LTBC in Figure {{< resource_link 6c1cf0fd-d59a-b650-239b-04f487afbfe2 "3.3" >}}.

{{< resource 6c1cf0fd-d59a-b650-239b-04f487afbfe2 >}}

**Figure 3.3**: Probability density function (PDF) of \\(L\_{TBC}\\) uniformly-distributed from 0.00025m \< \\(L\_{TBC}\\) \<0.00075m

The first step is to generate a random sample of \\(L\_{TBC}\\). The basic approach relies on the ability to generate random numbers that are uniformly distributed from 0 to 1. This type of functionality exists within many different scientific programming environments or languages. In MATLAB{{< sup "®" >}}, the command rand returns a random number that is uniformly distributed from 0 to 1. Then, using the uniform distribution from 0 to 1, a uniform distribution of \\(L\_{TBC}\\) over the desired range can be created,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[L\_{TBC} = 0.00025 + 0.0005 U\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.26)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(U\\) is a random variable uniformly distributed from 0 to 1.

This approach is used to create the samples shown as histograms in Figure 21.3 for samples of size \\(N\\) = 100, 1000, and 10000. For the smaller sample size (specifically \\(N\\) = 100), the fact that the sample was drawn from a uniform distribution is not readily apparent. However, as the number of samples increases, the uniform distribution becomes more evident. Clearly, the sample size will have a direct impact on the accuracy of the probabilistic estimates in the Monte Carlo method.

{{< resource 72863293-5ad5-87f9-6c20-4d764f325a40 >}} {{< resource 5685f0bf-0d24-581c-255e-0addfcdd7c93 >}} {{< resource 284b73c3-5c03-ab33-d084-9a5c495a8fee >}}

**Figure 3.4**: Histogram of a random sample from a uniformly-distributed \\(L\_{TBC}\\) for a sample size of N=100,1000,and 10000.

The following is a MATLAB script that implements the Monte Carlo method for this uniform distribution of \\(L\_{TBC}\\). The distributions of \\(T\_{mh}\\) shown in Figure 3.5 correspond to the \\(L\_{TBC}\\) distributions shown in Figure 3.4 and were generated with this script.

clear all; 
hgas = 3000; 
Tgas = 1500; 
ktbc = 1; 
km = 20; 
Lm = 0.003; 
hcool = 1000; 
Tcool = 600; 
N = 100; 
Ltbc = zeros(N,1); 
Tmh = zeros(N,1); 
for n = 1:N, Ltbc(n) = 0.00025 + 0.0005\*rand; 
\[Ttbc, Tmh(n), Tmc, q\] = blade1D(hgas, Tgas, ktbc, Ltbc(n), km, Lm, hcool, Tcool); 
end figure(1); 
hist(Ltbc,20); 
xlabel('\\(L\_{tbc}\\) (m)'); 
figure(2); 
hist(Tmh,20); 
xlabel('\\(T\_{mh}\\) (K)'); 

{{< resource 6c76c91e-1dea-a929-8a3c-d41f939a10ac >}} {{< resource 4acf6f0a-3493-7663-293b-dada4937265a >}} {{< resource a4ae5c4d-684b-d20f-c089-2eb1d37fd728 >}}

**Figure 3.5**: Histogram of \\(T\_{mh}\\), given a uniformly-distributed \\(L\_{TBC}\\), for a sample size of N=100,1000,and 10000

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; \\(\[1060, 1100\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(\[1100, 1150\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; \\(\[1150, 1200\]\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

For any given value of \\(L\_{TBC}\\), \\(T\_{mh}\\) is inversely proportional to \\(L\_{TBC}\\), the thicker the barrier coating, the lower \\(T\_{mh}\\) will be.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackMonte Carlo Analysis ContinueInversion Method for Sampling