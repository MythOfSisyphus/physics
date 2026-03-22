# Problem Set 1: Kinematics

## Problems:

- [[#Reasoning for Problem 1. Car and Bicycle Rider]]
- [[#Reasoning for Problem 2. Elevator Trip]]
- [[#Reasoning for Problem 3. Rocket Launch]]
- [[#Reasoning for Problem 4. Throw and Catch]]
- [[#Reasoning for Problem 5. Vertical Collision]]

---
## Reasoning for Problem 1. Car and Bicycle Rider

Car's acceleration $a_c$ is given by,
$$a_c = \begin{cases}
0 & 0 < t < t_1 \\
-c(t - t_1) & t_1 < t < t_2
\end{cases}$$
Acceleration is constant in the interval $t \in (0, t_1)$ therefore its velocity in this interval given by, $v_c(t) = v_0$ and distance travelled by car in this interval is just $x_c(t) = v_0 t$.

After time $t = t_1$, we see that acceleration isn't constant, but we know that change in velocity is acceleration, using this we get,

$$\begin{align*}
\frac{dv}{dt} &= a_c(t) \\
\int_{v_0}^{v_c(t)} dv &= \int_{t_1}^{t} - c (t' - t_1) \, dt' \\
v_c(t) - v_0 &= - \frac{c}{2} (t' - t_1) \bigg{|}_{t_1}^{t} \\
v_c(t) &= v_0 - \frac{c}{2} (t - t_1)^2.
\end{align*}$$

For $x_c(t)$, using the same lines of reasoning we see that,
$$\begin{align*}
\frac{dx}{dt} &= v_c(t) \\
\int_{v_0t_1}^{x_c(t)} dx &= \int_{t_1}^{t} \left(v_0 - \frac{c}{2} (t' - t_1)^2 \right) \, dt' \\
x_c(t) - v_0 t &= \left( v_0 t' - \frac{c}{6} (t' - t_1)^3 \right) \bigg{|}_{t_1}^{t} \\
x_c(t) - v_0 t_1 &= v_0 t - \frac{c}{6} (t - t_1)^3 - (v_0 t_1 - 0) \\
x_c(t) &= v_0 t - \frac{c}{6} (t - t_1)^3.
\end{align*}$$

Thus, for **(a)**:
$$v_c(t) = \begin{cases}
v_0 & 0 < t < t_1 \\
v_0 - \frac{c}{2} (t - t_1)^2 & t_1 < t < t_2
\end{cases}$$

and

$$x_c(t) = \begin{cases}
v_0 t & 0 < t < t_1 \\
v_0 t - \frac{c}{6} (t - t_1)^3 & t_1 < t < t_2
\end{cases}$$

Now bicycle rider's initial position is $x_{b, 0} = - 17 m$ and is travelling with constant speed $v_b$, so its speed and position after time $t$ are given by,
$$v_b(t) = v_b, \quad x_b(t) = -17 + v_b t$$

The cyclist reaches the car when the car just comes to rest, so at time $t = t_2$, we have,

$$\begin{align*}
x_b(t_2) &= x_c(t_2) \\
-17 + v_b t_2 &= v_0 t_2 - \frac{c}{6} (t_2 - t_1)^3
\end{align*}$$

Putting $v_0 = 12, t_1 = 1$ and $c = 6$, we get,
$$\begin{align*}
-17 + v_b t_2 &= 12t_2 - (t_2 - 1)^3 \\
v_b &= (12t_2 - (t_2 - 1)^3 + 17) / t_2
\end{align*}$$
We know that at $t = t_2$ car comes at rest, so $v_c(t_2) = 0$, gives us,
$$v_0  - \frac{c}{2} (t_2 - t_1)^2 = 0$$
after putting values of $v_0, c$ and $t_1$ and then solving $12 - 3(t_2 - 1)^2 = 0$, we get $t_2 = 3$.

**(b)**: Now putting all these in our expression for $v_b = (12t_2 - (t_2 - 1)^3 + 17) / t_2$ to get $v_b = 15m/s$.

---
## Reasoning for Problem 2. Elevator Trip

Elevator's accelerator is given by,
$$a(t) = \begin{cases}
a & \text{for } \, 0 < t < T \\
0 & \text{for } \, T < t < 5T \\
-a & \text{for } \, 5T < t < 6T
\end{cases}$$
where $a \in \mathbb{R}^{+}$. We know, how to find velocity, $v(t)$, in time interval $(t_1, t_2)$ we're given acceleration in that interval, that is,

$$v(t) - v(t_1) = \int_{t_1}^{t} a(t') \, dt.$$
Using this for the given time intervals $(0, T), (T, 5T)$ and $(5T, 6T)$, we get velocity function as,

$$v(t) = \begin{cases}
at & \text{for } \, 0 < t < T \\
aT & \text{for } \, T < t < 5T \\
6aT - at & \text{for } \, 5T < t < 6T
\end{cases}.$$

Using this we can draw the graph of $v(t)$ as shown below.

![[pset1_p2.png]]

We're asked to find $a$ in terms of $h$ and $T$ where $h$ is distance travelled by elevator in time interval $(0, 6T)$ and $T$ is just time. To do this, notice that, $h$ can be written as,

$$\begin{align*}
h &= \int_{0}^{6T} v(t) \, dt \\
&= \int_{0}^{T} v(t) \, dt + \int_{T}^{5T} v(t) \, dt + \int_{5T}^{6T} v(t) \, dt \\
&= \int_{0}^{T} at \, dt + \int_{T}^{5T} aT \, dt + \int_{5T}^{6T} (6aT - at) \, dt \\
&= \frac{aT^2}{2} + 4aT^2 + \left( 6aTt - \frac{at^2}{2} \right) \bigg{|}_{5T}^{6T} \\
&= \frac{aT^2}{2} + 4aT^2 + (36aT^2 - 18aT^2) - \left(30aT^2 - \frac{25aT^2}{2} \right) \\
&= 5aT^2
\end{align*}$$

Therefore, $a = h / 5 T^2$.

---
## Reasoning for Problem 3. Rocket Launch:

We can understand the problem setup better using our two dimensional coordinate system.
Suppose initial position of rocket is at $(0, 0)$ and stone is at $(0, h)$.

Rocket's time-varying accelerating is given by, $a_y(t) = A - Bt$ where $A$ and $B$ are positive constants. Since acceleration is rate of change in velocity, therefore,

$$\begin{align*}
\frac{d v_y(t)}{dt} &= a_y(t) \\
v_y(t) &= \int a_y(t) \, dt \\
v_y(t) &= \int (A - Bt) \, dt \\
v_y(t) &= At - \frac{B t^2}{2} + C_1
\end{align*}$$

$v_y(t) = 0$ at $t = 0$ because rocket is starting from rest. Using this in last equation, we get,
$$v_y(t) = At - \frac{B t^2}{2}.$$

And velocity is defined as rate of change in position, therefore using the same steps as above, we get,
$$y(t) = \frac{A t^2}{2} - \frac{B t^3}{6}.$$
Stone is initially is at rest means $s_0 = h$ and $s(t) = h - \frac{1}{2} g t^2$.

At maximum height rocket's velocity is $0$, implies $v_y(t) = 0 \implies t = 0$ or $t = 2A / B$.

Since the stone hits the rocket at the instant when the rocket reaches its maximum height means, at time $t = 2A/B$,

$$\begin{align*}
y(2A/B) &= s(2A/B) \\
\frac{A}{2} \left( \frac{2A}{B} \right)^2 - \frac{B}{6} \left( \frac{2A}{B} \right)^3  &= h - \frac{1}{2} g \left( \frac{2A}{B} \right)^2 \\
h &= \left( \frac{2A}{B} \right)^2 \left( \frac{A}{3} + g \right) \\
h &= \frac{2 A^2 (A + 3g)}{3 B^2}.
\end{align*}$$

### The Dimensional Check
To check the units, we need to identify the dimensions of $A$ and $B$ from the original acceleration equation: $a_y(t) = A - Bt$.

1. For $A:$ Since $a_y$ is accelerating $(m / s^2)$, $A$ must also be $m/s^2$.
2. For $B:$ Since the term $Bt$ must result in units of accelerating, and $t$ is in seconds $(s), B$ must have units of $m / s^2$.
3. For $g:$ This is standard gravitational accelerating, so it is $m / s^2$.

Now, let's look at the final expression:
$$h = \frac{2 A^2 (A + 3g)}{3 B^2}.$$

- **Numerator units:** $A^2$ is $(\text{m/s}^2)^2 = \text{m}^2/\text{s}^4$.
    
    - $(A + 3g)$ is $(\text{m/s}^2 + \text{m/s}^2) = \text{m/s}^2$.
        
    - Multiplying them: $(\text{m}^2/\text{s}^4) \cdot (\text{m/s}^2) = \mathbf{m^3/s^6}$.
        
- **Denominator units:** $B^2$ is $(\text{m/s}^3)^2 = \mathbf{m^2/s^6}$.
    
- **Final Ratio:**
$$\frac{\text{m}^3/\text{s}^6}{\text{m}^2/\text{s}^6} = \mathbf{m} \text{ (meters)}$$

The units match!

---
## Reasoning for Problem 4. Throw and Catch

Again, two dimensional coordinate system is going to help us a lot, since we don't need to worry about the height at which ball is thrown. We can freely assume initially ball is at $(0, 0)$ and person is at $(d, 0)$. Try imagining this person as a dot that moves along the *x-axis* as soon as the ball is thrown.

It is given that the initial ball's velocity is at an angle $\theta$ with respect to the ground and has a magnitude $v_0$. Therefore, its velocity components along *x-axis* and *y-axis* are,
$$v_x(t) = v_0 \cos(\theta), \quad v_y(t) = v_0 \sin(\theta) - g t$$
respectively and its positions on both axis at any time $t$ is given by,
$$x(t) = (v_0 \cos(\theta)) t, \quad y(t) = (v_0 \sin(\theta))t - \frac{1}{2} g t^2.$$

Person's acceleration is, $a_p(t) = Bt$, implies,
$$\begin{align*}
\frac{d v_p(t)}{dt} &= a_p(t) = Bt \\
v_p(t) &= \int Bt \, dt \\
v_p(t) &= \frac{B t^2}{2} + C
\end{align*}$$
where $C$ is constant of integration. Since we know person was initially at rest, so $v_p(t) = 0$ for $t = 0$, this gives us,
$$v_p(t) = \frac{B t^2}{2}.$$
Similarly, person's position at any time $t$ is given by,
$$\begin{align*}
\frac{d x_p(t)}{dt} &= v_p(t) \\
x_p(t) &= \int v_p(t) \, dt \\
&= \frac{B t^3}{6} + C.
\end{align*}$$
At $t = 0, x_p(t) = d$, this gives us $C = d$, after putting this into last equation, we get,
$$x_p(t) = \frac{B t^3}{6} + d.$$
The line in question, *"The person catches the ball at exactly the same height it was thrown from"*, means the time ball reaches ground ball and person are at the same position.

To find at what time ball reaches ground set, $y(t) = 0$ and get $t = (2 v_0 \sin(\theta)) / g$.
Further,
$$\begin{align*}
x_p((2 v_0 \sin(\theta)) / g) &= x((2 v_0 \sin(\theta)) / g) \\
\frac{B}{6} \left( \frac{2 v_0 \sin(\theta)}{g} \right)^3 + d &= (v_0 \cos(\theta)) \cdot \left( \frac{2 v_0 \sin(\theta)}{g} \right) \\
B &= \frac{3 g^3}{4 v_0^3 sin^3(\theta)} \left( \frac{v_0^2 \sin(2\theta)}{g} - d \right)
\end{align*}$$

### The Dimensional Check
From $a_p(t) = Bt$, we infer that units of $B$ must be $m/s^3$.

1. **The pre-factor:** $$\frac{g^3}{v_0^3} = \frac{(m / s^2)^3}{(m / s)^3} = \frac{m^3 / s^6}{m^3 / s^3} = \frac{1}{s^3}$$
2. **The term inside the parentheses:** $$\left( \frac{v_0^2}{g} - d \right) = \left( \frac{(m/s)^2}{m/s^2} - m \right) = (m - m) = m$$
   *(In dimensional analysis, $m - m$ doesn't equal zero; it means the resulting dimension is Length.)*

3. **Putting it together:**
$$\left( \frac{1}{s^3} \right) \cdot (m) = m / s^3.$$


---
## Reasoning for Problem 5. Vertical Collision

This is again problem of motion in one dimension, here that one dimension is *y-axis*.

Assume that initial velocity of both cans is $v_0$ and they collide at time $T$. Velocity of first can at any time $t$ is given by, $v_1(t) = v_0 - gt$ and for second can, we have to be little cautious because it was at rest for time $t \leq 4s$, so its velocity at any time $t$ is given by,

$$v_2(t) = 
\begin{cases}
0 & \text{if} \, 0 \leq t \leq 4 \\
v_0 (t - 4) - g(t - 4) & \text{if} \, t > 4
\end{cases}$$

and their positions after time $t$ is given by,

$$y_1(t) = v_0 t - \frac{1}{2} g t^2, \quad y_2(t) = v_0(t - 4) - \frac{1}{2} g (t - 4)^2.$$

At time $t = T$, we have $y_1(t) = y_2(t) = 5$.

Further,
$$\begin{align*}
y_1(T) &= y_2(T) \\
v_0 T - \frac{1}{2} g T^2 &= v_0 (T - 4) - \frac{1}{2} g (T - 4)^2 \\
v_0 &= g(T - 2)
\end{align*}$$
substituting $v_0 = g(T - 2)$ in $y_1(T) = 5$, gives us, $T \approx 4.240 s$.

Now, find $v_0$ using our relation $v_0 = g(T - 2) \approx 21.98 m/s$.

Final answers:
- **(a) Time of collision:** $4.240s$
- **(b) Initial Speed:** $21.98 m/s$

---