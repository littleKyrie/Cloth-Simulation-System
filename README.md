# Cloth Simulation System
## Introduction
In this case, we will see a piece of cloth falling down and colliding with a ball.

This task is based on Unity.

## Representation
We can use a simple mass-spring system to represent the cloth. 
Specifically, the cloth is presented as a structured triangular mesh. 

## Dynamics
We can choose to use implicit integral or position based dynamics to achieve the effects. 

## Implicit Solver
At the beginning, we set up the initial position X of the first iteration and the other one of the initial state by explicit integral.

After that, calculate the gradient such as the internal spring forces and the external gravities for every vertices.

Third, we consider the Hessian as a simple diagonal matrix to update the postion.
We compute the gradient and updated all the vertices with Hessian in every iterations.

After several iterations, we update the velocity. 

## PBD
We choose to use Jacobi solver.

First, we update the positions and velocities by explicit integral.

After that, we calculate the sum of position of its neighboring vertices for each endpoint and count the number of neighbors

After several iteration of the previous step, we update positions and velocities.

## Colision
Simple SDF collision detection between ball and cloth and impulse method to response it.

## Interaction
User can drag the ball by mouse to simulate the effects of collision.

## Effects
<img width="413" alt="image" src="https://user-images.githubusercontent.com/53171201/209613252-691fa177-b780-44f4-928e-97ce3d1a01c0.png">
