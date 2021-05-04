# Optimal-control-of-double-integrator-problem
![equation](http://www.sciweavers.org/tex2img.php?eq=1%2Bsin%28mc%5E2%29&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=)
[Double integrator ](https://en.wikipedia.org/wiki/Double_integrator) is a second order system relevant to many acceleration control problems like satellite attitude control. <br>
**Differential Equation**
$\ddot{x} =u(t)$

**State Space Equations**
$\dot{x_1} =x_2$
$\dot{x_2} =u$

**Cost Function**
$$
J = t_f ^2 + \int_0^{t_f}  u^{2}dt\,.
$$
Constrained by the state space equations.<br>
Boundary Conditions: <br>
$$x_1(0) = 10, x_2(0) = 0 $$
$$x_1 (t_f)  = 0, x_2(t_f) = 0 $$
<br> Objective: To minimize the the control effort as well as the operation time while guiding the system from initial state to the final state.
<br>
## Solution
$$H = u^2/2 + \lambda_1 x_2 + \lambda_2 u $$, where $\lambda_1$ and $\lambda_2$ are co-state variables.
<br>and 
$$\phi = t_f^2$$
1. Co-state equations:
<br> $\dot{\lambda_1} = - \frac{\partial H}{\partial x_1} = 0$
$\dot{\lambda_2} = - \frac{\partial H}{\partial x_2} = - \lambda_1$
2. Optimal control equation:
	$$\frac{\partial H}{\partial u} = 0 \implies u = - \lambda_2$$
3. State and costate equations: 
	 $\dot{x_1} =x_2$
	 $\dot{x_2} =u = - \lambda_2$
	 $\dot{\lambda_1} = 0$
	 $\dot{\lambda_2} =  - \lambda_1$
	 We have four simultaneous first order differential equations and four boundary conditions: 
	 $$x_1(0) = 10, x_2(0) = 0 $$
$$x_1 (t_f)  = 0, x_2(t_f) = 0 $$
where, $t_f$ is given by
 $$\frac{\partial \phi}{\partial t_f} = - H
\bigg\rvert_{t = t_f} $$

