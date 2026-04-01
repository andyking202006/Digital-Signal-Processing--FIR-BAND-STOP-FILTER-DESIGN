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
clc; % clear screen
clear all; % clear screen
close all; % close all figure windows
wc1=input('enter the value of wc1');
wc2=input('enter the value of wc2');
N=input('enter the value of filter');
alpha=(N-1)/2;
eps=0.001;
%Band Stop Filter Coefficient 
n=0:1:N-1;
hd=(sin(pi*(n-alpha+eps))-sin((n-alpha+eps)*wc1)+sin((n-alpha+eps)*wc2))./(pi*(n-alpha+eps)) 
% Bartlett Window Sequence
n = 0:1:N-1;
alpha = (N-1)/2;
wh = 1 - (2*abs(n - alpha)/N);
hn = hd .* wh;                
% Plot the Band Stop Filter with Bartlett Window Technique
w=0:0.01:pi;
h=freqz(hn,1,w);
plot(w/pi,abs(h),'blue');
title('Band Stop FIR Filter using Bartlett Window');
```
## OUTPUT:
<img width="1600" height="869" alt="image" src="https://github.com/user-attachments/assets/0919c597-0c84-419e-bf07-522c0ca68906" />

## RESULT:
<img width="900" height="1600" alt="image" src="https://github.com/user-attachments/assets/3ac5ea7e-672f-4d4c-a8ba-d69986523b18" />
