leraning python basics to increas my skils as an engineer

# Python for Engineering

Python can be used to model physical motion such as position and velocity.
This helps connect equations with real behavior.


#Apllication for notion of aircraft

import numpy as np
import matplotlib.pyplot as plt

# create time from 0 to 10 seconds
t = np.linspace(0, 10, 100)

# constant acceleration
a = 2

# calculate velocity
v = a * t

# calculate position
x = 0.5 * a * t**2

# acceleration array
acc = np.full_like(t, a)

# plot position
plt.figure()
plt.plot(t, x)
plt.title("Position vs Time")
plt.xlabel("Time")
plt.ylabel("Position")
plt.show()

# plot velocity
plt.figure()
plt.plot(t, v)
plt.title("Velocity vs Time")
plt.xlabel("Time")
plt.ylabel("Velocity")
plt.show()

# plot acceleration
plt.figure()
plt.plot(t, acc)
plt.title("Acceleration vs Time")
plt.xlabel("Time")
plt.ylabel("Acceleration")
plt.show()
