---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.7 Stiffness and Implicit Methods
parent_type: CourseSection
parent_uid: 935324e3-1ab2-cb57-9059-0ba1f034fcd5
title: 1.7 Stiffness and Implicit Methods
uid: 84564160-240c-f3be-e329-df42818d2eaa
---
<div class="navigation pagination">
<ul>
<li id="top_bck_btn"><a href="./resolveuid/b363c2d01814cf4c0cb36fe540840d02">&lt;<span>Newton-Raphson Implement Implicit Methods on Nonlinear Problems</span></a></li>
<li id="flp_btn_1"><a href="./resolveuid/935324e31ab2cb5790590ba1f034fcd5">1.7.1<span>Stiffness</span></a></li>
<li id="flp_btn_2"><a href="./resolveuid/900cc931acfbc43572d7f303ce81ef83">1.7.2<span>Spectral Condition Number</span></a></li>
<li id="flp_btn_3"><a href="./resolveuid/543e84063445482c020205c77ce31e71">1.7.3<span>Implicit Methods for Linear Systems of ODEs</span></a></li>
<li id="flp_btn_4"><a href="./resolveuid/b363c2d01814cf4c0cb36fe540840d02">1.7.4<span>Newton-Raphson Implement Implicit Methods on Nonlinear Problems</span></a></li>
<li id="flp_btn_5" class="button_selected"><a href="./resolveuid/84564160240cf3bee329df42818d2eaa">1.7.5<span>Apply Newton-Rhapson</span></a></li>
<li id="top_continue_btn"><a href="./resolveuid/67717326dffb74445162101fd9a9ec91">&gt;<span>Multi-Step Methods</span></a></li>
</ul>
</div>
<div class="self_assessment">
<h2 class="subhead">1.7.5 Apply Newton-Raphson</h2>
<p id="taglist"><a id="linearize" class="mo_link" href="./resolveuid/6018b2cc123ed80f52d919c7a1393c2e/#anchorMO14" title="MO1.4:  Approximate the behavior of a nonlinear equation with a linear one. ">Measurable Outcome 1.4</a>, <a id="explicitvsimplicit" class="mo_link" href="./resolveuid/6018b2cc123ed80f52d919c7a1393c2e/#anchorMO113" title="MO1.13:  Explain the differences and relative advantages between explicit and implicit methods to integrate systems of ordinary differential equations. ">Measurable Outcome 1.13</a>, <a id="newtonraphson" class="mo_link" href="./resolveuid/6018b2cc123ed80f52d919c7a1393c2e/#anchorMO114" title="MO1.14:  For nonlinear systems of equations, explain how a Newton-Raphson can be used in the solution of an implicit method. ">Measurable Outcome 1.14</a>, <a id="odeinteg" class="mo_link" href="./resolveuid/6018b2cc123ed80f52d919c7a1393c2e/#anchorMO119" title="MO1.19:  Recommend an appropriate ODE integration method based on the features of the problem being solved. ">Measurable Outcome 1.19</a></p>
<text> </text>
<p>&nbsp;</p>
<p>The value of \(u_1\) will be (3 significant digits):</p>
<div id="Q1_div" class="problem_question">
<p>Consider the system of ODEs \(\dot{u}_1 = \sin (u_2), \dot{u_2}=\cos (u_1)\) starting from an initial condition of \(u_1=0, u_2=\pi /2\). Implement trapezoidal integration with a timestep of \({\Delta t}=0.1.\) Ensure that the 2-norm of the residual is less than \(10^{-5}\) to ensure that the Newton-Rhapson iteration has converged. After one timestep</p>
<p>The value of \(u_1\) will be:</p>
<fieldset><legend class="visually-hidden">Exercise 1</legend>
<div class="choice"><label id="Q1_label"><span id="Q1_aria_status" tabindex="-1" class="visually-hidden"></span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q1_input" value="" onkeypress="numericTypedOrDropDownSelected(1)" class="problem_text_input" /><input type="hidden" id="Q1_ans" value="0.0998" /><input type="hidden" id="Q1_tolerance" value="1e-4" /><span id="Q1_normal_status" class="nostatus" aria-hidden="true"></span></label></div>
<p id="S1_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<p>The value of \(u_2\) will be:</p>
<div id="Q2_div" class="problem_question">
<div id="S1_div" class="problem_solution" tabindex="-1">&nbsp;</div>
<fieldset><legend class="visually-hidden">Exercise 2</legend>
<div class="choice"><label id="Q2_label"><span id="Q1_aria_status" tabindex="-1" class="visually-hidden"></span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q2_input" value="" onkeypress="numericTypedOrDropDownSelected(2)" class="problem_text_input" /><input type="hidden" id="Q2_ans" value="1.6705" /><input type="hidden" id="Q2_tolerance" value="1e-2" /><span id="Q2_normal_status" class="nostatus" aria-hidden="true"></span></label></div>
<p id="S2_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset>
<div class="action"><button id="Q1_button" onclick="checkAnswer({1: 'numerical', 2: 'numerical'})" class="problem_mo_button">Check</button><button id="Q1_button_show" onclick="showHideSolution({1: 'numerical', 2: 'numerical'}, 1, [1, 2])" class="problem_mo_button">Show Answer</button></div>
</div>
<p>&nbsp;</p>
<p>&nbsp;</p>
<div id="S2_div" class="problem_solution" tabindex="-1"><font color="blue">Answer: </font> <font color="blue"> </font>
<p>The following code can be used to solve the problem:</p>
<p>dt=0.1; u0=[0; pi/2]; w = u0; normR=100; while normR &gt; 1e-5 R = w - u0 - dt/2*([sin(w(2)); cos(w(1))] + [sin(u0(2)); cos(u0(1))]); J = [0 cos(w(2)); -sin(w(1)) 0]; dw = (eye(2)-dt/2*J)&shy;R; normR = norm(R);</p>
</div>
<p>&nbsp;</p>
</div>
<div class="navigation progress"><button id="bck_btn" type="button" onclick="window.location.assign('/courses/aeronautics-and-astronautics/16-90-computational-methods-in-aerospace-engineering-spring-2014/numerical-integration-of-ordinary-differential-equations/stiffness-and-implicit-methods/1690r-newton-raphson-implement-implicit-methods-on-nonlinear-problems');">Back<span>Newton-Raphson Implement Implicit Methods on Nonlinear Problems</span></button> <button id="continue_btn" type="button" onclick="window.location.assign('/courses/aeronautics-and-astronautics/16-90-computational-methods-in-aerospace-engineering-spring-2014/numerical-integration-of-ordinary-differential-equations/multi-step-methods');">Continue<span>Multi-Step Methods</span></button></div>