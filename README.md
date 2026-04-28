# 1.Experimental verification of Signal sampling using various types
# Aim
Write a simple Python program for the construction and reconstruction of ideal, natural, and flattop sampling.
# Tools required
```
Google Colab
Python
NumPy Library
Matplotlib Library
Internet Connection
Computer / Laptop
```

# Program
```
import numpy as np
import matplotlib.pyplot as plt

fm = 5
fs = 50
t = np.linspace(0, 1, 1000)
ts = np.arange(0, 1, 1/fs)

x = np.sin(2 * np.pi * fm * t)

xs = np.sin(2 * np.pi * fm * ts)

flat_top = np.zeros_like(t)

for i in range(len(ts)-1):
    idx = np.where((t >= ts[i]) & (t < ts[i+1]))
    flat_top[idx] = xs[i]

plt.figure(figsize=(12,8))

plt.subplot(4,1,1)
plt.plot(t, x)
plt.title("Original Analog Signal")
plt.grid()

plt.subplot(4,1,2)
plt.stem(ts, xs, basefmt=" ")
plt.title("Ideal Sampling")
plt.grid()

plt.subplot(4,1,3)
plt.plot(t, x)
plt.stem(ts, xs, linefmt='r', markerfmt='ro', basefmt=" ")
plt.title("Natural Sampling")
plt.grid()

plt.subplot(4,1,4)
plt.plot(t, flat_top)
plt.title("Flat-top Sampling")
plt.grid()

plt.tight_layout()
plt.show()
```
# Output Waveform

<img width="1136" height="750" alt="Screenshot 2026-04-21 090547" src="https://github.com/user-attachments/assets/c5ddb4a9-8a25-40c1-943b-c0af42eb835e" />



# Results

A simple Python program for the construction and reconstruction of ideal, natural, and flattop sampling is simulated using COLAB.

