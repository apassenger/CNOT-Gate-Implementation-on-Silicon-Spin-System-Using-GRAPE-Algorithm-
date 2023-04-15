# CNOT Gate Implementation on Silicon Spin System Using GRAPE Algorithm"

To implement the CNOT gate on silicon spin systems, we utilized the GRAPE algorithm with QUTIP. 
The system consists of two phosphorus nuclei and one shared electron between them (2P1e). 
The electron's rotation around the nuclei creates hyperfine interaction, which can be used to generate entangling gates such as CNOT. 
However, since we have two nuclei in the system, there are two hyperfine interactions, which are permanent properties of the system 
and cannot be turned off, tuned or manipulated. Therefore, we attempted to implement the CNOT gate using one of these hyperfine interactions, 
while the other hyperfine interaction is a disturbance to the system. To achieve a perfect CNOT gate, we would need to wait long enough 
for the second hyperfine interaction to become negligible, and the GRAPE algorithm was used to examine this effect.

The algorithm was executed with various gate evolution times (1, 10, 100, and 1000 microseconds) while maintaining constant min/max amplitudes.
The theoretical fidelity was found to be optimal at a gate evolution time of 100 microseconds, which can be attributed to the 
interruption of the second hyperfine interaction in the system. In addition, the algorithm was executed for the same gate evolution time, 
but with varying min/max control amplitudes (ranging from 2mT to 40mT). These two scenarios were then tested for different frequencies in the system, 
using both modulated and non-modulated control Hamiltonians. It is important to note that a minimum of 10,000 time slots were required for the algorithm 
to successfully implement the CNOT gate. Any fewer time slots than this will prevent the algorithm from executing the gate properly.

You can find the codes and the results of the codes in this folder


P.S Another solution for implementing a CNOT gate without having to wait for a long time could be to polarize the state of the nuclei. 
For instance, if we are implementing a CNOT gate between the electron and the down state of the nuclei, we can bring the second nucleus to the 
down state as well, so that they cannot interfere with each other. However, this method goes against the universality of computation, 
where we should be able to implement gates perfectly and independently of the states of the system.
