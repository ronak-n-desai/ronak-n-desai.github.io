---
layout: post
title: Marshmallow Launching
use_math: true
category: misc
---

If we have a heavy object of mass $M_o$, we can launch a ligher object (like a marshmallow) of mass $M_m$ by dropping the object onto a see-saw type of catapult depicted below

![image](https://user-images.githubusercontent.com/98538788/228967807-2d8e5a2d-676a-4455-bdab-8997203bf7ba.png)

Here, $M_o$ falls from a height $H_o$ into a cup of mass $M_c$ that is affixed to the end of a plank of length $L$ and mass $M_p$. The middle of the plank is elevated to a height $H_p$. After the heavy object falls into the cup, it will cause the plank to rotate downwards until the right end of the plank hits the ground. This will impart a velocity upwards into the marshmallow $v_m$ launching it up to a final height $H_m$. 

![image](https://user-images.githubusercontent.com/98538788/228967964-815353c3-ea23-49b4-ad26-82975437ee80.png)



## No Energy Loss

In the most naive approach, we assume all the the potential energy in the dropped object gets converted to the potential energy of the marshmallow. This would result in a marshmallow height of 

\begin{equation}
H = \frac{mO}{mM} h1
\end{equation}

## All Energy Converted to Rotational Energy

## Inelastic Collision

## In the 
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
  <label for="output1"><strong>Calculated Height (cm)</strong>: </label><span class="output" id="output1" style="color:blue"></span>
  </div>
  <div> 
  <label for="output2"><strong>Total Energy Conservation Height (cm)</strong>: </label><span class="output" id="output2" style="color:blue"></span>
  </div>
  <div> 
  <label for="output3"><strong>Other Height (cm)</strong>: </label><span class="output" id="output3" style="color:blue"></span>
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
              let mP = mP0.value/1000;
              let mO = mO0.value/1000;
              let mM = mM0.value/1000;
              let mC = mC0.value/1000;
              let h3 = h30.value/100;
              let h1 = h10.value/100;
              let l = l0.value/100;
              out1.innerHTML = Math.round(-3*(4*h3*h3-l*l)*100);
              out2.innerHTML = Math.round((mO/mM)*h1*100);
              out3.innerHTML = Math.round(-100*3*(4*h3*h3-l*l)*(-1*12*h1*h3*h3*mO*mO+24*h3*h3*h3*mO*mO+3*h1*l*l*mO*mO+2*h3*l*l*(3*mC*mC-3*mM*mM-mM*mP+mO*mP+mC*(6*mO+mP)))/(4*l*l*l*l*(3*mM+mP)*(3*mM+mP)));
       }
       
</script>
