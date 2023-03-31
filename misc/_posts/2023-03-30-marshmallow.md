---
layout: post
title: Marshmallow Launching
use_math: true
category: misc
---

Using a heavy object of mass $M_o$, one can launch a lighter object (like a marshmallow) of mass $M_m$ by dropping the object onto a see-saw type of catapult depicted below

![image](https://user-images.githubusercontent.com/98538788/228967807-2d8e5a2d-676a-4455-bdab-8997203bf7ba.png)

Here, $M_o$ falls from a height $H_o$ into a cup of mass $M_c$ that is affixed to the end of a plank of length $L$ and mass $M_p$. The middle of the plank is elevated to a height $H_p$. After the heavy object falls into the cup, it will cause the plank to rotate downwards until the right end of the plank hits the ground. This will impart a velocity upwards into the marshmallow $v_m$ launching it up to a final height $H_m$. 

![image](https://user-images.githubusercontent.com/98538788/228967964-815353c3-ea23-49b4-ad26-82975437ee80.png)

# Obtaining an Upper Limit

Due to conservation of energy, we know that the amount of gravitational potential energy of the marshmallow at its peak height must be less than the amount of potential energy of the object at its initial height. Using this, we can predict the maximum possible height of the marshmallow as 

\begin{equation}
H_m = \frac{M_o}{M_m} H_o
\end{equation}
however, the actual height should be much less than this due to energy being transferred to the plank as well as being lost through collisions.

# Predicting the Maximum Marshmallow Height

First, the object will drop from a height $H_o$ to the plank at height $2 H_p$ where its gravitational potential energy is converted into kinetic energy. The velocity just before impact would be

\begin{equation}
v_o = \sqrt{2 g (H_o - 2 H_p)}
\end{equation}
Then, assume that the collision is perfectly inelastic so that the falling object sticks to the cup. The falling object will strike the plank at an angle $\theta$ off the normal given by $\sin(\theta) = \frac{2 H_p}{H_o}$ and the combined system will have a rotational inertia $I = \frac{1}{12} M_p L^2 + (M_o + M_m + M_c) (L/2)^2$. This results in the following equation for momentum conservation as 

\begin{equation}
  M_o v_o (L/2) \cos(\theta) = I \omega_1
\end{equation}
so that the angular speed $\omega_1$ of the plank is

\begin{equation}
  \omega_1 = \frac{M_o v_o L \cos(\theta)}{2 I}
\end{equation}
Next, the imbalance of mass on the right and left hand side will add rotational kinetic energy as the difference in gravitational energy in the system. This can be expressed as

\begin{equation}
M_m g (2 H_p) + \frac{1}{2} I \omega_1^2 = (M_o+M_c) g (2 H_p) + \frac{1}{2} I \omega_2^2 
\end{equation}
which can be rearranged for an increased angular speed $\omega_2$

\begin{equation}
  \omega_2 = \sqrt{\frac{2 g (2 H_p) (M_c + M_o - M_m)}{I} + \omega_1^2}
\end{equation}
After the right end hits the floor, the plank will begin to rotate about its end with a new rotational inertia $I' = \frac{1}{3} M_p L^2 + M_m L^2$. Here, the physics gets complicated and assuming energy conservation, one can get

\begin{equation}
\omega_3 = \omega_2 \sqrt{\frac{I}{I'}}
\end{equation}
Finally, the velocity of the left end of the plank just after the right end hits the ground is $v_p = L \omega_3$ which will be equal to the velocity of the marshmallow as it is also on the left end of the rod. The marshmallow will fly at this velocity into the air with a vertical component given by $v_m = v_p \cos(\theta)$ and reach a final height $H_m$ given by 

\begin{equation}
  H_m = \frac{(v_p \cos(\theta))^2}{2 g} + 2 H_p
\end{equation}

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
  <label for="output3"><strong>Calculated Height (cm)</strong>: </label><span class="output" id="output3" style="color:blue"></span>
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
              out3.innerHTML = Math.round(-100*3*(4*h3*h3-l*l)*(-12*h1*h3**2*mO**2+24*h3**2*mO**2+3*h1*l**2*mO**2+2*h3*l**2*(3*mC**2-3*mM**2-mM*mP+mO*mP+mC*(6*mO+mP)))/(l**4*(3*mM+mP)*(3*mM+mP+3*mO+3*mC))+2*h3);
       }
       
</script>
