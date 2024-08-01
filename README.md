# The-Virtual-Parkinsonian-Patient

Implementation of Dodymodel.
The coupling terms are base on the connectome computed as the edge-wise average of 10 healthy subjects extracted from the Human Connectome project.

Inputs
y: This is a vector that represents the state variables of the system at a given time t.
It includes the following components, each associated with a specific range of indices:
r: rate
V: membrane potential
u: adaptation current
Sa: synaptic activity (excitatory)
Sg: synaptic activity (inhibitory)
Dp: dopamine concentration
The length of y is 6 times the number of nodes (n_nodes) in the system, where each component (r, V, u, Sa, Sg, Dp) is a vector of length n_nodes.
t: This is the current time at which the function evaluates the system's dynamics.
params:
A tuple containing various parameters used in the model. These include constants and coefficients for the differential equations governing the dynamics of the system. 
In particular, three parameters are given: coupling_inhibitor, coupling_excitator, and coupling_dopamine, which represent the coupling constants for inhibitory, excitatory, and dopamine interactions respectively.
Outputs
The function returns dydt, a vector representing the time derivatives of the state variables. This vector is the result of concatenating the derivatives of each component (r, V, u, Sa, Sg, Dp).

The function computes the time derivatives (dydt) for each state variable using the given parameters and coupling constants.
The specific differential equations for each variable are based on the QIF (Quadratic Integrate-and-Fire) neuron model with additional terms for synaptic and dopamine dynamics.
