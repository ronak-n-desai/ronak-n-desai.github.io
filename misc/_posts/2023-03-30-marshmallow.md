---
layout: post
title: Marshmallow Launching
use_math: true
category: misc
---

Using a heavy object of mass $M_o$, one can launch a lighter object (like a marshmallow) of mass $M_m$ by dropping the object onto a see-saw type of catapult depicted below

![image](https://user-images.githubusercontent.com/98538788/229964361-4cb95568-75ba-484b-87dc-0ab20dff5bd4.png)

Here, $M_o$ falls from a height $H_o$ into a cup of mass $M_c$ that is affixed to the end of a plank of length $L$ and mass $M_p$. The inclined plane that the plank sits on has a horizontal length $x$ and diagonal length $r$. After the heavy object falls into the cup, it will cause the plank to rotate downwards until the right end of the plank hits the ground. This will impart a velocity upwards and to the right into the marshmallow $v_p$ launching it up to a final height $H_m$. 

![image](https://user-images.githubusercontent.com/98538788/229964388-bef57f38-9579-4ab6-a979-7746d3dfc7f3.png)

# Predicting the Maximum Marshmallow Height

First, let's calculate some useful quantities. The angle of elevation of the inclined plane will be given by $\sin(\theta) = x/r$ and the height of the inclined plane will be $y = \sqrt{r^2 - x^2}$. Using this, the initial height of the right end of the plank will be $H_{p,i} = L \sin(\theta)$. With these considerations, the object $M_o$ will drop from a height $H_o$ to the plank at height $H_{p,i}$ where its gravitational potential energy is converted into kinetic energy. The velocity just before impact would be

\begin{equation}
v_o = \sqrt{2 g (H_o - H_{p,i})}
\end{equation}
Then, assume that the collision is perfectly inelastic so that the falling object sticks to the cup. The falling object will strike the plank at an angle $\theta$ off  the normal direction to the plank and the combined system will have a rotational inertia $I = (1/12) M_p L^2 + (M_o + M_c) (L-r)^2 + M_m r^2$. This results in the following equation for momentum conservation as 

\begin{equation}
  M_o v_o (L-r) \cos(\theta) = I_1 \omega_1
\end{equation}
so that the angular speed $\omega_1$ of the plank is

\begin{equation}
  \omega_1 = \frac{M_o v_o (L-r) \cos(\theta)}{I_1}
\end{equation}
Next, the imbalance of mass on the right and left hand side will add rotational kinetic energy as the difference in gravitational energy in the system. This can be expressed as

\begin{align}
&=(M_o+M_c) g H_{p,i} - M_p g (r-L/2) \sin(\theta) + \frac{1}{2} I_1 \omega_1^2 \\
&= M_m g H_{p,f} + M_p g (r-L/2) \sin(\phi) + \frac{1}{2} I_1 \omega_2^2 \nonumber
\end{align}
where $\phi$ is the new angle of elevation that the ramp makes and $H_{p,f} = L \sin(\phi)$ which can be rearranged for an increased angular speed $\omega_2$

\begin{equation}
  \omega_2 = \sqrt{\frac{(2 g ( (M_c + M_o) H_{p,i} - M_m H_{p,f} - M_p (r-L/2)(\sin(\theta) + \sin(\phi))}{I_2} + \omega_1^2}
\end{equation}
After the right end hits the floor, if plank rotates about its end, it will have a new rotational inertia $I_2 = M_p ((1/12)L^2 + (L-r)^2) + M_m L^2$. Assuming energy conservation leads to

\begin{equation}
\frac{1}{2} I_1 \omega_2^2 = \frac{1}{2} I_2 \omega_3^2 
\end{equation}
or

\begin{equation}
\omega_3 = \omega_2 \sqrt{\frac{I_1}{I_2}}
\end{equation}
Finally, the velocity of the left end of the plank just after the right end hits the ground is $v_p = L \omega_3$ which will be equal to the velocity of the marshmallow as it is also on the left end of the rod. The marshmallow will fly at this velocity into the air with a vertical component given by $v_p \cos(\phi)$ and reach a final height $H_m$ given by 

\begin{equation}
  H_m = \frac{(v_p \cos(\phi))^2}{2 g} + H_{p,f}
\end{equation}

# Python Analysis

# Marshmallow Height Calculator 
<form id="calc" oninput="calcheight()">
  <div>
  <label for="mM">Marshmallow Mass (g):</label>
  <input type="number" step="any" id="mM" name="mM" min="1" max="20" value="5.9" size="5">
  </div>
  <div>     
  <label for="mC">Cup Mass (g):</label>
  <input type="number" step="any" id="mC" name="mC" min="1" max="50" value="9.2" size="5">
  </div>   
  <div>     
  <label for="mP">Plank Mass (g):</label>
  <input type="number" step="any" id="mP" name="mP" min="1" max="500" value="87.7" size="5">
  </div>     
  <div>     
  <label for="mO">Object Mass (g):</label>
  <input type="number" step="any" id="mO" name="mO" min="1" max="1000" value="143.2" size="5">
  </div>    
  <div>     
  <label for="h3">Shim Angle Height (cm):</label>
  <input type="number" step="any" id="h3" name="h3" min="1" max="10" value="2.0" size="5">
  </div>     
  <div>     
  <label for="h1">Object Drop Height (cm):</label>
  <input type="number" step="any" id="h1" name="h1" min="10" max="200" value="50.0" size="5">
  </div>     
  <div>     
  <label for="l">Plank Length (cm):</label>
  <input type="number" step="any" id="l" name="l" min="10" max="100" value="61.5" size="5">
  </div>
  <div> 
  <label for="output1"><strong>Height Upper Bound (cm)</strong>: </label><span class="output" id="output1" style="color:blue"></span>
  </div>
  <div> 
  <label for="output2"><strong>Calculated Height 1 (cm)</strong>: </label><span class="output" id="output2" style="color:blue"></span>
  </div>
  <div> 
  <label for="output3"><strong>Calculated Height 2 (cm)</strong>: </label><span class="output" id="output3" style="color:blue"></span>
  </div>
</form>

<script>
       const mP0 = document.getElementById("mP");
       const mO0 = document.getElementById("mO");
       const mM0 = document.getElementById("mM");
       const mC0 = document.getElementById("mC");
       const h30 = document.getElementById("h3");
       const h10 = document.getElementById("h1");
       const l0 = document.getElementById("l");
       const out1 = document.getElementById("output1");
       const out2 = document.getElementById("output2");
       const out3 = document.getElementById("output3");
       
       function calcheight() {
              let mP = mP0.value/1000.0;
              let mO = mO0.value/1000.0;
              let mM = mM0.value/1000.0;
              let mC = mC0.value/1000.0;
              let h3 = h30.value/100.0;
              let h1 = h10.value/100.0;
              let l = l0.value/100.0;
              out1.innerHTML = Math.round((mO/mM)*h1*100);
              out2.innerHTML = Math.round(100*(-3*(4*h3*h3-l*l)*(-12*h1*h3**2*mO**2+24*h3**2*mO**2+3*h1*l**2*mO**2+2*h3*l**2*(3*mC**2-3*mM**2-mM*mP+mO*mP+mC*(6*mO+mP)))/(l**4*(3*mC+3*mM+3*mO+mP)**2)+2*h3));
              out3.innerHTML = Math.round(100*(-3*(4*h3*h3-l*l)*(-12*h1*h3**2*mO**2+24*h3**2*mO**2+3*h1*l**2*mO**2+2*h3*l**2*(3*mC**2-3*mM**2-mM*mP+mO*mP+mC*(6*mO+mP)))/(l**4*(3*mM+mP)*(3*mM+mP+3*mO+3*mC))+2*h3));
       }
       
</script>
