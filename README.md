# Dominating-Set-Problem-using-QAOA

To run the file, specify the inputs in the cell commented Input and run it. Further call the dsp_qaoa function to get 
the optimal parameters and pass the obtained parameter to plot_result funtion.The above directions are for running on
non-noisy simulator.

For running on completely noisy simulator, after passing inputs, call the dsp_qaoa_noise function to retrieve the 
parameters and pass them to plot_result_noise function to get the histogram plot of the output.

For running on partially noisy simulator, call dsp_qaoa instead of dsp_qaoa_noise to get the parameters and pass them to plot_result_noise function.

For running on IBM quantum computer, specify the backend in the variable backend_ibm, you want to run on, by default it is set to "IBM_Oslo". Running cost function on quantum computer for the specified number of shots won't be practically possible. So, it is suggested to run the final circuit on the quantum computer and cost function circuit on quantum simulator. To do this, pass the inputs, call function dsp_qaoa, pass the obtained parameters to plot_result_noise_ibm and get the output.

#### Input-
    N : number of nodes in the graph
    E : A sequence containing pairs of connected nodes through edges in tuples
    num_iter : number of times you want to apply the quantum circuit that calculates the cost. 
               This parameter is basically used to increase or decrease the accuracy of the output. More is the num_iter, 
               better are the results but execution time is also increased with accuracy.
               
#### Output -
    Histogram plot representing the probabilities for various bitstrings
    
The output obtained is a histogram plot. The bitstring on x-axis corresponding to highest probability is the result to
the dominating set problem in reverse order. It is in reverse order due to qiskit's way of numbering qubits from right 
to left.

#### Reference Paper:
  Guerrero, Nicholas J., ”Solving Combinatorial Optimization Problems using the Quantum Approximation Optimization Algorithm” (2020). Theses and Dissertations. 3263. https://scholar.afit.edu/etd/3263

