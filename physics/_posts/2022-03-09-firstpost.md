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

\begin{center}
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[ultra thick, red] (0,0) cos(1, 1) sin (2,2) cos(3, 1) sin(4, 0);
    \draw[<->] (0,-.2) -- node[anchor=north] {$\lambda$} (4,-.2);
\end{tikzpicture}
</script>
\end{center}
  
\begin{center}
  \begin{tikzpicture}
    \draw[ultra thick, blue] (0,0) cos(1, 1) sin (2,2) cos(3, 1) sin(4, 0);
    \draw[<->] (0,-.2) -- node[anchor=north] {$\lambda$} (4,-.2);
\end{tikzpicture}
\end{center}

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




