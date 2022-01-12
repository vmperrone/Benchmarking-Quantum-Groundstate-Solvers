### QOSF 2021 Cohort 4 (Oct 2021 to Jan 2022)
### Benchmarking Quantum Algorithms to Find the Ground State Energy of Molecules

#### Abstract
Several methods for performing computational chemistry have been developed to leverage quantum computers and algorithms. In the NISQ (Noisy Intermediate Scale Quantum) device era, several variational algorithms are being researched to find the solution from ground state energies of molecules. This project aims to investigate, benchmark and combine these algorithms across universal gate-controlled quantum devices and quantum annealer devices to make progress towards simulating large molecules.

#### How to use this repo
Open the BenchmarkingTool.ipynb file and follow the prompts. The file can be opened in Google Colab (recommended) or in a remote VS Code environment by following the applicable prompts in the notebook (requires user to have an ngrok account to host a remote environment). The VS Code environment allows the user to perform more advanced work by allowing users to directly access supporting python files such as helper.py, utilities.py, XBK.py and QCC.py. Instructions for both the Google Colab and VS Code options are enclosed in the notebook file. Prompts to install all the required packages are also enclosed within the notebook file.

#### Benchmarking Tool Workflow
After setting up the notebook and installing the required packages, the notebook will progress to select and load a molecule using the PYSCF Driver and qiskit-nature tools. This will be the molecule subject to the various quantum groundstate solvers to be benchmarked. As the notebook progresses the methods described in the digrams below will be benchmarked.

Qiskit and OpenFermion libraries are used to create a Fermionic Operator to represent the second quantization of the electronic hamiltonian. The Fermionic Operator is then mapped to a Qubit Operator in order to be solvable using quantum computing methods. The methods used are outlined in the diagram below.

![Alt text](https://github.com/kkhendry/Benchmarking-Quantum-Groundstate-Solvers/blob/master/Workflow1.PNG?raw=true "Title")

Where the XBK and QCC methods within the Ising Form aproach are mapped according to the high level diagram below. XBK and QCC and re-implementations of the approaches detailed in [1] and [2].

![Alt text](https://github.com/kkhendry/Benchmarking-Quantum-Groundstate-Solvers/blob/master/Workflow2.PNG?raw=true "Title")

Each method outputs a convergence plot of the groundstate energy calculated in each iteration of the respective algorithm as well as a dictonary containing the method used, the associated method parameters, the groundstate energy found and the running time.

#### Benchmarking Results
[To be added]

#### Other Relevant Repos
[To be added]
