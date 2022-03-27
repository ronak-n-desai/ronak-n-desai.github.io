---
layout: post
title: Relativity and E&M
use_math: true
category: physics
---

In an introductory Electricity and Magnetism Class, we learn that the magnetic force on a charge in a magnetic field is dependendent on its velocity. This is an issue because if we move into an inertial reference frame moving with the particle, the magnetic force will appear to vanish!

This cannot be true because we know that the magnetic force will change the particle's trajectory whether we are in a moving or stationary reference frame. Let's consider an example to gain some intuition of what might be going on. We have a stream of positive charges moving in a thin tube towards the right at a constant velocity $\vec{v}$. The linear charge density of the positive charges is given by $\lambda$ and the electrical current associated with this stream will be

\begin{equation}
  I = \frac{dq}{dt} = \frac{dq}{dx} \frac{dx}{dt} = \lambda v
\end{equation}

Now, let's consider a point charge $q$ a distance $d$ below the current stream.

<img src="/osunotebook/physics/images/charge_mag_field.gif" style="display:block; width: 100%;"/>
  
Here, the charge $q$ is moving at the same velocity as the charges in the current stream. First, let's consider the 'stationary' reference frame where the particle is seen to be moving. Here, the magnetic force is $F_B = q v B = q v \frac{\mu_0 \lambda v}{2 \pi d}$ and the electric force is $F_E = q \frac{\lambda}{2 \pi \epsilon_0 d}$. Using, $c^2 = \frac{1}{\mu_0 \epsilon_0}$, we get

\begin{equation}
  F \equiv F_E - F_B = \frac{q \lambda}{2 \pi \epsilon_0 d}(1 - \frac{v^2}{c^2})
\end{equation}

and let us define $\gamma \equiv \frac{1}{\sqrt{1 - \frac{v^2}{c^2}}}$ so that our expression for the net force on the charge is

\begin{equation}
  F = \frac{q \lambda}{2 \pi \epsilon_0 d} \frac{1}{\gamma^2}
\end{equation}

Next, let's consider the 'moving frame' where the particle appears to be at rest. In this case, the force is simply just

\begin{equation}
  F' = F_E = \frac{q \lambda}{2 \pi \epsilon_e d}
\end{equation}

So, it is clear that our understanding of introductory Electricity and Magnetism is not complete as we are computing two different forces in different inertial reference frames. Interestingly, these two expressions bear a striking similarity and only differ by $\gamma^2$. The $\gamma$ factor is actually very close to 1 when $v \ll c$, so it seems that this difference in force is neglible at ordinary speeds we would encounter on earth.

However, when we approach the speed of light (671,000,000 mph), the forces are no longer approximately equal. Additionally, when our velocity is greater than the speed of light, the formula entirely breaks down because we get a negative number in the square root!

So, in order to save physics from this catastrophe, let us propose some basic rules


1. Nothing can travel faster than the speed of light $c$
2. The speed of light $c$ is a constant, independent of the relative motion of the source.

This second rule might sound very unintuitive, but consider the following scenario. There is a light source on the ground shining forwards at speed $c$ and you are moving backwards at a speed $v$. Classically, you should observe the speed of the light particles at a speed $v+c$, but by rule 1, this would be impossible. So, we are forced to conclude that the speed of light must appear to be moving at $c$ in all inertial reference frames. Since speed is a distance divided by time, we must be willing to accept that length and time may no longer be experienced the same in different reference frames!

Let us consider the movement of this particle at speed $v$ as before. I will define two reference frames $S$ and $S'$ where $S'$ is moving with speed $v$ relative to $S$. Before we introduced any of these light speed rules, we would relate these systems by the following Galilean transformation

\begin{equation}
  x' = x - v t
\end{equation}

Now, let us propose a more general relation between $x'$ and $x$ and also allow for the time $t'$ to be different from $t$

<p>
\begin{align}
  x' &= A x + B t \\
  t' &= C x + D t 
\end{align}
</p>

We should expect $x'$ and $t'$ to be a linear function of $x$ and $t$ because what we consider primed and unprimed is arbitrary and these relations should hold if we expressed $x$ in terms of $x'$ and $t'$. If $x \propto x'^2$ for example, then $x' \propto x^2$ could not be true.

1. First, let's consider $S'$ to be moving exactly with the particle so that the measured position is always $x'=0$ which means $x = vt$

This leads to $ v = -\frac{B}{A}$ so that 

\begin{equation}
  x' = A (x - v t)
\end{equation}

2. Next, let's consider $S$ to be moving exactly with the particle so that the measured position is always $x=0$ so that $x'=-vt'$. Using this, we would get $t' = D t$ and $-v t' = B t$ so that $D = - \frac{B}{V}$. Using $v = - \frac{B}{A}$, we get $A = D$.

\begin{equation}
  t' = C x + A t
\end{equation}

3. Then, we can solve for $x = \frac{x'}{A} + v t$ but it should also have the same lorentz transformation as moving a speed $v$ to the left of the primed frame: $x = A(x' + v t')$. This means that 

\begin{equation}
  \frac{x}{A} - v t' = A(x - v t)
\end{equation}

Solving for $t'$, we get

<p>
\begin{align}
  t' &= \frac{x}{A v} - \frac{A}{v} (x - v t) \\
    &= A (\frac{x}{A^2 v} - \frac{x}{v} + t) \\
    &= A (t - \frac{x}{v}(1 - \frac{1}{A^2})
\end{align}
</p>

4. Now, all that remains is to solve for $A$. We can get this by imposing the requirement that the speed of light of light is observed to be the same in all reference frames. So, if we observe the particle moving at the speed of light in $S$, we will also measure it at the speed of light in $S'$. Mathematically, this means if $\frac{x}{t} = c$, then $\frac{x'}{t'} = c$ as well. Making these substitutions, we get $c t' = A (c t - v t)$ and $t' = A(t - \frac{c t}{v}(1 - \frac{1}{A^2}))$ and if we solve for $t'$ in both, we get

\begin{equation}
  t' = A(t - \frac{c t}{v}(1 - \frac{1}{A^2})) = A t (1 - \frac{v}{c})
\end{equation}

We can cancel $A t$ from all sides to get

\begin{equation}
  1 - \frac{c}{v} + \frac{c}{v A^2} = 1 - \frac{v}{c}
\end{equation}

and solving for $A$ gets us

\begin{equation}
  A = \frac{1}{\sqrt{1 - \frac{v^2}{c^2}}}
\end{equation}

which is exactly the $\gamma$ factor we discovered earlier! Putting this all together, we have

<p>
\begin{align}
  x' &= \gamma (x - v t) \\
  t' &= \gamma(t - \frac{v x}{c^2}) \\
  \gamma &= \frac{1}{\sqrt{1 - \frac{v^2}{c^2}}}
\end{align}
</p>

Which are the Lorentz Transformations that govern how time and space get shifted when we move near the speed of light. 

Let's consider what consequences this transformation has. Let's say we are trying to measure the length of a moving object with endpoints $x_2$ and $x_1$. Then, $L = x_2 - x_1$ will be the length in the reference frame to a stationary observer and $L_0' = x_2' - x_1'$ will be the length in the reference frame with the moving object (where the object appears to be stationary) where $x_1' = \gamma(x_1 - v t_1)$ and $x_2' = \gamma(x_2 - v_t_2)$. We call $L_0$ the proper length. Next, we need to measure the endpoints of the object simultaneously so that $t_1 = t_2 = t$. This leaves us with 

\begin{equation}
  L_0 = \gamma (x_2 - v t - x_1 + v t) = \gamma L
\end{equation}

or 

\begin{equation}
  L = \frac{L_0}{\gamma}
\end{equation

This shows that fast moving objects actually appear to be contracted by a factor of $\gamma$! 

Now, let's consider a moving object and lets consider the time measured by a stationary observer $\delta t = t_2 - t_1$ and an observer moving with the object $t_0 = t_2' - t_1'$. In the frame of the moving object, the object appears to be at rest, so that $x_2' = x_1' = x'$. Using the inverse transformation for time, we will get

\begin{equation}
  \delta t = \gamma (t_2' + \frac{v x'}{c^2} - t_1' - \frac{v x'}{c^2}) = \gamma t_0
\end{equation}

This shows that fast moving objects actually appear to be taking a longer time to travel some distance. Or in other words, time is dilated!

So, armed with the lorentz transfomation, we can now take another look at our problem with a charge traveling under the influence of the magnetic field. In our stationary reference frame, we see the charges in the current stream moving with speed $v$ and they should actually be seen to be contracted. In other words, $\lambda = \frac{\lambda'}{\gamma}$. Furthermore, we know that the force experienced in the moving frame should be 

\begin{equation}
  F' = \frac{d p_y'}{dt'} = \frac{d p_y}{dt} \frac{dt}{dt'}
\end{equation}

where $\frac{dt}{dt'} = \gamma$ due to time dilation and $p_y = p_y'$ because the motion is only in the x direction and should not affect the y direction momentum.

\begin{equation}
  F' = F \gamma
\end{equation}


References: https://www.feynmanlectures.caltech.edu/II_13.html
https://en.wikipedia.org/wiki/Length_contraction#:~:text=Length%20contraction%20can%20also%20be%20derived%20from%20time,multiple%20times%2C%20and%20is%20represented%20by%20the%20relation%3A

