---
layout: post
title: Gaussian Beam Energy and Intensity
tags: python
published: true
category: research
---

```python
import numpy as np
import matplotlib.pyplot as plt
%matplotlib notebook
w0 = 1.5e-6
lbda = 8e-7
tau = 4e-15
zR = np.pi *w0**2 / lbda
c = 3e8
def I(z, r):
    return (w0/w(z))**2 * np.exp(-2*r**2 / w(z)**2) * env(z/c)
def w(z): 
    return w0 * np.sqrt(1 + (z/zR)**2)
def env(t):
    return np.sin(np.pi * t / (2*tau) + np.pi/2)**2

fig, ax = plt.subplots()
xmin = -50e-6
xmax = -xmin
ymin = -10*w0
ymax = -ymin
rs = np.linspace(ymin, ymax, 1000)
zs = np.linspace(xmin, xmax, 1000)
X, Y = np.meshgrid(zs, rs)
Z = I(X, Y)
ax.set_xlim([xmin, xmax])
ax.set_ylim([ymin, ymax])
ax.contourf(X, Y, I(X, Y), 100, cmap='hot')
ax.plot(zs, w(zs), color='blue', linestyle='dashed', label = 'w(z)')
ax.plot(zs, -w(zs), color = 'blue', linestyle='dashed')
ax.legend()
```
