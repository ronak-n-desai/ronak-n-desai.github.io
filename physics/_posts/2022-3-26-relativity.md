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

<p style="text-align:center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[ultra thick, red] (0,0) cos(1, 1) sin (2,2) cos(3, 1) sin(4, 0);
    \draw[<->] (0,-.2) -- node[anchor=north] {$\lambda$} (4,-.2);
    \draw[->] (5, 1) -- node[anchor = north] {$v$} (8, 1);
    \draw[black, shading=ball, ball color=yellow] (10, 1) circle(.1) node[anchor = north] {$q$};
\end{tikzpicture}
</script>
</p>
