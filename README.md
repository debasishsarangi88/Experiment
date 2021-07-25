# Neural Net Basics

### What is a Neuron?
Neural network neuron is a storage unit that stores a number or a "signal". Neurons in our brain in addition to having a storage unit, also have own computation unit. An artificial neural network neuron has the computation unit outside it along with a weight (a number) for each neuron. A NN neuron stores the result of the computation of its input based on the weight and the activation function.

### How are weights initialized?
Weights are initialized based on Gaussian or normal distribution (random-normal) with zero-mean and a calculated variance (smaller weights). The intuition behind the generalization of a NN is about learning from the input distribution. The weights should follow a normal distribution (or something similar) such that as it learns during the training it is able to converge better. The scale of the initial weight distribution affects the convergence of the network. The smaller the scale, better the convergence.

Using weights as constant values hinders convergence mainly because of vanishing/exploding gradients.

### What is "loss" in a neural network?
The difference between the NN output and the ground truth output. The loss function determines the learning (training) outcome in a NN. A loss function shows the NN the gaps that it needs to fill/learn, such that it is able to perform a particular task.

## What is "chain rule" in gradient flow ?

We know that the chain rule is used for calculating the derivative of composite functions. If a variable z depends on the variable y, which itself depends on the variable x, so that y and z are dependent variables, then z, via the intermediate variable of y, depends on x as well. This is called the chain rule.Just like this the input/hidden layer neuron has impact on the final output obtained in the final layer.The weights associated with the input/hidden layer is optimized via their association with the output layer which itself updated via loss calculated from difference between predicted and actual value.


Chain rule helps in find the partial derivative of a function A with respect to another function B, by using a function C

![chain-rule-1](https://user-images.githubusercontent.com/39134120/126879921-1d80c7b9-354d-44d3-b9fc-87b94fba4b36.png)

Chain rule helps in propagating the loss value from one layer to another such that a given NN's weight is changed with respect to the loss value.

![propagation](https://user-images.githubusercontent.com/39134120/126880076-48e47336-22b9-4c55-9ee1-9373dbfa03fa.png)

![propagation1-gif](https://user-images.githubusercontent.com/39134120/126880092-834226c8-30b1-4484-a99a-8db186c11cd2.gif)

Source: https://medium.com/@pavisj/convolutions-and-backpropagations-46026a8f5d2c

# Let us see forward and backward pass of a small Neural network in MS Excel

![NN_network](https://user-images.githubusercontent.com/39134120/126893872-89ff9e62-b36d-4d38-9e52-c54602e5f909.JPG)


The above image shows the architecture of the Neural network.<br>
We have considered a samller network with less layers as we are doing the entire excercise in MS Excel.<br>
i1 and i2 are the input layer neurons.<br>
h1 and h2 are the hidden layer neurons.<br>
a_h1 and a_h2 are activated outputs from hidden layer neuron h1 and h2.<br>
o1 and o2 are the neuron connected to the output layer.<br>
a_o1 and a_o2 are activated output of o1 and o2 neuron.<br>
E_total is the total error of the network.<br>
w1 and w3 are the weights from input layer neuron i1 to h1 and h2 respectively.<br>
w2 and w4 are the weights from input layer neuron i2 to h1 and h2 respectively.<br>
w5 and w7 are the weights from activated hidden layer neuron a_h1 to o1 and o2 respectively.<br>
w6 and w8 are the weights from activated hidden layer neuron a_h2 to o1 and o2 respectively.<br>

So using above concept when we calculated values for different parameters we got the following -
![NN parameters](https://user-images.githubusercontent.com/39134120/126879579-725ee132-39f2-4fd2-ba0c-db2dff80dba9.JPG)


<img width="745" alt="backprop-1" src="https://user-images.githubusercontent.com/39134120/126879428-83ffae65-f3f7-4ab7-ae9b-0644ee2f30a3.png">

![1st_level_wt_calc](https://user-images.githubusercontent.com/39134120/126893892-9948f9f9-d740-4ab1-8632-9de2a5baa64d.JPG)
![2nd_level_wt_calc](https://user-images.githubusercontent.com/39134120/126893897-dabf84bf-019a-4cfb-80fe-64bd1eef3d47.JPG)
![3rd_level_wt_calc](https://user-images.githubusercontent.com/39134120/126893899-8ecdc86b-3ce2-42a3-9350-7f6c9801256f.JPG)


We used learning rate of 0.5<br>


After using the formula obtained by applying chain rule for backward pass and running for 45 epochs (dragged the formula to 45 observations) we got the following.
First 21 epochs
![Weight_calc_excel1](https://user-images.githubusercontent.com/39134120/126894152-43714ee6-834a-4a3d-bbb8-1cb5cbbc6023.JPG)
Last 24 epochs
![Weight_calc_excel2](https://user-images.githubusercontent.com/39134120/126894159-4391784a-4bcb-4981-83d6-5b6dd295f333.JPG)


when we plot the error rate with respect to the number of epochs we got the following graph.
![Error vs epoch](https://user-images.githubusercontent.com/39134120/126896146-ca0d2f30-3eb9-4a28-9230-52f99b4c55cc.JPG)



We tried with different learning rates and we can see the result in below graph.
![Error vs epoch_LR](https://user-images.githubusercontent.com/39134120/126895570-a42772a9-3a3e-43ca-b0f8-3282c484b429.JPG)



Learning rate =0.1<br>
The network is not converging fast enough due to low learning rate.

Learning rate =0.2 <br>
Better convergence compared to learning rate of 0.1 but still network not converging fast enough due to low learning rate.

Learning rate =0.5<br>
Better convergence of network at learning rate of 0.5 compared to 0.1 and 0.2.

Learning rate =0.8<br>
Better convergence of network at learning rate of 0.8 compared to 0.1,0.2 and 0.5.

Learning rate =1<br>
Better convergence of network compared to learning rate of 0.1,0.2,0.5 and 0.8. Since this is a small network learning rate of 1 is giving 
good convergence but it is not advisable to start with learning rate of 1 for neural network with more number of layers.

Learning rate =2<br>
Better convergence of network compared to all previous learning rates. Since this is a small network learning rate of 2 is giving 
good convergence but it is not advisable to start with learning rate of 2 for neural network with more number of layers.










