# Use_Classes_for_Generating_Signals

**Learn how to build a class in python and use it to generate signals.**


During your work with signal data, you might end up programming multiple functions and methods that can implement the process you want to use on the signal data. However, at some point, it might be hard to keep tracking the quality of your methods applied to signals without prior knowledge of this data. Therefore, generating signal data with prior known parameters helps you better understand your program and method. Generating signals, especially sinusoidal signals, is very common in signal processing studies. And it is usually done for testing or to represent the use of different signal processing techniques, such as Discrete Fourier Transform, Wavelet analysis, etc.

In this notebook, we will learn how to use classes to build a signal generator that you can use to generate sinusoidal signals for further understanding signal processing methods.

The example below is to generate a signal that is the sum of three sinusoidal signals using the Signal class we've built.

```sh
# Define the first signal, 20Hz and amplitude of 2
s1 = Signal(amplitude=2, frequency=20, sampling_rate=1000.0, duration=3)
sine1 = s1.sine()

# Define the second signal, 2Hz and amplitude of 6
s2 = Signal(amplitude=6, frequency=2, sampling_rate=1000.0, duration=3)
sine2 = s2.sine()

# Define the second signal, 7Hz and amplitude of 1
s3 = Signal(amplitude=1, frequency=7, sampling_rate=1000.0, duration=3)
sine3 = s2.sine()

# Our signal is the sum of the three signals
signal = sine1 + sine2 + sine3

# Plot the signal
plt.plot(s1.time_axis, signal, 'r')
plt.xlabel('Time [sec]')
plt.ylabel('Amplitude')
plt.title('This signal is generated using Signal class')
plt.show()
```

<p align="center">
  <img src="https://github.com/OmarAlkousa/Use_Classes_for_Generating_Signals/blob/e6abd84608fcd846d51f59e943463379a561f154/Use_Classes_for_Generating_Signals/example%20of%20sinusoidal%20wave%20using%20Signal%20Class.png", width="400">
</p>


## Acknowledgment:
[[1]](https://docs.python.org/3/tutorial/classes.html) Python Documentation, Classes, A First Look at Classes. [Accessed at 28/1/2023]

[[2]](https://www.geeksforgeeks.org/self-in-python-class/) GeeksforGeeks, Classes, Self in Classes. [Accessed at 28/1/2023]

[[3]](https://pythonnumericalmethods.berkeley.edu/notebooks/chapter24.01-The-Basics-of-waves.html) Kong, Q., Siauw, T., & Bayen, A. (2020). Python programming and numerical methods: A guide for engineers and scientists, Fourier Transform, The Basics of waves. Academic Press.
