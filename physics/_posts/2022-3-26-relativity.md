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

Let us consider the movement of this particle at speed $v$ in the 'stationary' relative to the 'moving' reference frame which I will label $S$ and $S'$. Before we introduced any of these light speed rules, we would relate these systems by the following Galilean transformation

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

This leads to 

\begin{equation}
  v = - \frac{B}{A}
\end{equation}

