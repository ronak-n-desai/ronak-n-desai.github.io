---
layout: post
title: Intuition about Lasers
use_math: true
category: physics
---

Here we have an electron interacting with wave traveling in the $\hat{y}$ direction linearly polarized in the $\hat{x}$ direction

\begin{equation}
  \vec{E} = E_0 \sin(\omega t - k y) \hat{x}
\end{equation}

<p style="text-align:center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[ultra thick, red] (0,0) cos(1, 1) sin (2,2) cos(3, 1) sin(4, 0);
    \draw[<->] (0,-.2) -- node[anchor=north] {$\lambda$} (4,-.2);
    \draw[->] (5, 1) -- node[anchor = north] {$\vec{v}$} (8, 1);
    \draw[black, shading=ball, ball color=yellow] (10, 1) circle(.1) node[anchor = north] {$e^-$};
\end{tikzpicture}
</script>
</p>

where the speed of the wave is given by $c = f \lambda = \frac{\omega}{k}$. 

The acceleration will be given by 

\begin{equation}
  a_x = \frac{q E_0}{m} \sin(\omega t)
\end{equation}
  
 which can be integrated to yield
  
\begin{equation}
  v_x(t) = \frac{q E_0}{m \omega} \( \cos(\omega t) - 1 \)
\end{equation}
  
and from this we can arrive at some characteristic velocity, $v \sim \frac{q E_0}{m \omega}$ and if we divide this by $c$ we arrive at a dimensionless quantity called the quiver velocity
  
\begin{equation}
  a_0 \equiv \frac{v}{c} = \frac{q E_0}{m \omega c}
\end{equation}
  
The Intensity of the laser at Wright-Patterson AFB is around $I = 10^19 W/cm^2$ which corresponds to a peak electric field of around $E_0 = \sqrt{2I}{c \epsilon_0} \sim 10 TV/m$. Also, the laser has a wavelength of around $800$ nm which would result in quiver velocity around $a_0 \sim 1$ which would indicate that we need to account for relativistic effects even for these types of single-cycle pulses.




