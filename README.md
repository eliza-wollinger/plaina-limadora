# Whitworth Mechanism Animation

Interactive simulation of a **Whitworth Quick Return Mechanism** developed in Python using **NumPy** and **Matplotlib**.

The project combines a real-time mechanism animation with synchronized kinematic plots of **position**, **velocity**, and **acceleration**, allowing a complete visualization of the mechanism behavior throughout a full crank revolution.

![Whitworth Animation](https://github.com/eliza-wollinger/plaina-limadora/blob/main/image/download.gif)

---

## Features

* Whitworth quick-return mechanism animation
* Real-time slider motion
* Position, velocity and acceleration analysis
* Synchronized indicators on all graphs
* Adjustable mechanism geometry
* Gear reduction modeling
* Compatible with Jupyter Notebook and Google Colab

---

## Mathematical Model

### Gear Reduction

The angular velocity of the mechanism is obtained from the gear ratio:

```math
i=\frac{Z_{coroa}}{Z_{motor}}
```

```math
n_{coroa}=\frac{n_{motor}}{i}
```

```math
\omega=\frac{2\pi n_{coroa}}{60}
```

Where:

```math
* (Z_{motor}) = motor gear teeth
```
```math
* (Z_{coroa}) = driven gear teeth
```
``` math
* (n) = rotational speed (rpm)
```
```math
* (\omega) = angular velocity (rad/s)
```
---

### Crank Coordinates

The crank endpoint (B) is defined by:

```math
x_B=r\cos\theta
```

```math
y_B=r\sin\theta
```

Where:
```math
* (r) = crank radius
```
```math
* (\theta) = crank angle
```
---

### Slider Position

The horizontal displacement of the ram is given by:

```math
x(\theta)=\frac{(a+b)\,r\cos\theta}{b+r\sin\theta}
```

Where:
```math
* (a) = slider offset
```
``` math
* (b) = slotted lever offset
```

---

### Velocity

Velocity is obtained from the first derivative of displacement:

```math
v(\theta)=\frac{dx}{dt}
```

```math
v(\theta)=
-\omega(a+b)r
\frac{r+b\sin\theta}
{(b+r\sin\theta)^2}
```

---

### Acceleration

Acceleration is obtained from the second derivative:

```math
a(\theta)=\frac{d^2x}{dt^2}
```

```math
a(\theta)=
\omega^2(a+b)r\cos\theta
\frac{2r^2+br\sin\theta-b^2}
{(b+r\sin\theta)^3}
```

---

## Parameters Used

| Parameter         |     Value |
| ----------------- | --------: |
| r                 |  25.31 mm |
| a                 | 130.20 mm |
| b                 | 127.50 mm |
| Motor Gear Teeth  |        30 |
| Driven Gear Teeth |        68 |
| Motor Speed       |    10 rpm |

### Gear Ratio

```math
i=\frac{68}{30}=2.2667
```

### Driven Speed

```math
n_{coroa}=\frac{10}{2.2667}=4.41\ rpm
```

### Angular Velocity

```math
\omega=\frac{2\pi(4.41)}{60}=0.462\ rad/s
```

---

## Dashboard

The dashboard is divided into two sections:

### Mechanism Animation

* Crank rotation
* Slotted lever motion
* Connecting rod movement
* Slider displacement

### Kinematic Analysis

* Position vs. crank angle
* Velocity vs. crank angle
* Acceleration vs. crank angle

A moving marker highlights the current operating point during the animation.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/eliza-wollinger/mechanism-animations.git
cd mechanism-animations
```

Install dependencies:

```bash
pip install numpy matplotlib
```

---

## Usage

Run the notebook:

```python
HTML(anim.to_html5_video())
```

The animation will be rendered directly inside Jupyter Notebook or Google Colab.

---
