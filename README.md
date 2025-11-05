# RADAR-RANGE-USING-SCILAB

## Aim:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Python programming.

## Theory:
The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:

## Formula:

<img width="365" height="423" alt="image" src="https://github.com/user-attachments/assets/69e2f6c9-056c-4e7b-8eb5-993868bc3013" />



## Procedure
```
1.Open Scilab software on your computer.
2.Create a new script file by choosing File → New → Script from the menu bar.
3.Clear the Scilab environment using the commands to clear the screen and previous variables.
4.Define the input values required for radar range calculation, such as:
5.Transmitted power in watts
6.Antenna gain (a number without units)
7.Wavelength in meters (directly entered value)
8.Radar cross-section in square meters
9.Minimum detectable power in watts
10.Use Scilab statements to perform the radar range calculation based on the given parameters.
11.Display the calculated range using the display command so that the output appears in the Scilab console window.
12.Save the script file with an appropriate name such as “radar_range.sce”.
13.Run the program by selecting Execute → File with Echo or by pressing the shortcut key combination.
14.Observe the result displayed in the Scilab command window — it shows the maximum range of the radar in meters.
15.Stop the execution of the program.
```

## Algorithm:
```
1.Start the program.

2.Define constants such as the speed of light and the value of pi.

3.Input all radar parameters — these include the transmitted power, antenna gain, wavelength, radar cross-section, and the minimum detectable power.

4.Assign a fixed wavelength value directly (do not calculate it).

5.Substitute all known values of transmitted power, antenna gain, wavelength, radar cross-section, and minimum detectable power into the radar range equation.

6.Perform the necessary mathematical operations in Scilab to compute the maximum radar detection range.

7.Display the computed range on the screen in meters.

8.End the program.
```

## Program:

```
clc;
clear;
clf;
Gt = 50;
Gr = 45;
l = 0.08;
s = 6;
Pm = 1e-10;
K = (4 * %pi)^3;
Pt = 0:6:600;
x = Pt .* Gt .* Gr .* l .* l .* s;
y = K * Pm;
z = x ./ y;
R = z.^(1/4);
subplot(3,1,1);
plot(Pt,R);
xlabel('Transmit Power (W)');
ylabel('Range (m)');
title('Range vs Transmit Power');
xgrid();
Pr = 0:10:1000;
Pt_fixed = 50;
x = Pt_fixed .* Gt .* Gr .* l .* l .* s;
y = K .* Pr;
z = x ./ y;
R1 = z.^(1/4);
subplot(3,1,2);
plot(Pr, R1);
xlabel('Received Power (W)');
ylabel('Range (m)');
title('Range vs Received Power');
xgrid();
G = 0:0.7:70;
Pm_fixed = 1e-10;
Pt_fixed = 50;
a = Pt_fixed .* G .* l .* l .* s;
b = K * Pm_fixed;
c = a ./ b;
R2 = c.^(1/4);
subplot(3,1,3);
plot(G, R2);
xlabel('Antenna Gain (G)');
ylabel('Range (m)');
title('Range vs Antenna Gain');
xgrid();
```

## Output:
<img width="1920" height="1200" alt="Screenshot (559)" src="https://github.com/user-attachments/assets/2d7e773a-6de0-4684-8278-33460dec96ea" />


## Tabular Column:

![WhatsApp Image 2025-11-05 at 10 49 02_85957233](https://github.com/user-attachments/assets/9f1cf6af-5726-4bf7-915d-8aa40fe3f3a2)


## Result:

Thus, the maximum range of a radar system using the Radar Range Equation is verified through a Python program.
