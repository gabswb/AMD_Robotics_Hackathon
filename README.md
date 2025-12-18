# AMD Open Robotics Hackathon 2025

Pick, Scans, Sort.

## Team Information

**Team:** *Stereobot*: Thomas Gaviard, Haoran Wang and Gabriel Schwab

**Summary:** *Two arms, one model to rule them both. Our bi-manual robot picks, scans, and sorts packages autonomously—an end-to-end, modular solution built for accurate and scalable warehouse automation.*

https://github.com/user-attachments/assets/432d1f3d-6a5f-4893-bd81-b893cff9afdf

## Submission Details

### 1. Mission Description
- Our mission demonstrates a real-world warehouse automation use case through a candy warehouse scenario, where a bi-manual robotic system autonomously picks and scans items with one arm and hands them off to a second arm for accurate sorting and packaging, showcasing a modular, end-to-end solution for high-throughput fulfillment.

### 2. Creativity
- Our approach is novel in that we use a single unified model to coordinate a bi-manual robotic task, enabling seamless handoff between picking, scanning, and sorting. The system is fully modular and easy to use, remaining independent of specific scanning or sorting technologies while maintaining high accuracy. By design, it is low-cost and adaptable, allowing the same framework to be deployed across different hardware setups and warehouse workflows without reengineering.

### 3. Technical implementations
- *Dataset capture*

https://github.com/user-attachments/assets/44792dfd-e260-454e-b1d6-f775cea8e952

- *Training*
We trained ACT on a compact dataset of 150 episodes using one top camera, one scan-state camera, and two arm-mounted cameras, following the LeRobot training recipe for 35K steps on AMD MI300X. To improve robustness, we fine-tuned the model on 30 failure-case episodes.

- *Inference*
AMD Ryzen AI 9 HX370 PC
OS: ubuntu 24.04
ROCm v6.3+
PyTorch v2.7.x
LeRobot: v0.4.1

### 4. Ease of use
- Generalization: The model successfully generalizes to all trained objects and also to new, previously unseen objects.
- Flexibility & Adaptability: The system is fully independent of specific scanning or warehouse setups and operates solely on color feedback for sorting decisions.
- Control Interface: The robot requires minimal inputs—color feedback, an inference script, and items to pick up—making deployment simple and low overhead.

## Additional Links
Video showcase the high accuracy of our solution:

https://github.com/user-attachments/assets/6aad2e10-6287-481a-ba9a-de118a41c07e

Model weights on HuggingFace: [https://huggingface.co/tms-gvd/act-finetune-35k](https://huggingface.co/tms-gvd/amd-act-v3)

Datasets: 
- [https://huggingface.co/datasets/tms-gvd/scan-v2-merged-01-02-fix0-cycling](https://huggingface.co/datasets/tms-gvd/amd-bimanual-core)
- [https://huggingface.co/datasets/tms-gvd/scan-v2-cycling-30](https://huggingface.co/datasets/tms-gvd/amd-bimanual-finetune)
