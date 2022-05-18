---
layout: post
title: Shape Functions
use_math: true
category: research
---

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

<img src="/osunotebook/research/images/shape_functions.png" width="200" height="200"/>
