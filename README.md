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
G = 60;
eta = 0.5;
Ae = 1;

Smin = 1e-10;

Ppeak= 2000:100:10000; 

Rmax_values = zeros(1, length(Ppeak));

for i = 1:length(Ppeak)
    Rmax_values(i) = ((Ppeak(i) * G * eta * Ae) / (16 * %pi^2 * Smin))^(1/4);
end

clf;
subplot(3,1,1);
plot(Ppeak, Rmax_values,'b');
xlabel('P_{peak}');
ylabel('R_{max}');

clear "G" "Rmax_values" "Ppeak";
Ppeak = 5000;
G = 10:5:100;
Rmax_values = zeros(1, length(G));

for i = 1:length(G)
    Rmax_values(i) = ((Ppeak * G(i) * eta * Ae) / (16 * %pi^2 * Smin))^(1/4);
end

subplot(3,1,2);
plot(G, Rmax_values,'r');
xlabel("G");
ylabel("R_{max}");

clear "G" "Rmax_values" "Smin";
G = 60;
Smin_values = logspace(-12, -8, 50);
Rmax_values = zeros(1, length(Smin_values));

for i = 1:length(Smin_values)
    Rmax_values(i) = ((Ppeak * G * eta * Ae) / (16 * %pi^2 * Smin_values(i)))^(1/4);
end

subplot(3,1,3);
plot(Smin_values, Rmax_values,'g');
xlabel("S_{min}");
ylabel("R_{max}");

```
## OUTPUT WAVEFORM:



## TABULATION :


## RESULT:

Thus, the Radar Range Equation was successfully implemented in Scilab. 







