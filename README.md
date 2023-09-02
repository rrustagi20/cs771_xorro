# cs771_xorro
This repository contains the mini project done in the course CS771A under Prof. Purushottam Kar

Our task was to crack a XOR Ring Oscillator PUF using a Linear ML Model.

## Problem 

### XOR Ring Oscillator?
The XORRO has R XOR gates and for each gate, the second input is linked to a config bit that tells us whether that XOR gate will act like an inverter or an identity. The first inputs of all the XOR gates is connected in a ring to create a ring oscillator.

### Simple XOR Ring Oscillator PUF
The above realization allows us to create a PUF as described above.
We take two XORROs. Our challenge is an R bit string that is fed into both XORROs as their
config bits. Each of the XORROs will now start oscillating. The (oscillating) outputs of the
two XORROs is fed into a counter which can find out which XORRO has a higher frequency.
If the upper XORRO (in this case XORRO 0) has a higher frequency, the counter outputs 1
else if the lower XORRO (in this case XORRO 1) has a higher frequency, the counter outputs
0. The output of the counter is our response to the challenge.

### Advanced XOR Ring Oscillator PUF
Make the PUF even stronger. Instead of having just 2
XORROs, Now take 2S XORROs and extend the challenge vector to have 2S more bits
which are called select bits. The first S of these select bits is interpreted as a number between 0
and 2S − 1 and used to select the corresponding XORRO as the first XORRO. This selection is
done by using a multiplexer. The next S select bits are used to select another XORRO as the
second XORRO. A counter is connected at the end taking in inputs from these two selected XORROs emulating the simple XORRO configuration
