# Fast Online Collision Detection RRTConnect: Robotic Arm Path Planning in Narrow Spaces


This repository contains the implementation of **"Robotic Arm Path Planning in Narrow Spaces Using Fast Collision Detection of High-dimensional Configurations"**.

The proposed algorithm addresses the critical bottlenecks of low efficiency and success rate in narrow passage scenarios by introducing an **online, learning-based fast collision detection  module** that runs in parallel with the RRTConnect path search framework.

## 🚀 Key Features & Innovation

- **🚀 High-Speed Collision Detection**: Transforms traditional bounding-box-based collision checks into efficient distance calculations between a sampled configuration and pre-clustered models.
- **🧠 Online Learning**: Constructs a balanced dataset and trains the collision detection model on-the-fly during the planning process, adapting to specific narrow environments.
- **⚖️ Heuristic Balanced Sampling**: Overcomes the data imbalance issue of uniform sampling in narrow spaces, ensuring sufficient exploration of free configurations for robust model training.
- **⚡ Parallel Architecture**: The fast collision detection module runs concurrently with the RRTConnect planner, minimizing planning latency.
- **🎯 High Success Rate**: Significantly improves path planning success rates in challenging narrow spaces (simple, opened, and closed types).

## 📊 Algorithm Overview

The core of our method lies in augmenting the RRTConnect algorithm with a fast collision detection module.

1.  **Baseline Planner**: RRTConnect
2.  **Online Dataset Construction**: Uses a heuristic strategy to actively sample both collision and, more importantly, *free* configurations in narrow spaces, creating a balanced dataset.
3.  **Online Clustering**: Employs clustering algorithms (e.g., K-Means, GMM) to model the distribution of collision and free configurations in the high-dimensional C-Space.
4.  **Fast Collision Query**: For a new configuration, the algorithm calculates its distance to the collision and free clusters. A simple distance-based criterion is used to infer collision status, bypassing expensive geometric checks.

A simplified workflow: `RRTConnect Expansion → Candidate Configuration → FCD Module (Distance to Clusters) → Collision/Free Decision → Add to Tree or Discard`.

## Required Packages:

OMPL, https://ompl.kavrakilab.org/index.html, for planner setup
OpenCV, https://opencv.org/, for 2d environment setup.
ThunderSVM, https://github.com/Xtra-Computing/thundersvmfor, for learning Kernel-SVM.
Amino, https://github.com/golems/amino, for scene setup, viusalization and robot modeling.
NLOPT, https://nlopt.readthedocs.io/en/latest/, for solving optimization problems.
