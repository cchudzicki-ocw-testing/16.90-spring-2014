---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 'Unit 3: Probabilistic Methods and Optimization'
parent_type: CourseSection
parent_uid: 487c3b15-ab67-d7c9-5cff-a6b147049d0c
title: 3.3 Monte Carlo Methods
uid: 2733fa33-374f-cb88-814c-413cb75b3483
---

*   {{% resource_link 48e310af-9f94-1a31-5e65-7482fc62956d "\<The Central Limit Theorem" %}}
*   {{% resource_link 2733fa33-374f-cb88-814c-413cb75b3483 "3.3.1Introduction" %}}
*   {{% resource_link e4ed709d-1333-d460-e932-cde246cff19f "3.3.2Monte Carlo Analysis" %}}
*   {{% resource_link 2ff49897-a168-59d4-5d17-feb89ff6fae6 "3.3.3Monte Carlo Example" %}}
*   {{% resource_link 91c4e401-232c-3823-cf38-1f612b323bb6 "3.3.4Inversion Method for Sampling" %}}
*   {{% resource_link e4ed709d-1333-d460-e932-cde246cff19f "\>Monte Carlo Analysis" %}}

3.3.1 Introduction
------------------

{{% resource_link 6018b2cc-123e-d80f-52d9-19c7a1393c2e "Measurable Outcome 3.3" "#anchorMO33" %}}

In the previous section, we reviewed some basic concepts from probability theory. We will now move on to applying some of those concepts, and developing probabilistic tools for engineering and design. Before we move ahead to the units introducing these tools, we will spend some time emphasizing why probabilistic analysis is important in engineering analysis and design.

Observe the two flow fields in Figure {{% resource_link b64f5d6e-363c-7c81-d034-d9b2ac56f6e7 "3.1" %}} below. Both represent numerical simulations of a flow past a cylinder at a Reynolds number of 100. The upper flow field only incorporates deterministic effects, in particular, the inlet flow velocity is treated as a fixed, deterministic variable. In contrast, the flow field in the lower plot, treats the inlet velocity as a random variable, i.e., the inlet flow velocity is modeled as the sum of the fixed velocity used to generate the first plot and, an additional random component that models noise.

{{< resource b64f5d6e-363c-7c81-d034-d9b2ac56f6e7 >}}

**Figure 3.1**: Vorticity field for flow past a cylinder: Upper: Deterministic inflow; Lower: Mean solution with random inflow. (Courtesy of Elsevier, Inc., [http://www.sciencedirect.com.](http://www.sciencedirect.com/) Used with permission. Source: Xiu, Dongbin, and George Em Karniadakis. "Modeling uncertainty in flow simulations via generalized polynomial chaos." _Journal of Computational Physics_ 187, no. 1 (2003): 137-167.)

Recall, your experiments in the wind tunnel, where you studied flow past an obstacle. Even though the experiment required a fixed inlet velocity, it is easy to see that enforcing a fixed velocity in the wind tunnel is not possible. Indeed, the actual inlet velocity in those experiments will be a random variable with the mean as the flow velocity we wish to study, plus some random noise. The figure above tells us that such random effects can have a substantial impact on the flow field.

Engineering systems operate in a world where many such random effects are encountered. Our analysis has to include such effects and our design has to be robust to handle such uncertainties. Engineering systems designed in this way are likely to be more reliable and provide better performance than the ones designed with a deterministic analysis.

BackThe Central Limit Theorem ContinueMonte Carlo Analysis