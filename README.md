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

Implicit Integral

https://user-images.githubusercontent.com/53171201/209668793-25e5e3b1-e9c7-4dbc-b603-e7f637db54ea.mov

Comparison of PBD results for different iterations

k=1
<img width="259" alt="image" src="https://user-images.githubusercontent.com/53171201/209820514-0c18ad79-aeef-41ed-a1cb-58c73614b962.png">

K=10
<img width="254" alt="image" src="https://user-images.githubusercontent.com/53171201/209820604-5b9f6157-55d9-4b55-8620-14ec0e4c9300.png">

K=20
<img width="258" alt="image" src="https://user-images.githubusercontent.com/53171201/209820679-f11dafb9-10f2-4b33-87ba-4caf1f521fa2.png">

K=32
<img width="260" alt="image" src="https://user-images.githubusercontent.com/53171201/209820764-f9604967-81ad-4150-bf73-8f8de5876e37.png">

K=100
<img width="241" alt="image" src="https://user-images.githubusercontent.com/53171201/209820914-3c5dfe3f-f988-4003-87fc-66c76fb9f185.png">
