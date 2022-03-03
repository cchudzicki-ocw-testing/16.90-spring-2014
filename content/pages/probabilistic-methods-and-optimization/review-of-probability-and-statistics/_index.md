---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 3: Probabilistic Methods and Optimization'
parent_type: CourseSection
parent_uid: 487c3b15-ab67-d7c9-5cff-a6b147049d0c
title: 3.2 Review of Probability and Statistics
uid: 972a23bc-2208-f9b1-2895-30de24175e7d
---

*   {{% resource_link 3fd6bb8d-feaf-382c-e150-3c80bd79737e "\<Pre-requisite Material" %}}
*   {{% resource_link 972a23bc-2208-f9b1-2895-30de24175e7d "3.2.1Random Variables" %}}
*   {{% resource_link a3d2bfd5-90c2-ddaf-a1c4-73639ba4be5e "3.2.2Outcomes and Events" %}}
*   {{% resource_link 0c7b4a5a-66d4-c9d6-0849-150ad651b9c6 "3.2.3Distributions" %}}
*   {{% resource_link f11bfbbc-299e-7603-ff39-0e8071fc595e "3.2.4Expectations" %}}
*   {{% resource_link 48e310af-9f94-1a31-5e65-7482fc62956d "3.2.5The Central Limit Theorem" %}}
*   {{% resource_link a3d2bfd5-90c2-ddaf-a1c4-73639ba4be5e "\>Outcomes and Events" %}}

3.2.1 Random Variables
----------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.1" "#anchorMO31" %}}

Random variables arise frequently in engineering analyses. The utility of random variables is in being able to describe phenomena that exhibit uncertainty. For example, consider the assembly of a jet engine. To build the turbine we need turbine blades of a certain thickness. In classes thus far, you have treated the thickness of the blade as a fixed, deterministic variable. However, in the real world, the different blades used for building the turbine will have variations in thickness due to variations in the manufacturing process and material impurities. Thus, in reality, the thickness of the blade is a random variable subject to uncertainty, and we have to incorporate this variability in our analysis.

Types of Random Variables
-------------------------

In general, a random variable can be defined as a variable or parameter whose values are subject to variations due to chance. We will use capital letters to denote a random variable, to distingush it from a deterministic variable. For example, we denote the random variable that describes the thickness of an arbitrary blade by \\(X\\), whereas the thickness of a particular blade will be denoted by \\(x\\).

A **discrete random variable** is one that can take a countable number of different values. In other words, we can simply list all the possible values the random variable can take. In contrast to discrete random variables, **continuous random variables** can take an uncountable number of different values, i.e., they can be equal to any real number in an interval.

**Example 1:** Consider the inspection of rotor blades in the turbine of a jet engine. Suppose that the total number of rotor blades in the engine is \\(N\\). The outcome of a single inspection is recorded as the number of blades that must be replaced due to damage. A very simple example of a random variable would be the number of blades which are replaced after an inspection. We can denote this random variable by the letter \\(N\_ R\\), where the subscript \\(R\\) indicates that this is the number of blades to be replaced. What values do you think \\(N\_ R\\) can take ? Is \\(N\_ R\\) a discrete or a continuous random variable?

Functions of Random Variables
-----------------------------

We further recognize that not only can we have random variables, we can also have processes that depend on the random variables, in addition to depending on deterministic variables. For example, the thickness of the turbine blades affects the heat transfer across the blade and the flow pattern in the engine, and this affects the thrust the engine produces. We see that the thrust produced by the engine is also a random variable, which depends on the thickness(es) of the turbine blades. Therefore, if we denote the thrust produced by the engine as a random variable \\(Y\\), then we have,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[Y = Y(X)\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.1)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

**Example 2:** The airline is concerned about the cost of the inspection and repair of its engines. The cost to replace a single blade is \\(c\_ B\\). Also, if the number of replacements is greater than 5, the cost rises dramatically, since regulations dictate that a more thorough inspection must be performed. We will model this as an extra cost \\(c\_ D\\). Clearly the total cost of an inspection and repair is a random variable. We wil denote this random variable as \\(C(N\_ R;c\_ B,c\_ D)\\), recognizing its dependence on the random variable \\(N\_ R\\), and its dependence on the deterministic variables \\(c\_ B\\) and \\(c\_ D\\). We can also easily determine an expression for the total cost,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[C(N\_ R;c\_ B,c\_ D) = \\left\\{ \\begin{array}{ll} c\_ B N\_ R, & \\mbox{for } 0 \\leq N\_ R \\leq 5, \\\\\[0.1in\] c\_ B N\_ R + c\_ D, & \\mbox{for } 6 \\leq N\_ R \\leq N \\end{array}\\right.\\\]
{{< tdclose >}}
{{< tdopen >}}
(3.2)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\(\\{ 1, 2, 3, \\ldots , N \\}\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\{ N\\}\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} \\(\\{ 0, 1, 2, 3, \\ldots , N\\}\\){{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(\\{ 0, 1, 2, 3, \\ldots , N\_ R\\}\\){{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

\\(N\_ R\\) is a discrete random variable. The number of blades that need to be replaced can vary from no blades needing to be replaced to all blades needing to be replaced.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}} \\(Y(X)\\) is a random variable{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}} \\(Y(X)\\) can be either a deterministic or random variable{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}} \\(Y(X)\\) is a deterministic variable{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

\\(Y(X)\\) can clearly be a random variable. \\(Y(X)\\) can also be a deterministic variable, think of a function \\(Y\\) that always maps to a given number.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackPre-requisite Material ContinueOutcomes and Events