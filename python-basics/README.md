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


## Negative Acceleration and Turning Point

In this stage, the motion simulation was tested using negative acceleration to represent deceleration.

The acceleration was set to a negative value while keeping a positive initial velocity:

a = -10  
v0 = 50

This caused the object's velocity to decrease over time instead of increasing.

The simulation showed that velocity gradually dropped until it reached zero at:

t = 5

At this exact moment, the object reached its maximum position:

Position = 125

This point represents the farthest distance traveled before the object stopped.

After this moment, the velocity became negative, which means the object reversed direction and started moving backward.

This demonstrated an important physical concept:

When velocity becomes zero, it can indicate a turning point rather than the end of motion.

The simulation also showed that:

Positive velocity means motion in the forward direction.  
Negative velocity means motion in the opposite direction.

This behavior is similar to projectile motion, where an object slows down while rising, stops at the highest point, then reverses direction and falls back down.

Overall, this experiment introduced the concept of deceleration, direction reversal, and turning points in motion simulation.

This was done to include the distance traveled because of the initial velocity in addition to the distance caused by acceleration.

Overall, the first version represented an object starting from rest, while the second version represents a more general and realistic motion model where the object may already be moving before acceleration begins.

## Programming Progress – Introduction to if Statement

In this step, conditional logic was introduced into the simulation using the if statement.

The program was updated to check when the velocity becomes zero using:

if (v == 0)

When this condition is met, the program prints a message indicating that the object has stopped.

This is the first step in transforming the program from simple calculations into a system that can make decisions based on computed values.

This improvement allows the simulation to detect important physical events instead of only printing numerical results.


## Programming Progress – Using break to Stop Simulation

In this step, the simulation was improved by adding control flow using the break statement.

Previously, the loop continued running even after the object stopped and began moving in the opposite direction.

To fix this, a condition was added:

if (v == 0)

When the velocity reaches zero, the program now prints a message and immediately exits the loop using:

break;

This allows the simulation to stop exactly at the moment the object reaches its turning point.

This change improves the realism of the simulation and prevents unnecessary calculations after the object stops.


## Programming Progress – Detecting Direction Reversal (Velocity Sign Change)

In this update, the motion simulation was improved by adding logic to detect when the object changes direction.

A new variable `prev_v` was introduced to store the previous velocity value. This allows comparison between consecutive velocity values.

The condition:

if (prev_v > 0 && v < 0)

was used to detect when velocity changes from positive to negative, indicating that the object has passed its turning point and started moving in the opposite direction.

## Programming Progress – From Basic Simulation to Intelligent Motion Model

The motion simulation evolved significantly through multiple stages of development.

Initially, the program performed simple calculations using constant acceleration and assumed the object started from rest.

The model was then improved by introducing initial velocity (v0), making the simulation more realistic.

Next, time step control was refined (from larger steps to smaller ones) to improve accuracy.

Conditional logic was introduced using if statements to detect important events such as when velocity becomes zero.

The break statement was added to stop the simulation at meaningful moments, such as the stopping point.

Further improvements included tracking previous velocity (prev_v) to detect direction reversal by checking when velocity changes from positive to negative.

Finally, the simulation was enhanced to track the maximum position (max_x), allowing the program to determine the highest point reached during motion.

Overall, the program evolved from simple numerical output to a system capable of analyzing motion behavior and making decisions based on physical conditions.
When this condition is satisfied, the program prints a message and stops execution using `break`.

This improves the simulation by identifying not only when the object stops, but also when it reverses direction.

## Programming Progress – Correct Placement of Derived Calculations

In this update, the calculation of derived variables was organized correctly within the program flow.

The variable `t_stop` was computed using the formula:

t_stop = -v0 / a

This calculation was placed after user input (cin statements) because it depends on values provided by the user.

This demonstrates the importance of execution order in C++, where variables that depend on input data must be calculated only after those inputs are available.

The program structure now follows a logical sequence: input → computation → output.

## Programming Progress – First Function and Stopping Time Calculation

In this step, the program was improved by introducing the first C++ function.

A function called `calculateStoppingTime()` was created to calculate the stopping time using the formula:

t_stop = -v0 / a

Instead of writing the equation directly inside `main()`, the calculation was moved into a separate function.

This made the code cleaner, more organized, and easier to understand.

I also learned that calculations depending on user input must be placed after `cin`, because values like acceleration and initial velocity must be entered first before they can be used.

This step introduced better code structure and the concept of reusable functions.
