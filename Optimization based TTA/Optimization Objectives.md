## Optimization Objectives
Methods that optimize based on unsupervised objectives constitute a classical category of Test-Time Adaptation(TTA) algorithms. These approaches are implemented through minimizing predictive uncertainty, adapting batch statistics, or leveraging density estimation, and are characterized by their reliance on label-free objective functions derived from model outputs or data distributions to align the model with the target domain without supervised signals. In subsequent discussions, we will systematically introduce unsupervised optimization-based Test-Time Adaptation(TTA) algorithms according to their different methodological approaches and analyze whether they are edge-friendly.
### entropy minimization
The essence of entropy-minimization Test-Time Adaptation (TTA) is to take information uncertainty as the optimization signal and realize model self-calibration under the test data distribution through source-free domain online optimization.  
##### Tent: Fully Test-time Adaptation by Entropy Minimization(ICLR2021)  

