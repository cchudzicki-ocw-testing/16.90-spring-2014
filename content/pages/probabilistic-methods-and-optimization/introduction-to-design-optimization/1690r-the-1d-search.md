---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 3.6 Introduction to Design Optimization
parent_type: CourseSection
parent_uid: 6f317b0d-95c1-d32c-f178-c9fdbae632d2
title: 3.6 Introduction to Design Optimization
uid: 3cde12b3-c306-b87c-973f-5af561f4875f
---
<div class="navigation pagination"><li id="top_bck_btn"><a href="./resolveuid/c0e755e748fd33db478288b736e0381c"><<span>Finite Difference Methods</span></a></li><li id="flp_btn_1"><a href="./resolveuid/6f317b0d95c1d32cf178c9fdbae632d2">3.6.1<span>Design Optimization</span></a></li><li id="flp_btn_2"><a href="./resolveuid/1d39506a8ae7400e107dfe048008e5c2">3.6.2<span>Gradient Based Optimization</span></a></li><li id="flp_btn_3"><a href="./resolveuid/da1cf6178af153b14d4a177f24979948">3.6.3<span>Unconstrained Gradient-Based Optimization Methods</span></a></li><li id="flp_btn_4"><a href="./resolveuid/c0e755e748fd33db478288b736e0381c">3.6.4<span>Finite Difference Methods</span></a></li><li id="flp_btn_5" class="button_selected"><a href="./resolveuid/3cde12b3c306b87c973f5af561f4875f">3.6.5<span>The 1d Search</span></a></li></div><div class="self_assessment">
<h2 class="subhead">3.6.5 The 1D Search</h2>
<p id="taglist">
<a id="optimizationtechniques" class="mo_link" href="./resolveuid/6018b2cc123ed80f52d919c7a1393c2e/#anchorMO317" title="MO3.17:  Describe the steepest descent, conjugate gradient, and the Newton method for optimization of multivariate functions, and apply these optimization techniques to simple unconstrained design problems. ">Measurable Outcome 3.17</a>
</p>
<text>
</text><p>
</p>
<p>
In this section, we detail how to compute an appropriate step size for a typical optimization step. This is referred to as a 1D line search, since we are searching for the minimum along the search direction. One common approach is to use polynomial interpolation to first construct an approximation for the objective function in the search direction. </p>
<p>
Consider that at some point, \(x^0\), have \(\nabla J = [ 1 \  2]^ T\). The steepest descent direction is then \(S = -\nabla J = [-1 \  -2]^ T\). To compute \(\alpha\), we sample at three points along the direction \(S\), i.e., we compute the objective function value \(J(x^0+\alpha S)\). We find<br />\(\alpha =0\), \(J=10\) <br />\(\alpha =1\), \(J=6\) <br />\(\alpha =2\), \(J=8\) </p>
<p>
Also, we know that for \(\alpha =0\), </p>
<table id="a0000000493" class="equation" width="100%" cellspacing="0" cellpadding="7" style="table-layout:auto;border-style:hidden">
<tr>
<td class="equation" style="width:80%;vertical-align:middle;text-align:center;border-style:hidden">\[\frac{dJ}{d\alpha } = \nabla J^ T S = -5\]</td>
<td class="eqnnum" style="width:20%;vertical-align:middle;text-align:left;border-style:hidden">(3.78)</td>
</tr>
</table>
<p>
Using these four pieces of data, we can fit a cubic polynomial to describe \(J(\alpha )\): </p>
<table id="a0000000494" class="equation" width="100%" cellspacing="0" cellpadding="7" style="table-layout:auto;border-style:hidden">
<tr>
<td class="equation" style="width:80%;vertical-align:middle;text-align:center;border-style:hidden">\[J(\alpha ) = c_1 + c_2\alpha + c_3\alpha ^2 + c_4\alpha ^3\]</td>
<td class="eqnnum" style="width:20%;vertical-align:middle;text-align:left;border-style:hidden">(3.79)</td>
</tr>
</table>
<p>
We solve for the coefficients by setting up the system </p>
<table id="a0000000495" class="equation" width="100%" cellspacing="0" cellpadding="7" style="table-layout:auto;border-style:hidden">
<tr>
<td class="equation" style="width:80%;vertical-align:middle;text-align:center;border-style:hidden">\[\left[\begin{array}{c c c c} 1 &amp;  0 &amp;  0 &amp;  0 \\ 0 &amp;  1 &amp;  0 &amp;  0 \\ 1 &amp;  1 &amp;  1 &amp;  1\\ 1 &amp;  2 &amp;  4 &amp;  8\\ \end{array}\right] \left[\begin{array}{c} c_1 \\ c_2 \\ c_3 \\ c_4 \end{array}\right] =\left[\begin{array}{c} 10 \\ -5 \\ 6 \\ 8 \end{array}\right],\]</td>
<td class="eqnnum" style="width:20%;vertical-align:middle;text-align:left;border-style:hidden">(3.80)</td>
</tr>
</table>
<p>
 giving solution \(c_1 = 10\), \(c_2 = -5\), \(c_3=0\), \(c_4=1\). </p>
<p>
So we approximate \(J\) as \(J(\alpha ) = 10-5\alpha + \alpha ^3\). </p>
<p>
Now we want to find the \(\alpha\) that minimizes \(J(\alpha )\), i.e., set \(-5+3\alpha ^2=0\), giving \(\alpha =\sqrt {\frac{5}{3}}=1.291\). </p>
<p>
This is the value of \(\alpha\) that minimizes \(J(x+\alpha S)\) in the given direction \(S\). </p>
<p>
Consider that at some point, \(x^0\), we have \(\nabla J=[1 3]^ T\). The steepest descent direction is then \(S=-\nabla J = [-1 -3]^ T\). To compute a good step size \(\alpha\), we sample at three points along the direction \(S\), i.e., we compute the objective function value \(J(x^0 + \alpha S)\) for three different values of \(\alpha\). Let's say that we find:<br /></p>
<p>
\(\alpha =0, J=8\)<br />\(\alpha =1, J=6\)<br />\(\alpha =2, J=8\) </p>
<p>
Fit a cubic equation to approximate \(J(\alpha )\), and find the value of \(\alpha\) that minimizes this cubic equation. </p>
<p>
<div id="Q1_div" class="problem_question"><p>
The resulting value of \(\alpha\) (to three decimals) that approximately minimizes \(J(x+\alpha S)\) in the given direction \(S\) is: </p><fieldset><legend class="visually-hidden">Exercise 1</legend><div class="choice"><label id="Q1_label"><span id="Q1_aria_status" tabindex="-1" class="visually-hidden"></span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q1_input" value="" onkeypress="numericTypedOrDropDownSelected(1)" class="problem_text_input" /><input type="hidden" id="Q1_ans" value="0.603" /><input type="hidden" id="Q1_tolerance" value="0.001" /><span id="Q1_normal_status" class="nostatus" aria-hidden="true"></span></label></div><p id="S1_ans" tabindex="-1" class="problem_answer"></p></fieldset><div class="action"><button id="Q1_button" onclick="checkAnswer({1: 'numerical'})" class="problem_mo_button">Check</button><button id="Q1_button_show" onclick="showHideSolution({1: 'numerical'}, 1, [1])" class="problem_mo_button">Show Answer</button></div></div><div id="S1_div" class="problem_solution" tabindex="-1">
</div></p>
</div><div class="navigation progress"><button id="bck_btn" type="button" onclick="window.location.assign('/courses/aeronautics-and-astronautics/16-90-computational-methods-in-aerospace-engineering-spring-2014/probabilistic-methods-and-optimization/introduction-to-design-optimization/1690r-finite-difference-methods');">Back<span>Finite Difference Methods</span></button> </div>