# CNOT Gate Implementation on Silicon Spin System Using GRAPE Algorithm

To implement the CNOT gate on silicon spin systems, we utilized the GRAPE algorithm with QUTIP. 
The system consists of two phosphorus nuclei and one shared electron between them (2P1e)(https://www.nature.com/articles/s41586-021-04292-7). 
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


If you use the code, please cite the software and the paper.
For paper:

@article{Üstün_2024,
doi = {10.1088/2058-9565/ad473c},
url = {https://dx.doi.org/10.1088/2058-9565/ad473c},
year = {2024},
month = {may},
publisher = {IOP Publishing},
volume = {9},
number = {3},
pages = {035037},
author = {Gözde Üstün and Andrea Morello and Simon Devitt},
title = {Single-step parity check gate set for quantum error correction},
journal = {Quantum Science and Technology},
abstract = {A key requirement for an effective quantum error correction (QEC) scheme is that the physical qubits have error rates below a certain threshold. The value of this threshold depends on the details of the specific QEC scheme, and its hardware-level implementation. This is especially important with parity-check circuits, which are the fundamental building blocks of QEC codes. The standard way of constructing the parity check circuit is using a universal set of gates, namely sequential CNOT gates, single-qubit rotations and measurements. We exploit the insight that a QEC code does not require universal logic gates, but can be simplified to perform the sole task of error detection and correction. By building gates that are fundamental to QEC, we can boost the threshold and ease the experimental demands on the physical hardware. We present a rigorous formalism for constructing and verifying the error behavior of these gates, linking the physical measurement of a process matrix to the abstract error models commonly used in QEC analysis. This allows experimentalists to directly map the gates used in their systems to thresholds derived for a broad-class of QEC codes. We give an example of these new constructions using the model system of two nuclear spins, coupled to an electron spin, showing the potential benefits of redesigning fundamental gate sets using QEC primitives, rather than traditional gate sets reliant on simple single and two-qubit gates.}
}

For software:

Üstün, G., Morello, A., Devitt, S., & Pitchford, A. (2023). CNOT Gate Implementation on Silicon Spin System Using GRAPE Algorithm (Version 1.0.0) [Computer software]. https://github.com/apassenger/CNOT_gate_implementation_with_Grape
or 
@software{Ustun_CNOT_Gate_Implementation_2023,
author = {Üstün, Gözde and Morello, Andrea and Devitt, Simon and Pitchford,  Alexander},
month = apr,
title = {{CNOT Gate Implementation on Silicon Spin System Using GRAPE Algorithm}},
url = {https://github.com/apassenger/CNOT_gate_implementation_with_Grape},
version = {1.0.0},
year = {2023}
}

Citation will not take anything from your work !
