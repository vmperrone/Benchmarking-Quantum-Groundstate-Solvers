### QOSF 2021 Cohort 4 (Oct 2021 to Jan 2022)
### Benchmarking Quantum Algorithms to Find the Ground State Energy of Molecules

#### Abstract
Several methods for performing computational chemistry have been developed to leverage quantum computers and algorithms. In the NISQ (Noisy Intermediate Scale Quantum) device era, several variational algorithms are being researched to find the solution from ground state energies of molecules. This project aims to investigate, benchmark and combine these algorithms across universal gate-controlled quantum devices and quantum annealer devices to make progress towards simulating large molecules.

#### How to use this repo
There are two ways to work with this repo:
1. Google Colab - This is the easiest option but the least powerful. You may run the notebook and view the results inline - but you will not have the ability to save your results to the databse or edit the supporting files (helper.py, utilities.py, XBK.py and QCC.py).
2. Remote VS Code Editor - This option gives you full access to the repo directory and it's associated files. You will be able to run experiments, update the results database and modify the supporting files (helper.py, utilities.py, XBK_method.py and QCC_method.py). However, in order or this option to work, you will need to set up an ngrok authentication token by signing up for an ngrok account at https://ngrok.com/ as instructed in cell 2 of the notebook.

Regardless of the the option you choose you will start by opening main\BenchmarkingTool.ipynb in Google Colab and follow the prompts within the notebook. Below is a brief overview of how it is laid out. These instructions are provided in the notebook when required for execution.

##### Google Colab
1. Ignore cell 1 and 2.
2. Clone the repo using cell 3.
3. Continue to follow the notebook from cell 4 onwards.
Note: To keep a clean interface, you may uncomment out the %%capture line in cell 3 and 4 to hide the output in google colab.

##### Remote VS Code Editor
1. Run cell 1, be sure to set up your own ngrok account and obtain your own ngrok token at https://ngrok.com/. It's free. Input your authentication token into cell 1 as indicated in a comment.
2. Run cell 2. Click the first link in the first line of the output to open the remote server.
3. Clone and open this repo to the /root directory in the VS Code editor.
Note: Things may not work the first time you click them as they require extensions. Be patient while extensions load to allow you to clone repos and run jupyter notebooks. You can monitor the progress on the bar at the bottom.

##### Other Pre-requisites
In order to run the notebook experiements on real quantum device backends, you will need an IBM Quantum account and API authentication token to run VQE (and future QAOA) experiments (https://quantum-computing.ibm.com/) and a D-Wave Systems account and API authentication token (https://cloud.dwavesys.com/leap/login/?next=/leap/). Please use your own tokens as it would be unethical to use mine.

#### Benchmarking Tool Workflow
After setting up the notebook and installing the required packages, the notebook will progress to select and load a molecule using the PYSCF Driver and qiskit-nature tools. This will be the molecule subject to the various quantum groundstate solvers to be benchmarked. As the notebook progresses the methods described in the digrams below will be benchmarked.

Qiskit and OpenFermion libraries are used to create a Fermionic Operator to represent the second quantization of the electronic hamiltonian. The Fermionic Operator is then mapped to a Qubit Operator in order to be solvable using quantum computing methods. The methods used are outlined in the diagram below.

![Alt text](https://github.com/kkhendry/Benchmarking-Quantum-Groundstate-Solvers/blob/master/main/img/Workflow1.PNG?raw=true "Title")

Where the XBK and QCC methods within the Ising Form aproach are mapped according to the high level diagram below. XBK and QCC and re-implementations of the approaches detailed in [1] and [2].

![Alt text](https://github.com/kkhendry/Benchmarking-Quantum-Groundstate-Solvers/blob/master/main/img/Workflow2.PNG?raw=true "Title")

Each method outputs a convergence plot of the groundstate energy calculated in each iteration of the respective algorithm as well as a dictonary containing the method used, the associated method parameters, the groundstate energy found and the running time.

#### Benchmarking Results
Some prelimnary results are shown in the table below:

![Alt text](https://github.com/kkhendry/Benchmarking-Quantum-Groundstate-Solvers/blob/master/main/img/Results.PNG?raw=true "Title")

#### Other Relevant Repos
The code for the QCC_method and the XBK_method is from https://github.com/jcopenh/Quantum-Chemistry-with-Annealers with reference to [2].

#### References
[1] Xia, Rongxin, Teng Bian, and Sabre Kais. "Electronic structure calculations and the Ising Hamiltonian." The Journal of Physical Chemistry B 122.13 (2017): 3384-3395. https://pubs.acs.org/doi/10.1021/acs.jpcb.7b10371
arXiv:1706.00271

[2] J. Copenhaver, A. Wasserman, and B. Wehefritz-Kaufmann. “Using Quantum Annealers to Calculate Ground State Properties of Molecules,” (2020), arXiv:2009.10779v2 [quant-ph]. doi:10.1063/5.0030397
arXiv:2009.10779
https://github.com/jcopenh/Quantum-Chemistry-with-Annealers
