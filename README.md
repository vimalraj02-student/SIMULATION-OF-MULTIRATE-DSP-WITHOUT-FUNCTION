# EXP 6 : SPEECH RECOGNITION USING SCILAB

## AIM: 

To perform and verify multirate DSP without function using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM : 
    clear;
    clc;
    close();
    
    n = 0:%pi/50:2*%pi;
    x = sin(n); // Original signal
    
    // Input upsampling and downsampling factors
    M = input("Enter the downsampling factor M: ");
    L = input("Enter the upsampling factor L: ");
    
    // --- Downsampling ---
    downsampling_x = x(1:M:$);
    disp(x, "Input signal x(n) = ");
    disp(downsampling_x, "Downsampled signal x(Mn) = ");
    
    // Plot original and downsampled signals
    scf(1);
    subplot(2,1,1);
    plot2d3(1:length(x), x);
    xtitle("Original Signal");
    
    subplot(2,1,2);
    plot2d3(1:length(downsampling_x), downsampling_x);
    xtitle("Downsampled Signal by a factor of M");
    
    // --- Upsampling ---
    upsampling_x = zeros(1, L*length(x));
    for i = 1:length(x)
        upsampling_x((i-1)*L + 1) = x(i);
    end
    
    disp(upsampling_x, "Upsampled signal x(n/L) = ");
    
    // Plot original and upsampled signals
    scf(2);
    subplot(2,1,1);
    plot2d3(1:length(x), x);
    xtitle("Original Signal");
    
    subplot(2,1,2);
    plot2d3(1:length(upsampling_x), upsampling_x);
    xtitle("Upsampled Signal by a factor of L");

//  SPEECH RECOGNITION USING SCILAB

## OUTPUT: 
<img width="1919" height="969" alt="image" src="https://github.com/user-attachments/assets/b813ca56-0fa2-4c5c-8530-a5c76e9324bb" />


## RESULT: 
Thus the decimation process by a factor M and interpolation process by a factor L using 
SCILAB was implemented. 
