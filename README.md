# DSBSC_using_python

# Aim


To implement and analyze (DSBSC) using Python's NumPy and Matplotlib libraries. 

# Apparatus Required

1.	Software: Python with NumPy and Matplotlib libraries
2.	Hardware: Personal Computer
  
# Theory

DSB-SC (Double Sideband Suppressed Carrier) is a type of amplitude modulation where the carrier wave is suppressed, and only the two sidebands (which contain the actual information) are transmitted. This saves power and reduces bandwidth waste compared to standard AM.

In DSB-SC, the amplitude of the carrier is still varied according to the message signal, but the carrier itself is not transmitted.


# Algorithm


1.	Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and frequency deviation.
2.	Generate Time Axis: Create a time vector for the signal duration.
3.	Generate Message Signal: Define the message signal as a cosine wave.
4.	Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
5.	Generate FM Signal: Apply the DSBSC modulation formula to obtain the modulated signal.
6.	Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

# Program

```
import numpy as np
import matplotlib.pyplot as plt
Am = 4.0;
fm = 345;
Ac = 8.0;
fc = 3450;
fs = 34500;
t=np.arange(0,2/fm,1/fs)
m = np.cos(2 * np.pi * fm * t)
c=np.cos(2*np.pi*fc*t)
s1 = (Ac + m) * np.cos(2 * np.pi * fc * t)
s2 = (Ac - m) * np.cos(2 * np.pi * fc * t)
s = s1 - s2
s = m * c
plt.subplot(3,1,1)
plt.plot(t, m)

plt.subplot(3,1,2)
plt.plot(t,c)

plt.subplot(3,1,3)
plt.plot(t,s)

```

# Output Waveform

<img width="694" height="507" alt="image" src="https://github.com/user-attachments/assets/a73e1e68-92e7-4e0c-86db-280f136e791e" />



## Tabular Column

![WhatsApp Image 2025-10-28 at 18 56 38_1b3c7972](https://github.com/user-attachments/assets/1e7be690-bcab-40d1-bb1f-02b0e1c6746e)



## Result

The message signal, carrier signal, and DSBSC signal will be displayed in separate plots. The modulated signal will show amplitude variations corresponding to the amplitude of the message signal.
