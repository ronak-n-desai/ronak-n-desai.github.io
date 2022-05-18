---
layout: post
title: Shape Functions
use_math: true
category: research
---

In PIC simulations, we are solving for quantities on a discrete grid. So, for example, if we are looking at charge, it would seem that all the charge would be concentrated in point charges. However, this is not capturing the true physical picture of a simulation, because each of these simulation charges are macroparticles and represent many, many real particles. It would make more sense to smooth these charges out into some type of shape function that represents the charge density. Closer to the macroparticle location, we shold expect a higher value of the shape function and further away, it should be lower.

So, to describe this picture with macroparticles being described as point charges, the shape function would be a dirac $\delta$ function. A better formalism would be to smear out the charge uniformly half a cell in each direction. This is the simplest shape function called the **Top-Hat** as is defined as follows:

\begin{equation}
  th(x) \equiv& 
  \begin{cases}
  1 &\mbox{if} & \lvert x \rvert \leq 0.5 \\
  0 &\mbox{otherwise} &
  \end{cases}
\end{equation}

Here, the total area under the curve is 1, which is something that needs to be enforce of all shape functions in order to ensure that we are preserving the same number of particles. Previously, I mentioned that it would be a good idea to have a shape function gives a higher weighting to points closer to the location of the macroparticle. The most simple way to implement this would be a triangle, which we could define mathematically as

\begin{equation}
  tr(x) \equiv& 
  \begin{cases}
  1 + x &\mbox{if} & -1 < x < 0 \\
  1 - x &\mbox{if} & 0 < x < 1 \\
  0 & \mbox{otherwise} &
  \end{cases}
\end{equation}

```python
import numpy as np
import matplotlib.pyplot as plt
xs = np.arange(-5, 5, 0.01)
dx = xs[1]-xs[0]
tophat = lambda x: 1 if abs(x) <= 0.5 else 0
y_tophat = np.piecewise(xs, [abs(xs) <= 0.5, abs(xs) > 0.5], [1, 0])
y_triangle = np.convolve(y_tophat, y_tophat, 'same') * dx
y_spline = np.convolve(y_triangle, y_triangle, 'same') * dx
plt.figure()
plt.xlim([-2 , 2])
plt.plot(xs, y_tophat, label='top hat')
plt.plot(xs, y_triangle, label='triangle')
plt.plot(xs, y_spline, label='spline')
plt.legend()
plt.show()
```

<img src="/osunotebook/research/images/shape_functions.png" style="display:block; width: 100%;"/>
