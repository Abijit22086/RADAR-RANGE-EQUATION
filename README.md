# RADAR-RANGE-EQUATION
## AIM:
To implement and analyze the Radar Range Equation using Scilab, and to plot the received power with respect to range.

## Apparatus Required

Software: Scilab
Hardware: Personal Computer

## Theory

The Radar Range Equation relates the power received by a radar from a target at distance 𝑅:


<img width="182" height="83" alt="image" src="https://github.com/user-attachments/assets/62355deb-66a1-42ca-a2ef-e8b029e1d594" />





<img width="333" height="293" alt="image" src="https://github.com/user-attachments/assets/0b2fb318-dbbc-44bd-ac0e-c874abc35b79" />




## PROGRAM:
```
G = 75;
eta = 0.65;
Ae = 1.2;

Smin = 2e-11;

Ppeak = linspace(1500, 12000, 400);

Rmax_values = ((Ppeak .* G .* eta .* Ae) ./ (16 * %pi^2 * Smin)).^(1/4);

clf;
subplot(3,1,1);
plot(Ppeak, Rmax_values, 'b');
xlabel('P_{peak}');
ylabel('R_{max}');

clear G Rmax_values Ppeak;
Ppeak = 7000;

G = linspace(5, 125, 400);
Rmax_values = ((Ppeak .* G .* eta .* Ae) ./ (16 * %pi^2 * Smin)).^(1/4);

subplot(3,1,2);
plot(G, Rmax_values, 'r');
xlabel('G');
ylabel('R_{max}');

clear G Rmax_values Smin;
G = 75;

Smin_values = logspace(-13, -9, 400);
Rmax_values = ((Ppeak .* G .* eta .* Ae) ./ (16 * %pi^2 .* Smin_values)).^(1/4);

subplot(3,1,3);
plot(Smin_values, Rmax_values, 'g');
xlabel('S_{min}');
ylabel('R_{max}');


```
## OUTPUT WAVEFORM:
<img width="1919" height="1141" alt="Screenshot 2025-11-27 003626" src="https://github.com/user-attachments/assets/347c9c78-ecbd-49c0-919e-519f2e42fd0e" />


## TABULATION :
<img width="871" height="1280" alt="image" src="https://github.com/user-attachments/assets/0e590d9c-d927-49aa-b588-29b94ce64a99" />


## RESULT:

Thus, the Radar Range Equation was successfully implemented in Scilab. 







