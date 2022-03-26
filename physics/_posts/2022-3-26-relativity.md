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

<img src="/osunotebook/physics/images/charge_mag_field.gif" style="display:block; width: 90%;"/>
  
Here, the charge $q$ is moving at the same velocity as the charges in the current stream. First, let's consider the 'stationary' reference frame where the particle is seen to be moving. Here, the magnetic force is $F_B = q v B = q v \frac{\mu_0 \lambda v}{2 \pi d}$ and the electric force is $F_E = q \frac{\lambda}{2 \pi \epsilon_0 d}$. Using, $c^2 = \frac{1}{\mu_0 \epsilon_0}$, we get

\begin{equation}
  F \equiv F_E - F_B = \frac{q \lambda}{2 \pi \epsilon_0 d}(1 - \frac{v^2}{c^2})
\end{equation}

and let us define $\gamma \equiv \frac{1}{\sqrt{1 - \frac{v^2}{c^2}}}$ so that our expression for the net force on the charge is

\begin{equation}
  F = \frac{q \lambda}{2 \pi \epsilon_0 d \gamma^2}
\end{equation}
