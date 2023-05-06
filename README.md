Download Link: https://assignmentchef.com/product/solved-ee2703-tutorial6-part-2-the-laplace-transform
<br>
In this assignment, we will look at how to analyse “Linear Time-invariant Systems” with numerical tools in Python. LTI systems are what Electrical Engineers spend most of their time thinking about – linear circuit analysis or communication channels for example. In this assignment we will use mostly mechanical examples, but will move on to circuits in the next assignment.

All the problems will be in “continuous time” and will use Laplace Transforms. Python has a Signals toolbox which is very useful and complete. In this assignment, we will explore the following commands:

<table width="298">

 <tbody>

  <tr>

   <td width="92">Command</td>

   <td width="205">Description</td>

  </tr>

  <tr>

   <td width="92">poly1d</td>

   <td width="205">Defines polynomials&gt;&gt;&gt; p = poly1d([1, 2, 3])&gt;&gt;&gt; print poly1d(p)1<em>x</em><sup>2</sup>+2<em>x</em>+3</td>

  </tr>

  <tr>

   <td width="92">polyadd</td>

   <td width="205">&gt;&gt;&gt; polyadd([1, 2], [9, 5, 4]) array([9, 6, 6])</td>

  </tr>

  <tr>

   <td width="92">polymul</td>

   <td width="205">&gt;&gt;&gt; polymul([1,2],[9,5,4]) array([ 9, 23, 14, 8])</td>

  </tr>

  <tr>

   <td width="92"> </td>

   <td width="205">Using poly1d objects:&gt;&gt;&gt; p1 = np.poly1d([1, 2])&gt;&gt;&gt; p2 = np.poly1d([9, 5, 4])&gt;&gt;&gt; print p1 + 2&gt;&gt;&gt; print p229 x + 5 x + 4&gt;&gt;&gt; print p1 + p229 x + 6 x + 6</td>

  </tr>

  <tr>

   <td width="92">signal toolbox</td>

   <td width="205">import scipy.signal as sp</td>

  </tr>

  <tr>

   <td width="92">sp.lti</td>

   <td width="205">&gt;&gt;&gt; s=sp.lti(Num,Den) defines a transfer function&gt;&gt;&gt; H=sp.lti([1,2,1],[1,2,1,1])&gt;&gt;&gt; w,S,phi=H.bode()&gt;&gt;&gt; subplot(2,1,1)&gt;&gt;&gt; semilogx(w,S)&gt;&gt;&gt; subplot(2,1,2)&gt;&gt;&gt; semilogx(w,phi)</td>

  </tr>

  <tr>

   <td width="92">sp.impulse</td>

   <td width="205">&gt;&gt;&gt; t,x=sp.impulse(H,None, linspace(0,10,101))Computes the impulse response of the transfer function&gt;&gt;&gt; plot(t,x)</td>

  </tr>

  <tr>

   <td width="92">Command</td>

   <td width="205">Description</td>

  </tr>

  <tr>

   <td width="92">sp.lsim</td>

   <td width="205">&gt;&gt;&gt; t=linspace(0,10,101)&gt;&gt;&gt; u=sin(t)&gt;&gt;&gt; t,y,svec=sp.lsim(H,u,t)This simulates y=convolution of u and h</td>

  </tr>

 </tbody>

</table>

<h2>1      The Assignment</h2>

<ol>

 <li>The Laplace transform of <em>f</em>(<em>t</em>)= cos(1<em>.</em>5<em>t</em>)<em>e</em><sup>−0</sup><em><sup>.</sup></em><sup>5<em>t</em></sup><em>u</em><sub>0</sub>(<em>t</em>) is given by</li>

</ol>

<em>s</em>+0<em>.</em>5

<em>F</em>(<em>s</em>)=

(<em>s</em>+0<em>.</em>5)<sup>2</sup>+2<em>.</em>25

Solve for the time response of a spring satisfying

<em>x</em>¨+2<em>.</em>25<em>x </em>= <em>f</em>(<em>t</em>)

with <em>x</em>(0)= 0 and ˙<em>x </em>= 0 for <em>t </em>going from zero to 50 seconds. Use system.impulse to do the computation

<ol start="2">

 <li>Solve the above problem with a much smaller decay:</li>

</ol>

<table>

 <tbody>

  <tr>

   <td width="216"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<em>f</em>(<em>t</em>)= cos(1<em>.</em>5<em>t</em>)<em>e</em><sup>−0</sup><em><sup>.</sup></em><sup>05<em>t</em></sup><em>u</em><sub>0</sub>(<em>t</em>)

<ol start="3">

 <li>Consider the problem to be an LTI system. <em>f</em>(<em>t</em>) is the input, and <em>x</em>(<em>t</em>) is the output. Obtain the system transfer function <em>X</em>(<em>s</em>)<em>/</em><em>F</em>(<em>s</em>). Now use <em>lsim </em>to simulate the problem. In a for loop, vary the frequency of the cosine in <em>f</em>(<em>t</em>) from 1<em>.</em>4 to 1<em>.</em>6 in steps of 0<em>.</em>05 keeping the exponent as exp(−0<em>.</em>05<em>t</em>) and plot the resulting responses. Explain what is happening.</li>

 <li>Solve for a coupled spring problem:</li>

</ol>

<em>x</em>¨+(<em>x</em>−<em>y</em>) = 0 <em>y</em>¨+2(<em>y</em>−<em>x</em>) = 0

where the initial condition is <em>x</em>(0)= 1, ˙<em>x</em>(0)= <em>y</em>(0)= <em>y</em>˙(0)= 0. Substitute for <em>y </em>from the first equation into the second and get a fourth order equation. Solve for its time evolution, and from it obtain <em>x</em>(<em>t</em>) and <em>y</em>(<em>t</em>) for 0 ≤ <em>t </em>≤ 20.

<ol start="5">

 <li>Obtain the magnitude and phase response of the Steady State Transfer function of the following two-port network.</li>

 <li>Consider the problem in Q5. suppose the input signal <em>v<sub>i</sub></em>(<em>t</em>) is given by</li>

</ol>

<em>v<sub>i</sub></em>

Obtain the output voltage <em>v</em><sub>0</sub>(<em>t</em>) by defining the transfer function as a system and obtaining the output using <em>signal.lsim</em>.

How do you explain the output signal for 0 <em>&lt; t </em><em>&lt; </em>30<em>µs</em>? Can you explain the long term response on the msec timescale?

Note: You need to capture the fast variation, which means your time step should be smaller than 10<sup>−6</sup>. Yet you need to see the slow time, which means you must simulate till about 10 msec. Use an appropriate time vector.

Note: Since the network is resistive, the current at <em>t </em>= 0<sup>− </sup>will have decayed to zero, which gives you your initial condition.