

Kinematic Modeling of Collective Biological Motion: The Pine Processionary Algorithm
Overview
This project explores the mathematical modeling and computational simulation of the collective movement exhibited by the Pine Processionary (Thaumetopoea pityocampa). In nature, these larvae move in a continuous, single-file "procession," where each individual maintains precise coordination with the one ahead of it.
The project aims to translate this biological behavior into a multi-agent kinematic system. This has practical applications in swarm robotics, autonomous vehicle platooning, and path-finding algorithms where agents must navigate complex terrains while maintaining structural cohesion.
Problem Statement
Modeling a procession involves solving three primary challenges:
1. Connectivity: Ensuring each agent follows the exact path of its predecessor with minimal "string instability" (the amplification of small movements as they travel down the line).
2. Terrain Adaptation: Using 3D rotations to ensure the "group" conforms to the geometry of the environment (e.g., the bark of a tree).
3. Kinematic Constraints: Maintaining a constant distance between segments while allowing for fluid, non-linear movement.
Mathematical Framework
To provide a rigorous analysis, the project implements the following concepts:
* Follow-the-Leader Dynamics: We model the system as a series of coupled differential equations. Each agent $i$ updates its state based on a pursuit-evasion manifold relative to agent $i-1$.
* Quaternion-Based Orientation: To handle 3D spatial orientation without the risk of gimbal lock, we use Quaternions ($q = w + xi + yj + zk$) to represent the local frame of each segment.
* B-Spline Interpolation: The leader's path is treated as a continuous curve. We apply cubic splines to ensure the followers move along a smooth trajectory rather than a jagged, discrete set of points.
* Computational Complexity: The project includes an analysis of $O(n)$ scaling for real-time simulation of large processions.
Technical Implementation
The simulation is built using Python, leveraging its powerful scientific ecosystem:
* NumPy: Used for high-dimensional vector math and matrix transformations.
* SciPy: Utilized for spatial calculations and spline-based path smoothing.
* Matplotlib / Pygame: Provides the engine for real-time 2D and 3D visualization.
Project Goals
* Implement a robust Lead-Follower class structure.
* Simulate the "wave effect" of movement delays within the chain.
* Export kinematic data for analysis of path efficiency vs. chain length.

