Classification problem:
- Problem of identifying which of a set of classes an observation (or observations) belongs to.
- e.g. filtering emails into "spam" or "non-spam"

The neuron as inspiration:
- Main parts:
	- Dendrites are where neurons receive input from other cells
	- Cell body or Soma is where information is processed
	- Axon is the output structure of a neuron
	- Synapses are the connection points of two nerve cells
![[Pasted image 20241114151954.png]]

- Artificial neurons:
	- Inputs with weights (Synapses)
		- Inputs are data values, weights represent the importance of each input
	- Summation unit (Soma)
		- Adds up the weighted inputs
	- Activation function for output (Axon)
		- Produces the final output based on summation, similar to a biological axon's output
	- Equation: $y = φ(w^Tx+b)$
		- Where φ is the activation function, $w$ the weights, $x$ the inputs and $b$ the bias term

- Activation Functions:
	- Describes various activation functions used to define the output of a neuron based on input values.
	- Control how a neuron "fires" and can vary depending on the task, such as binary classification or regression.

- Step Function: 
	- Used in binary classification by firing only if inputs exceed a threshold
- Sigmoid (Logistic Function): 
	- Smooth approximation of step function, output in [0,1]
	- Produces a smooth output between 0 and 1
	- Often used in binary classification
- ReLU (Rectified Linear Unit):
	- Common in regression, $f(x)=max(0,x)$
	- Outputs only positive values and is commonly used in deep learning
- Tanh:
	- Output range [-1,1]
	- Can help in stabilizing training in certain modules


<u>Perceptron Training Algorithm</u>
- Explains the process of training a perceptron by adjusting weights.
- This is the core of perceptron learning, showing how the model improves by minimising errors

Training steps:
1. Define inputs and Target Output:
	- Decide what the perceptron should learn.
2. Initialise weights:
	- Start with arbitrary weights and adjust them over time.
3. Error calculation and adjustment:
	- The model calculates the difference (error) between the actual and target output and updates weights based on this error
4. Adjustment Formula:
	- $w new​=w old​+αδx$ where $α$ is the learning rate and $δ$ is the error


<u>Perceptron Limitations</u>

- Describes the inherent limitations of perceptron's, especially the inability to solve non-linearly separable problems.
- This sets up the need for multi-layer networks and deep learning

- Linear Separability:
	- Single-layer perceptrons can only solve problems where the classes are linearly separable
	- e.g. XOR Problem:
		- Classic example that a single perceptron cannot solve because its classes cannot be separated with a straight line
- Implication:
	- To handle more complex scenarios, we need multi-layer perceptrons and deep learning methods 


<u>Perceptron example:</u>

Goal: Model the Logical OR Operation with a Perceptron

- In a logical OR, the output is 1 if at least one of the inputs is 1
- Otherwise the output is 0

1. Define the structure of the perceptron
	- A perceptron has:
		- **Inputs** $x1$ and $x2$ (the values we feed into the perceptron)
		- **Weights** $w1$ and $w2$, which determine the influence of each input
		- **A bias term** $w0$ which shifts the decision boundary to help the perceptron make the correct classification
		- **An activation function** to decide the output based on the weighted sum of inputs and the bias. Here, we use the step function:      φ(z)={1​if z≥0, 0if z<0​ }

2. Set Initial Weights and bias
	- For an OR function, we can try:
		- w1 = 1
		- w2 = 1
		- w0 = -0.5
	- These weights and bias are chosen because they allow the perceptron to correctly classify all inputs for the OR operation

3. Calculate the Output for Each Input Combination
	- The perceptron calculates an output by finding the weighted sum of the inputs and applying the activation function
	- For any given inputs $x1$ and $x2$, the weighted sum is:
			$z=w1​⋅x1​+w2​⋅x2​+w0​$ 

	- Case 1: $x1 = 0, x2 = 0$
			$z=(1⋅0)+(1⋅0)+(−0.5)=−0.5$
		- Since -0.5 < 0, the output (after applying the step function) is 0

	- Case 2: $x1​=0, x2=1$
			$z=(1⋅0)+(1⋅1)+(−0.5)=0.5$
		- Since z = 0.5 ≥ -, the output is 1

	- Case 3: $x1​=1, x2=0$
			$z=(1⋅1)+(1⋅0)+(−0.5)=0.5$
		- Since z = 0.5 ≥ -, the output is 1

	- Case 4: $x1​=1, x2=1x$
			$z=(1⋅1)+(1⋅1)+(−0.5)=1.5$
		- Since z = 1.5 ≥ -, the output is 1

| Input x1​ | Input x2​ | Calculated z | Output |
| --------- | --------- | ------------ | ------ |
| 0         | 0         | -0.5         | 0      |
| 0         | 1         | 0.5          | 1      |
| 1         | 0         | 0.5          | 1      |
| 1         | 1         | 1.5          | 1      |

<u>Algorithmic Perceptron Training Example</u>

Goal: Train a Perceptron to Model the logical AND function

1. Initialise weights and bias
- We start with arbitrary values, often zeros:
	 w1 = 0, w2 = 0, w0 = 0

2. Define the activation function:
- We use the Step activation function to determine the output:
	 φ(z)={1 ​if z≥0, 0 if z<0​ }
- The perceptron will calculate a weighted sum $z=w1​x1​+w2​x2​+w0​$ and then apply the step function to produce the output

3. Learning rate (α)
- We set a learning rate of α =1. 
- This determines how much we adjust the weights on each iteration

4. Training Iterations (Epochs)
- For each input-output pair, we:
	1. Calculate the perceptron's output
	2. Compare it with the target output
	3. Update weights if the output is incorrect

Epoch 1 (First pass)
- Case 1: $x1 = 0, x2 = 0, target = 0$
	- Weighted sum $z = w1 ⋅ 0 + w2 ⋅ 0 + w0 = 0$
	- Output φ(z) = 0 (matches target), so no weight adjustment needed
- Case 2: $x1 = 0, x2 = 1, target = 0$
	- Weighted sum $z = w1 ⋅ 0 + w2 ⋅ 1 + w0 = 0$
	- Output φ(z) = 0 (matches target), so no weight adjustment needed
- Case 3: $x1 = 1, x2 - 0, target = 0$
	- Weighted sum $z = w1 ⋅ 1 + w2 ⋅ 0 + w0 = 0$
	- Output φ(z) = 0 (matches target), so no weight adjustment needed
- Case 4: $x1 = 1, x2 - 1, target = 1$
	- Weighted sum $z = w1 ⋅ 1 + w2 ⋅ 1 + w0 = 0$
	- Output φ(z) = 0 (incorrect, target is 1)
	- Adjust weights:
		- Calculate the error δ=Target−Output=1−0=1
		- Update the weights using the rule $wnew​=wold​+α⋅δ⋅x$
			- $w1​=0+1⋅1⋅1=1$
			- $w2​=0+1⋅1⋅1=1$
			- $w0​=0+1⋅1=1$

Epoch 2 (Second Pass)
- Now the weights are $w1 = 1, w2 = 2, w0 = 1$ 

- Case 1: $x1 = 0, x2 = 0, Target = 0$
	- Weighted sum z = 1
	- Output φ(z) = 1 (Incorrect, target is 0)
	- Adjust weights:
		- Error $δ=0−1=−1$
		- Update weights:
			- $w1​=1+(−1)⋅0=1$
			- $w2​=1+(−1)⋅0=1$
			- $w0​=1+(−1)=0$

- Case 2: $x1 = 0, x2 = 1, Target = 0$
	- Weighted sum z = 1
	- Output φ(z) = 1 (Incorrect, target is 0)
	- Adjust weights:
		- Error $δ=0−1=−1$
		- Update weights:
			- $w1​=1
			- $w2​=1+(−1)⋅1=0$
			- $w0​=0+(−1)=-1$ 

- Case 3: $x1​=1,  x2=0, Target =0$
	- Weighted sum z = 0
	- Output φ(z) = 0 (correct), so no adjustment

- Case 4: $x1​=1, x2=1, Target =1$
	- Weighted sum z = 1
	- Output φ(z) = 1 (correct), no adjustment

After repeating these steps over multiple epochs, the perceptron's weights converge to values that correctly classify all inputs in the AND truth table:

- Final weights might converge to $w1 = 1, w2 = 1, w0 = -1.5$

The perceptron now successfully models the AND function and outputs the correct result for all input combinations.

- This iterative process of adjusting weights based on errors allows the perceptron to "learn" the target function.