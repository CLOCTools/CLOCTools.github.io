# CLOCTools
Hello, this is the overview page for CLOCTools with links to its various repositories. CLOCTools are a library of tools for closed-loop neuroscience.
CLOCTools includes algorithms for closed-loop control and tools for real-time implementation.  Additionally, you'll find a list of relevant publications and related tools for simulation, modeling, and analysis.

## Overview
<img src="figures/Copy of CLOCtools overview.png" align='center' style='border:15px solid #ffffff00; width:100%'>

CLOCTools algorithms include linear dynamical systems control estimation (ldsCtrlEst) and hidden Markov model switching linear dynamical systems (hmm).  For implementation, CLOC tools has a variety of software for interfacing with the the real time tools RTXI and TDT along with tools for interfacing across programming languages.

## Core Algorithms

### **State-space dynamics** (GLDS, PLDS) [`CLOCTools/ldsCtrlEst`](https://github.com/CLOCTools/lds-ctrl-est)

<img src="/figures/lds_ctrl_est_logo2022.png" height=90 style='border:15px solid #ffffff00'>

ldsCtrlEst is a C++ library for estimation and control of linear dynamical systems (LDS) with Gaussian or Poisson observations. It is meant to provide the functionality necessary to implement feedback control of linear dynamical systems experimentally. This library was originally developed for the task of controlling neuronal activity using spike count data as feedback and optogenetic inputs for control.  ldsCtrlEst has both estimation and feedback control with parameter adaptive estimation, switched estimate and control, and can use both Gaussian and Poisson observation models.

The repository also provides an alternate MATLAB implementation, MATLAB bindings to model fitting functions, and Python bindings to the entire library.

  - [code](https://github.com/CLOCTools/lds-ctrl-est), [documentation](https://CLOCTools.github.io/lds-ctrl-est/)    
 
<details markdown="1"><summary>examples scripts:</summary>
  
  - GLDS control - `eg_glds_ctrl`([`.cpp`][glds_ctrl_cpp]\|[`.py`][glds_ctrl_py]) - [tutorial](https://CLOCTools.github.io/lds-ctrl-est/docs/tutorials/eg_glds_control/)
  - GLDS control of PLDS - `eg_glds_du_plds_ctrl`([`.cpp`][glds_du_plds_ctrl_cpp]\|[`.py`][glds_du_plds_ctrl_py])
    - change in control (du) is being updated, rather than amplitude (u).
  - PLDS control - `eg_plds_ctrl`([`.cpp`][plds_ctrl_cpp]\|[`.py`][plds_ctrl_py])
  - PLDS estimation - `eg_plds_est`([`.cpp`][plds_est_cpp]\|[`.py`][plds_est_py]) - [tutorial](https://CLOCTools.github.io/lds-ctrl-est/docs/tutorials/eg_plds_state_estimation/)
  - Switched PLDS control - `eg_plds_switched_ctrl`([`.cpp`][plds_switched_ctrl_cpp]\|[`.py`][plds_switched_ctrl_py]) - [tutorial](https://CLOCTools.github.io/lds-ctrl-est/docs/tutorials/eg_switched_plds_control/)
  - GLDS fit - [`eg_glds_fit.py`][glds_fit_py], [`test_glds_fit.m`][glds_fit_mat]
  - PLDS fit - [`eg_plds_fit.py`][plds_fit_py], [`test_plds_fit.m`][plds_fit_mat]
  
</details>

[glds_ctrl_cpp]: https://CLOCTools.github.io/lds-ctrl-est/docs/api/examples/eg_glds_ctrl_8cpp-example/#example-eg_glds_ctrl.cpp
[glds_du_plds_ctrl_cpp]: https://CLOCTools.github.io/lds-ctrl-est/docs/api/examples/eg_glds_du_plds_ctrl_8cpp-example/#example-eg_glds_du_plds_ctrl.cpp
[plds_ctrl_cpp]: https://CLOCTools.github.io/lds-ctrl-est/docs/api/examples/eg_plds_ctrl_8cpp-example/#example-eg_plds_ctrl.cpp
[plds_est_cpp]: https://CLOCTools.github.io/lds-ctrl-est/docs/api/examples/eg_plds_est_8cpp-example/#example-eg_plds_est.cpp
[plds_switched_ctrl_cpp]: https://CLOCTools.github.io/lds-ctrl-est/docs/api/examples/eg_plds_switched_ctrl_8cpp-example/#example-eg_plds_switched_ctrl.cpp

[glds_ctrl_py]: https://github.com/CLOCTools/lds-ctrl-est/tree/master/python/examples/eg_glds_ctrl.py
[glds_du_plds_ctrl_py]: https://github.com/CLOCTools/lds-ctrl-est/tree/master/python/examples/eg_glds_du_plds_ctrl.py
[plds_ctrl_py]: https://github.com/CLOCTools/lds-ctrl-est/tree/master/python/examples/eg_plds_ctrl.py
[plds_est_py]: https://github.com/CLOCTools/lds-ctrl-est/tree/master/python/examples/eg_plds_est.py
[plds_switched_ctrl_py]: https://github.com/CLOCTools/lds-ctrl-est/tree/master/python/examples/eg_plds_switched_ctrl.py
[glds_fit_py]: https://github.com/CLOCTools/lds-ctrl-est/tree/master/python/examples/eg_glds_fit.py
[plds_fit_py]: https://github.com/CLOCTools/lds-ctrl-est/tree/master/python/examples/eg_plds_fit.py

[glds_fit_mat]: https://github.com/CLOCTools/lds-ctrl-est/tree/master/matlab/test_glds_fit.m
[plds_fit_mat]: https://github.com/CLOCTools/lds-ctrl-est/tree/master/matlab/test_plds_fit.m

<details markdown="1"><summary>RTXI modules:</summary>

  - [rtxi-gldsController](https://github.com/CLOCTools/rtxi-gldsController)
  - [rtxi-pldsSimulator](https://github.com/CLOCTools/rtxi-pldsSimulator)
  - [rtxi-pldsSwitchedController](https://github.com/CLOCTools/rtxi-pldsSwitchedController)

</details>


### **Latent-switch decoding** (HMM) [`CLOCTools/hmm`](https://github.com/CLOCTools/hmm)

<img src="/figures/hmmlogo_center_white.png" height=150>

hmm is a simple set of hidden Markov model (HMM) code intended to support control of switching linear dynamical systems. It contains methods for generating and decoding systems with discrete latent states and discrete observed signals.

  - [code](https://github.com/CLOCTools/hmm), [documentation](https://CLOCTools.github.io/hmm/)
  - example script with build, simulate, and decode - [`test/main.cpp`](https://github.com/CLOCTools/hmm/blob/master/misc/test-cmake-installation/src/main.cpp), [tutorial](https://CLOCTools.github.io/hmm/_tutorial.html)
  - RTXI modules:
    - [rtxi-hmmDecoder](https://github.com/CLOCTools/rtxi-hmmDecoder)
    - [rtxi-hmmGenerator](https://github.com/CLOCTools/rtxi-hmmGenerator)

<!-- ### Local field potential (LFP) decoding
https://github.com/CLOCTools/lfp-cpp-library
https://github.com/CLOCTools/lfp-cpp-library/blob/master/src/lfpRatiometer.cpp -->

### State-aware (switched) control of neural dynamics (StAC)
StAC allows for model-based control and estimation of a switched (PLDS) system. It relies on the [CLOCTools/ldsCtrlEst](https://github.com/CLOCTools/lds-ctrl-est) and [CLOCTools/hmm](https://github.com/CLOCTools/hmm) libraries.
Building a switched control loop is demonstrated at [`eg_plds_switched_ctrl.cpp`](https://CLOCTools.github.io/lds-ctrl-est/docs/tutorials/eg_switched_plds_control/), an RTXI wrapper for switched control of a PLDS system suitable for custom decoding is available at [rtxi-pldsSwitchedController](https://github.com/CLOCTools/rtxi-pldsSwitchedController), and an RTXI wrapper for switched control of a PLDS using an HMM for decoding is available at [rtxi-StAC](https://github.com/CLOCTools/rtxi-StAC). *See also section [Satellite:StAC](#stac-analysis--manuscript-figures) for analysis code and manuscript figures.*

## Implementation tools

### Cross-language utilities

CLOCTools makes use of a variety of programming languages. This section lists tools to interface across these languages.

- [eg-cpp-library](https://github.com/CLOCTools/eg-cpp-library) - An example repository for C++ library development
- [lds-ctrl-est-pybind](https://github.com/CLOCTools/lds-ctrl-est/tree/master/python/ldsctrlest) - python bindings to ldsCtrlEst core C++ functionality
- [lds-ctrl-est-matlab](https://github.com/CLOCTools/lds-ctrl-est/tree/master/matlab) - MATLAB implementations, bindings to ldsCtrlEst
- [cpp-matlab-demos](https://github.com/CLOCTools/hmm/tree/master/matlab) - using mex to verify algos in c++ *(currently a part of the HMM repository)*

### Real-time utilities

In order to make use of real time utilities, a variety of wrappers and signal processors are needed.  Repositories for these wrappers and signal processors relevant to particular tools are listed in the sections with those tools, while more general repositories for real time utilities are listed in this section.

#### <img alt='RTXI' src="figures/RTXI_logo.png" height=90 style='border:15px solid #ffffff00'>

[RTXI](http://rtxi.org/), the Real-Time eXperiment Interface, is a hard real-time data acquisition and control application for biological research. At its core is a Real-Time Operating System (RTOS), which uses a modified Linux kernel to provide deterministic control in a variety of experimental settings. RTXI is a fast, free, and open-source system currently used in labs all over the world to probe diverse, technologically challenging problems, such as dynamic probing of ion-channel function, control of cardiac arrhythmia dynamics, and control of deep-brain stimulation patterns.  We have repositories with useful tools for interfacing with and configuring RTXI.

- [rtxi-settings](https://github.com/CLOCTools/rtxi-settings) -  RTXI experiment settings   
- [stimLoader](https://github.com/CLOCTools/rtxi-stimLoader) - Stimulus and parameter I/O 

<details markdown="1"><summary>RTXI signal processing modules  </summary>  
  
- https://github.com/old-rtxi-utilities
- [quantizer](https://github.com/old-rtxi-utilities/rtxi-quantizer)
- [gain modulation](https://github.com/old-rtxi-utilities/rtxi-gain_mod)
- [limiter](https://github.com/old-rtxi-utilities/rtxi-limiter)
- [nonlinearity & spiking](https://github.com/old-rtxi-utilities/rtxi-nonlin_spike)
  
</details>

#### <img alt="TDT" src="figures/TDT-LOGO-BLACK-TEXT_400.png" height=60 style='border:15px solid #ffffff00'>

Tucker Davis Technologies ([TDT](https://www.tdt.com/)) have a variety of hardware and software solutions for neuroscience.  We have repositories with useful tools for interfacing with TDT hardware and software. 

TDT utilities:

  - [rtxi-tdtSpikes](https://github.com/CLOCTools/rtxi-tdtSpikes) - retrieve spike counts from TDT
  - [rtxi-tdtLFP](https://github.com/CLOCTools/rtxi-tdtLFP) - receive local field potential (LFP)
  - [tdtUDP](https://github.com/CLOCTools/tdtUDP) - A repository for receiving/sending data through Tucker Davis Technologies UDP interface

## Related publications
[**CLOC Tools: A Library of Tools for Closed-Loop Neuroscience**](https://github.com/CLOCTools/tools-for-neuro-control-manuscript)<br>
A.A. Willats, M.F. Bolus, K.A. Johnsen, G.B. Stanley, and C.J. Rozell. *In prep*, 2022.

[**State-Aware Control of Switching Neural Dynamics**](https://github.com/awillats/state-aware-control)<br>
A.A. Willats, M.F. Bolus, C.J. Whitmire, G.B. Stanley, and C.J. Rozell. *In prep*, 2022.

[**Closed-Loop Identifiability in Neural Circuits**](https://github.com/awillats/clinc)<br>
A. Willats, M. O'Shaughnessy, and C. Rozell. *In prep*, 2022.

[**State-space optimal feedback control of optogenetically driven neural activity**](https://www.biorxiv.org/content/10.1101/2020.06.25.171785v2)<br>
M.F. Bolus, A.A. Willats, C.J. Rozell and G.B. Stanley. *Journal of Neural Engineering*, 18(3), pp. 036006, March 2021.

[**Design strategies for dynamic closed-loop optogenetic neurocontrol in vivo**](https://iopscience.iop.org/article/10.1088/1741-2552/aaa506)<br>
M.F. Bolus, A.A. Willats, C.J. Whitmire, C.J. Rozell and G.B. Stanley. *Journal of Neural Engineering*, 15(2), pp. 026011, January 2018.

## Satellite repositories 
These projects contain related work that doesn't necessarily fit into the primary focus of CLOCTools or have their own goals separate from CLOCTools.  They are listed here for completeness and relevance.  Of particular importance is CLEOSim which can serve to test the algorithms in ldsCtrlEst and hmm and to prototype experiments in-silico.
### StAC (analysis & manuscript figures)
[StAC](https://github.com/awillats/state-aware-control) - State-aware control of switching neural dynamics.  StAC applies control, decoding, and estimation to switching models of neural responses. Hidden Markov models and Poisson linear dynamical systems are used to design and characterize feedback in simulation and are compared to non-switching “state-naive” approaches. Real-time implementation is provided by [CLOCTools/rtxi-StAC](#state-aware-switched-control-of-neural-dynamics-stac), however [CLOCTools/state-aware-control-manuscript](https://github.com/awillats/state-aware-control) contains additional simulations, analysis, and plotting (in MATLAB) for the associated manuscript *(in preparation)*.
<!-- will get transferred over to CLOCTools/state-aware-control -->


<!-- <img src="/figures/Cleo_logo.png" height=90 style='border:15px solid #ffffff'> -->
<h4>
<img 
    alt="Cleo"
    style="display: block; border:15px solid #ffffff00;"
    height=90
    src="https://user-images.githubusercontent.com/19983357/187561700-100b853a-d226-4039-a580-1d798b00f9e4.png" 
    alt="logo">
</h4>

[Cleo](https://github.com/Sensory-Information-Processing-Lab/cleosim) (Closed-Loop, Electrophysiology, and Optogenetics experiment simulation testbed) is a Python package built on the Brian 2 spiking neural network simulator developed bridging theory and experiment for mesoscale neuroscience, facilitating electrode recording, optogenetic stimulation, and closed-loop experiments.  In conjunction with implementation tool sets such as ldsCtrlEst Python bindings, Cleo can also serve to prototype closed-loop experiments in silico and to test control algorithms on various models of mesoscale neural activity.


<p align="center">
  <img 
      style="display: block; 
             width: 100%;"
      src="https://user-images.githubusercontent.com/19983357/187723498-f0f03da8-096a-46eb-90df-28da55dce7a0.png" 
      alt="CLOCTools and Cleo">
</p>

- [code](https://github.com/Sensory-Information-Processing-Lab/cleosim), [documentation](https://cleosim.readthedocs.io/en/latest/)


<details markdown="1"><summary>tutorials:</summary>

  - [PI Control](https://github.com/kjohnsen/cleosim/blob/master/docs/tutorials/PI_ctrl.ipynb)
  - [electrode setup](https://github.com/kjohnsen/cleosim/blob/master/docs/tutorials/electrodes.ipynb)
  - [on-off control](https://github.com/kjohnsen/cleosim/blob/master/docs/tutorials/on_off_ctrl.ipynb)
  - [optogenetics](https://github.com/kjohnsen/cleosim/blob/master/docs/tutorials/optogenetics.ipynb)
  - [LQR Control using ldsCtrlEst](https://github.com/kjohnsen/cleosim/blob/master/docs/tutorials/lqr_ctrl_ldsctrlest.ipynb)
</details>

### CLINC
[CLINC](https://github.com/awillats/clinc) - Closed-loop identifiability in neural circuits. This project proposes a framework for understanding the impact of open and closed-loop interventions in identifying neural circuits. This manuscript (in preparation) summarizes the role of stimulation in circuit inference and demonstrates how to design interventions through simple gaussian network simulations. See also [https://github.com/awillats/brian_delayed_gaussian](awillats/brian_delayed_gaussian) for simulating networks of Gaussian nodes with delayed connections in the Brian2 simulator framework.
