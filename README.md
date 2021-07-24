# Neural Net Basics

Neural network neuron is a storage unit that stores a number or a "signal". Our neurons in our brain in addition to having a storage unit, also have their own computation unit. A neural network neuron has the computation unit outside it along with a weight (a number) for each neuron. A NN neuron stores the result of the computation of its input based on the weight and the activation function.

How are weights initialized?
Weights are initialized based on Gaussian or normal distribution (random-normal) with zero-mean and a calculated variance (smaller weights). The intuition behind the generalization of a NN is about learning from the input distribution. The weights should follow a normal distribution (or something similar) such that as it learns during the training it is able to converge better. The scale of the initial weight distribution affects the convergence of the network. The smaller the scale, better the convergence.

Using weights as constant values hinders convergence mainly because of vanishing/exploding gradients.

What is "loss" in a neural network?
The difference between the NN output and the ground truth output. The loss function determines the learning (training) outcome in a NN. A loss function shows the NN the gaps that it needs to fill/learn, such that it is able to perform a particular task.

### Let us see forward and backward pass of a small Neural network in MS Excel.

![Network Structure](https://user-images.githubusercontent.com/39134120/118151499-535e0580-b431-11eb-9248-c29fef488986.JPG)


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

Follwing are the values calculated for different parameters of the above shown Neural network.

![NN parameters](https://user-images.githubusercontent.com/39134120/126879579-725ee132-39f2-4fd2-ba0c-db2dff80dba9.JPG)


We know that the chain rule is used for calculating the derivative of composite functions. If a variable z depends on the variable y, which itself depends on the variable x, so that y and z are dependent variables, then z, via the intermediate variable of y, depends on x as well. This is called the chain rule.Just like this the input/hidden layer neuron has impact on the final output obtained in the final layer.The weights associated with the input/hidden layer is optimized via their association with the output layer which itself updated via loss calculated from difference between predicted and actual value.



<img width="745" alt="backprop-1" src="https://user-images.githubusercontent.com/39134120/126879428-83ffae65-f3f7-4ab7-ae9b-0644ee2f30a3.png">


So using above concept when we calculated values for different parameters we got the following -

![Weight_calc1](https://user-images.githubusercontent.com/39134120/118123847-70371080-b412-11eb-845d-3eb86bb9555d.JPG)
![Weight_calc2](https://user-images.githubusercontent.com/39134120/118123881-79c07880-b412-11eb-8126-b233d1d70596.JPG)
![Weight_calc3](https://user-images.githubusercontent.com/39134120/118123906-804ef000-b412-11eb-91e1-61adcdb872ed.JPG)
![Weight_calc4](https://user-images.githubusercontent.com/39134120/118123929-8644d100-b412-11eb-9847-e6c8b4b9a8db.JPG)

We used learning rate of 0.5<br>
![learning rate](https://user-images.githubusercontent.com/39134120/118124146-cdcb5d00-b412-11eb-9d30-f60148954141.JPG)

After using the formula obtained by applying chain rule for backward pass and running for 39 epochs (dragged the formula to 39 observations) we got the following.
![final_weights](https://user-images.githubusercontent.com/39134120/118124503-4df1c280-b413-11eb-9f91-e50b06e121a5.JPG)

when we plot the error rate with respect to the number of epochs we got the following graph.
![Trained network_Error_vs_Epochs](https://user-images.githubusercontent.com/39134120/118124626-7a0d4380-b413-11eb-9731-d38dfdc88444.JPG)

We tried with different learning rate and following are the graphs for different learning rates.

Learning rate =0.1<br>
![learning_rate0 1](https://user-images.githubusercontent.com/39134120/118125674-ec325800-b414-11eb-88aa-820b2f328e23.JPG)

The network is not converging fast enough due to low learning rate.

Learning rate =0.2 <br>
![learning_rate0 2](https://user-images.githubusercontent.com/39134120/118125803-12f08e80-b415-11eb-9319-b796cab89ccc.JPG)

Better convergence compared to learning rate of 0.1 but still network not converging fast enough due to low learning rate.

Learning rate =0.5<br>
![learning_rate0 5](https://user-images.githubusercontent.com/39134120/118127381-3e747880-b417-11eb-947a-534b35a86fb4.JPG)

Better convergence of network at learning rate of 0.5 compared to 0.1 and 0.2.

Learning rate =0.8<br>

![learning_rate0 8](https://user-images.githubusercontent.com/39134120/118126206-a5912d80-b415-11eb-9fba-14b0c5295f05.JPG)

Better convergence of network at learning rate of 0.8 compared to 0.1,0.2 and 0.5.

Learning rate =1<br>
![learning_rate1](https://user-images.githubusercontent.com/39134120/118126555-1fc1b200-b416-11eb-98ba-0dc28a0494ce.JPG)

Better convergence of network compared to learning rate of 0.1,0.2,0.5 and 0.8. Since this is a small network learning rate of 1 is giving 
good convergence but it is not advisable to start with learning rate of 1 for neural network with more number of layers.

Learning rate =2<br>

![learning_rate2](https://user-images.githubusercontent.com/39134120/118126820-7cbd6800-b416-11eb-8c6a-d388f6f8d94a.JPG)

Better convergence of network compared to all previous learning rates. Since this is a small network learning rate of 2 is giving 
good convergence but it is not advisable to start with learning rate of 2 for neural network with more number of layers.










