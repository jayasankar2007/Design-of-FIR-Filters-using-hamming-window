<img width="765" height="550" alt="image" src="https://github.com/user-attachments/assets/3d32c8b0-70fd-4015-b6f3-8fb1a1328464" /># Design-of-FIR-Filters-using-hamming-window

# DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of high pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
clc;
clear;
close;

// Filter specifications
N = 51;                      // Filter order (number of coefficients)
fc = 0.4;                    // Normalized cutoff frequency (fc = wc/pi)
n = 0:N-1;
alpha = (N-1)/2;

// Ideal High Pass Filter Impulse Response
hd = -sin(2*%pi*fc*(n - alpha)) ./ (n - alpha);
hd(alpha+1) = 1 - 2*fc;      // Handle division by zero at center

// Hamming Window
w = 0.54 - 0.46*cos(2*%pi*n/(N-1));

// Apply window to ideal response
h = hd .* w;

// Plot Impulse Response
subplot(2,1,1);
plot(n, h, 'r');
xlabel('n');
ylabel('h(n)');
title('Impulse Response of FIR High Pass Filter using Hamming Window');
grid on;

// Frequency Response
[H, f] = frmag(h, 512);      // Compute frequency response
subplot(2,1,2);
plot(f, abs(H));
xlabel('Normalized Frequency');
ylabel('|H(f)|');
title('Magnitude Response of FIR High Pass Filter');
grid on;

# OUTPUT
<img width="765" height="550" alt="image" src="https://github.com/user-attachments/assets/9aa763f2-4b95-47aa-9468-a52952c5e579" />

# RESULT
Thus, the High Pass FIR Digital Filter was successfully designed and implemented using the Hamming Window method in SCILAB. The impulse and magnitude responses were obtained and verified.
