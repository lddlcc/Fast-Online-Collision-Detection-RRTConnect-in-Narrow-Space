#  Robotic Arm Path Planning in Narrow Spaces Using Fast Collision Detection of High-dimensional Configurations
The proposed algorithm addresses the critical bottlenecks of low efficiency and success rate in narrow passage scenarios by introducing an **online, learning-based fast collision detection module** that runs in parallel with the RRTConnect path search framework.  

##  Algorithm Overview
The core of our method enhances the RRTConnect planner by integrating a novel fast collision detection module. The algorithm begins with the standard RRTConnect framework as its search backbone, while concurrently constructing a balanced dataset through heuristic sampling that strategically explores both collision and free configurations in narrow spaces. This addresses the critical data imbalance issue inherent in uniform sampling. Subsequently, online clustering techniques model the distribution of these configurations within the high-dimensional C-Space. The key innovation lies in transforming traditional geometric collision checks into efficient distance calculations: for any new configuration, the algorithm simply computes its distance to the pre-clustered collision and free models, using a distance-based criterion to rapidly infer collision status. This parallel architecture significantly reduces planning latency while maintaining high path quality in constrained environments.

The codebase is currently being organized and documented for public release.

## Required Packages:
OMPL, https://ompl.kavrakilab.org/index.html, for planner setup.

MoveIt, https://moveit.ai/, for narrow environment setup.

Armadillo, https://arma.sourceforge.net/, for matrix operations.

mlpack, https://www.mlpack.org/index.html, for Spherical K-means Clustering



https://github.com/user-attachments/assets/74b3401c-8c7c-4828-adab-82013f225d8b

