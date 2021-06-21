
Artificial neural network are computing system vaguely inspired by the biological neural network that constitute human brains.

![[ANN general architecture.png]]

An ANN is based on **a collection of connected unit or nodes call artificial neurons**, which loosely model the neurons in a biological brain. Each connection, like the synapses in a biological brain, can transmit a signal to oher neurons. An artificial neuron that receives a signal then processes it and can signal neurons connected to it. **The "signal' at a connection is a real number, and the output of each neuron is computed by some non-linear function of the sum of its inputs.** The connections are called edges.

Neurons and edges typically have a [weight](Weights) that adjusts as learning proceeds. The weight increases or decreases the strength of the signal at a connnection. Neurons may have threshold such that a signal is sent only if the aggregate signal crosses that [threshold](Bias) a.k.a Bias. 

![[general process of ANN.png]]

Typically, neurons are aggregated into layers. Different layer may perform different transformations on their inputs. Signal travel from the first layer to the last layer, possibly after traversion the layers multiple times.