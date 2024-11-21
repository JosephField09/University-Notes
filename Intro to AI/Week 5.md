
Artificial intelligence:
- Any technique which enables computers to mimic human behaviour

Machine learning:
- AI techniques that give computers the ability to learn without being explicitly programmed to do so
- Is a subset of AI and consists of the more advanced techniques and models that enable computers to figure things out from the data and deliver AI applications
- It is the science of getting computers to act without being explicitly programmed to
- Popular one is predictive text

Deep learning:
- A subset of ML which make the computation of multi-layer neural networks feasible
- Delivered high accuracy tasks such as object detection, speech recognition, language translation


<u>
What is machine learning?</u>
- [Arthur Samuel, 1959]: Field of study that gives computers the ability to learn from data without being explicitly programmes
- A branch of AI in which computer automatically improves performance from experience
- [Tom Mitchell, 1998]: A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T as measured by P, improves with experience E.

![[Pasted image 20241024143423.png]]

- Conventional/traditional computer programs or algorithms perform tedious tasks faster and more accurately than humans (addition, subtraction, spell-checking)

- Machine learning algorithms perform tasks that are difficult or infeasible to do via conventional/traditional computer algorithms (grammar checking, interpreting speech, image recognition)

Machine Learning applications:
![[Pasted image 20241024143639.png]]


ML for Fraud Prevention:
- Anomaly detected (unusual purchases/locations)
- Historical purchase data (data mining)
- Pattern Extraction from past purchase data sets
- Integrates user profile data (age, sex, job)
- Highly personalised

ML and face recognition:
- Locate the user's face in the image and delimit it with a bounding box
- Extract features from the face that can be used for the recognition task
- Make a face match with a database of vectors representing the visual features of the stored faces

Forms of Learning:
- Supervise Learning
	- Task driven
- Unsupervised Learning
	- Data Driven
- Reinforcement Learning
	- Learn from mistakes


<u>Supervised Learning</u>
- Where you have input variables (x) and an output variable (Y) and you use  and algorithm to learn the mapping function from the input to the output. Y = f(x)
- Goal is to approximate the mapping function so well that when you have new input data (x) that you can predict the output variables (Y) for that data.
- Names because the process of an algorithm learning from the training dataset can be thought of as a teacher supervising the learning process.

<u>Unsupervised Learning</u>
- Unsupervised learning is where you only have input data (X) and no corresponding output variables.
- Goal is to model the underlying structure or distribution in the data in order to learn about the data
- Names because unlike supervised learning above there is no correct answers and there is no teacher



<u>Supervised Learning (Most common)</u>
- We have access to a labelled dataset of input-output pairs: D = { x , y }
- Use an algorithm to learn the mapping function f from the input to the output
- Aim is to learn a predictive model f that takes an input x EX and aims to predict its corresponding output y EY
- The hope is that these example pairs can be used to "teach" 

<u>Mathematically defining the supervised learning problem:</u>
- Feature space: = $R^d$
	- Where d is the number of features
- Label space (class or target label): Y = {0,1} = {non-spam, spam}
- A classifier (hypothesis): h (A family of classifiers)
- Data: (x1, y1),...,(xn, yn)
- The task of machine learning:
	- A election problem to find a 
			h
		that "works well" on this problem

![[Pasted image 20241024152424.png]]

Training data:
- A dataset used to find potentially predictive relationships that will be used to create a model

Test data:
- A data set, separate from the training set but with the same structure, used to measure the performance of a model

Model:
- Mathematical representation of a real world process; a predictive model forecasts a future outcome based on past behaviours

Training:
- The process of creating a model from the training data. The data is fed into the training algorithm, which learns a representation for the problem and produces a model. 
- Also called "learning"


Feature:
- Independent variable or predictor variable, it is an observable quantity, recorded and used by a prediction model. 
- You can also engineer features by combining them or adding new information to them.

Target:
- Dependant on the variable; it is the output of the model or the variable you wish to predict

Classification:
- Predicting a category label (e.g. spam or non-spam)

Regression:
- Predicting a numerical/continuous label (e.g. price)



<u>Inductive learning</u>

Simplest form: lean a function from examples (tabula rasa)

- f is the target function
- An example is pair x, f(x), e.g.,
- Problem: find a(n) hypothesis h
	such that h = f
	given a training set of examples


- Overfitting is an undesirable machine learning behaviour that occurs when the machine learning model gives accurate predictions for training data but not for new data.


<u>Regression vs Classification</u>
- In regression the model predicts a continuous outcome variable (y) based on the value of one or multiple predictor variables (x).
	- e.g. price prediction

- In classification, the label is a categorical variable
	- e.g. the task of predicting the types of residence

![[Pasted image 20241024155118.png]]

<u>Define an ML problem</u>

- Choose an unsolved problem 
- Should be something that can't be easily solved mathematically or something which is vert difficult to do or requires special knowledge
- Ideally it should be focused on finding a pattern, a set of features or a way of classifying groups
- Need to choose a problem with lots of training or exemplar data where the answer is known or mostly known

<u>Construct your dataset</u>

- Must obtain your data from reliable sources 
- Needs to be labelled data (categorical, nominal or numerical) where labels are gold-standard "answers"
- Needs to have relevant parameters that you think or you know contribute to the phenomenon

- Split data into training data and testing data

- No single "right" answer to amount of data required for machine learning
- At a minimum collect about 1000 samples
	- 10,000 - 100,000 for most "average" problems
	- 100,000 - 1,000,000 for "hard" problems

- 2/3 is the training data - used to train model
- 1/3 is the testing data - used to assess model
- During training the model must not see the test data - **EVER**

<u>Data preparation</u>

- Clean up the data (Remove repeats, fill in or impute missive values, reformat for compatibility, fix outliers, etc.) - data cleansing
- Select features, keep relevant data remove irrelevant data (intuition or statistics) - feature selection

- Feature selection:
	- Way of reducing the amount of data used in training an ML model
	- Way to automatically or manually select data features that contribute most to the prediction accuracy of the model

<u>Choose and train a model</u>

- AI machine learning approaches require the use or creation of certain kinds of models
- e.g.:
	- - Decision Trees/Random Forest
	- Artificial Neural Networks (ANNs)
	- Hidden Markov Models (HMMs)
	- Support Vector Machines (SVMs)
	- Genetic Algorithms (GAs)
	- Bayesian Networks (BNs)

- No a priori way of know which model is the best - often have to try many


<u>Test and validate your models</u>

- We can evaluate the predictions by comparing them to the expected results in the testing set, then calculate classification accuracy.
	- classification accuracy = correct predictions / total predictions
- We can evaluate the prediction results on a classification problem
- Number of correct and incorrect predictions are summarised with count values and broken down by each class

- "true positive" for correctly predicted event values
- "false positive" for incorrectly predicted event values
- "true negative" for correctly predicted no-event values
- "false negative" for incorrectly predicted no-event values

![[Pasted image 20241024162535.png]]

<u>Use the model to make predictions</u>

![[Pasted image 20241024162605.png]]
