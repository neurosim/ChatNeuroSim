# Query Examples for ChatNeuroSim
This document provides representative Compute-in-Memory (CIM) query examples supported by ChatNeuroSim.
The queries are categorized into four major interaction modes:
+ Single Call
+ Multiple Call
+ Testbench Auto-design
+ PPA Optimization

These examples demonstrate how users can interact with the framework to perform simulation, evaluation, comparison, and automated design-space exploration for CIM architectures.

**You can freely design your own CIM queries, including device-circuit-architecture configurations, benchmarking, or optimization objectives. ChatNeuroSim will automatically interpret your request and orchestrate the complete simulation and optimization workflow.**

**1. Single Call**
+ Single testbench and one simulation with one fixed set of parameters.
+ Example: I want to simulate VGG8 on CIFAR-10 on CIM architecture using 8b quantization for both input and weight. I only want to get the PPA estimation. The memory device is 22nm RRAM with 1bit cell precision. The state conductances are 25uS and 167uS with no variations. The subarray size is 128x128 and ADC precision 7bit.

**2. Multiple Call**
+ Multiple testbenches and simulations with different user’s specified parameter values.
+ Example: I want to simulate VGG8 on CIFAR-10 on CIM architecture using 8b quantization for both input and weight. I only want to get the PPA estimation under 22nm, 14nm, and 7nm tech node. The memory device is SRAM. The subarray size is 128x128 and ADC precision 7bit.
Multiple call queries require iterative interaction, comparison, or parameter adjustment across multiple simulations.

**3. Testbench Auto-design**
+ Multiple testbenches and simulations with user’s  specified parameter names but without specified parameter values.
+ Example: Check the accuracy drop of ResNet-18 on CIFAR-100 of different input and weight quantization precisions. Only simulate the accuracy without the PPA. Run 5 batches with the batch size 100. Use 1b cell with a subarray of 128x128 and 7b ADC.

**4. PPA Optimization**
+ PPA optimization request to find the best CIM configuration under constraints.
+ Example: I’d like to design an CIM chip within 3600mm$^2$ based on 22nm tech node running ResNet-50 on ImageNet with the minimum power consumption. Use simulate annealing to find out the optimal parameter combination of device type, ADC type, ADC precision, subarray size, subarray mux with 20 episodes.
