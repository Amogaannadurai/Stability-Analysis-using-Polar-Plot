# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

![IMG-20251127-WA0016](https://github.com/user-attachments/assets/856f7ed0-b63b-48dc-a8d3-ab0035008c56)

![WhatsApp Image 2025-11-27 at 21 14 32_67c1af95](https://github.com/user-attachments/assets/cde096d2-611b-4874-858e-6a26bcb29931)
![WhatsApp Image 2025-11-27 at 21 14 54_f0173078](https://github.com/user-attachments/assets/39592871-5253-4e8b-b763-1dec9f742d3b)

![IMG-20251127-WA0012](https://github.com/user-attachments/assets/372107fd-f4ef-4df5-b160-c0d4e54b9115)


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b908f8a2-e425-48d8-80c1-e315fdce0d20" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7 <br>
Phase Margin = -8.8865 <br>
Gain crossover frequency = 3.7565 <br>
Phase crossover frequency = 3.1623 <br>
The system is unstable
