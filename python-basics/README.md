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

Today: I tried to study this code and i noticed that when i change the a it doesn't in the graph cuz its automaticalley making the values of x and y axes much bigger, anyways i made this edit for position code 
plt.figure()
plt.plot(t, x)
plt.title("Position vs Time")
plt.xlabel("Time")
plt.ylabel("Position")
plt.xlim(0, 10)
plt.ylim(0, 200)
plt.show()
when i did this it worked very well.

Next project was about calculating velocity and position and i used this code (I STARTED USING C++ FROM NOW ON)

#include<iostream>
using namespace std;
int main()
{
	double a;
	double t;
	double v;
	double x;
	cout << "Enter the accelration:";
	cin >> a;
	for (t = 0; t <= 10; t++) here i made change about the addition system by changing it to t+=2 so i found the value were less accurate because the calculation have been done every 2 seconeds
	{
		v = a * t;
		x = 0.5 * a * t * t;

		cout <<"time: " << t
			 <<"velocity: " << v
			 << "position: " << x << endl;
		
	}
	return 0;

}


 After that I learned new thing about adiing the initial velocity to my coding system
 ## Code Evolution Notes

In the second version of the program, several improvements were made to make the motion simulation more realistic and flexible.

First, a new variable called `v0` was added to represent the initial velocity of the object. This allows the simulation to model objects that are already moving before acceleration begins, instead of assuming they always start from rest.

User input was also added for the initial velocity so the user can choose the starting speed manually during program execution.

The velocity formula was updated from:

v = a * t

to:

v = v0 + a * t

This change means the velocity now starts from the initial velocity and then increases or decreases depending on acceleration.

The position formula was updated from:

x = 0.5 * a * t^2

to:

x = v0 * t + 0.5 * a * t^2

This was done to include the distance traveled because of the initial velocity in addition to the distance caused by acceleration.

Overall, the first version represented an object starting from rest, while the second version represents a more general and realistic motion model where the object may already be moving before acceleration begins.
