## Optimization Objectives
Methods that optimize based on unsupervised objectives constitute a classical category of Test-Time Adaptation(TTA) algorithms. These approaches are implemented through minimizing predictive uncertainty, adapting batch statistics, or leveraging density estimation, and are characterized by their reliance on label-free objective functions derived from model outputs or data distributions to align the model with the target domain without supervised signals. In subsequent discussions, we will systematically introduce unsupervised optimization-based Test-Time Adaptation(TTA) algorithms according to their different methodological approaches and analyze whether they are edge-friendly.
### entropy minimization
The essence of entropy-minimization Test-Time Adaptation (TTA) is to take information uncertainty as the optimization signal and realize model self-calibration under the test data distribution through source-free domain online optimization.  
- `Tent`[ICLR'2021]**Tent: Fully Test-time Adaptation by Entropy Minimization**[[paper](https://arxiv.org/abs/2006.10726)][[code](https://github.com/DequanWang/tent)]  
Tent is a Test-Time Adaptation(TTA) method that operates exclusively on the model and the current unlabeled test data. Its core principle is to minimize the Shannon entropy of the model’s predictions. This process dynamically tunes the affine parameters of the normalization layers, which in turn improves the model’s generalization performance under distribution shift.  
Edge-friendly&nbsp;✅   
Tent achieves its update in merely one forward and one backward pass, restricting optimization to the affine parameters of the normalization layers.
- `DSI`[CoRR'2019]**Dynamic Scale Inference by Entropy Minimization**[[paper](https://arxiv.org/pdf/1908.03182)]
DSI is a Test-Time Adaptation(TTA) algorithm designed to optimize the trade-off between accuracy and computational efficiency by dynamically selecting the model’s input scale. It employs prediction entropy as a confidence measure. Starting from the lowest resolution, the method incrementally scales the input. At each scale, the classification entropy is computed; if it drops below a set threshold, the current prediction is output and the inference is halted, thus avoiding the computational cost of processing higher resolutions.
Edge-friendly&nbsp;✅
DSI introduces a multi-resolution inference mechanism and an entropy-based early stopping mechanism. On the ImageNet dataset, it achieves a reduction of approximately 30% in average FLOPs at the cost of only a 0.1% drop in accuracy.


