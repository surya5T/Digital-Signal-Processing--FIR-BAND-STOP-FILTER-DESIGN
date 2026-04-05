# Digital-Signal-Processing--FIR-BAND-STOP-FILTER-DESIGN
## AIM:
To generate design of Band Stop FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Band Stop filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
```
GRAM:
clc
clear all
close all
Ap=input('enter the value of Ap');
As=input('enter the value of As');
wp=input('enter the PB frequency');
ws=input('enter the SB frequency');
T=input('enter the value of time');
omega_p=(2/T)*tan(wp/2)
omega_s=(2/T)*tan(ws/2)
alpha_p=20*log10(Ap)
alpha_s=20*log10(As)
[N wc]=buttord(omega_p,omega_s,alpha_p,alpha_s,'s')
[num den]=butter(N,1,'s')
display('normalised transfer function');
hs=tf(num,den)
[num1 den1]=butter(N,wc,'s')
display('unnormalised transfer function');
hs1=tf(num1,den1)
[numz denz]=bilinear(num1,den1,1/T)
hz=tf(numz,denz,T)
display('digital transfer function');
w=0:pi/16:pi
y=freqz(numz,denz,w);
%MAGNITUDE RESPONSE
y1=abs(y);
plot(w,y1);
xlabel('frequency');
ylabel('magnitude');
title('magnitude response butterworth LPF');

```
## OUTPUT:
![5b900ed8-962e-4fef-921e-15e0054d8150](https://github.com/user-attachments/assets/c9442960-6aeb-49c7-8c3e-2f77af284acd)

## RESULT:
![942d787c-3dbf-47e1-9008-cd8768a1caca](https://github.com/user-attachments/assets/91076915-1dea-4e9f-bea7-93e5407294d5)
