# Developing a Neural Network Regression Model
## Reg no:212223230188
## Name:Sanjay V

## AIM
To develop a neural network regression model for the given dataset.

## THEORY

The objective of this experiment is to design, implement, and evaluate a Deep Learning–based Neural Network regression model to predict a continuous output variable from a given set of input features. The task is to preprocess the data, construct a neural network regression architecture, train the model using backpropagation and gradient descent, and evaluate its performance using appropriate regression metrics such as Mean Squared Error (MSE), Mean Absolute Error (MAE), and R² score.

The experiment aims to understand the impact of different hyperparameters such as learning rate, number of hidden layers, and activation functions on model performance. It also focuses on improving the model’s generalization ability by applying techniques like normalization, regularization, and validation. Finally, the experiment helps in gaining practical knowledge of implementing deep learning models for real-world regression problems.

## Neural Network Model

<img width="985" height="597" alt="Screenshot 2026-04-24 112940" src="https://github.com/user-attachments/assets/80b2114e-aec4-478f-a82e-b2691340fae0" />


## DESIGN STEPS
### STEP 1: 

Create your dataset in a Google sheet with one numeric input and one numeric output.

### STEP 2: 

Split the dataset into training and testing.

### STEP 3: 

Create MinMaxScalar objects ,fit the model and transform the data.

### STEP 4: 

Build the Neural Network Model and compile the model.

### STEP 5: 

Train the model with the training data.

### STEP 6: 

Plot the performance plot.

### STEP 7: 

Evaluate the model with the testing data.

### STEP 8: 

Use the trained model to predict  for a new input value .

## PROGRAM

### Name: Sanjay V

### Register Number: 212223230188

```python
class NeuralNet(nn.Module):
    def __init__(self):
        super().__init__()
        #Include your code here
        self.fc1=nn.Linear(1,8)
        self.fc2=nn.Linear(8,10)
        self.fc3=nn.Linear(10,1)
        self.relu=nn.ReLU()
        self.history={'loss': []}
    def forward(self,x):
    x=self.relu(self.fc1(x))
    x=self.relu(self.fc2(x))
    x=self.fc3(x)
    return x

# Initialize the Model, Loss Function, and Optimizer
    lig=NeuralNet()
    criterion=nn.MSELoss()
    optimizer=optim.RMSprop(lig. parameters(),lr=0.001)

    def train_model(ai_brain, X_train, y_train, criterion, optimizer, epochs=2000):
        #Include your code here
        for epoch in range(epochs):
           optimizer.zero_grad()
           loss=criterion(ai_brain(X_train),y_train)
           loss.backward()
           optimizer.step()
           ai_brain.history['loss'].append(loss.item())
           if epoch % 200 == 0:
              print(f'Epoch [{epoch}/{epochs}], Loss: {loss.item():.6f}')

    train_model(lig, X_train_tensor, y_train_tensor, criterion, optimizer)
```

### Dataset Information
<img width="201" height="259" alt="image" src="https://github.com/user-attachments/assets/4d6a31a1-f02d-49f6-a9ca-30a881fb8906" />



### OUTPUT

### Training Loss Vs Iteration Plot
<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/2139e46d-7819-40a5-bc85-10bffc5c8705" />


### New Sample Data Prediction
<img width="314" height="36" alt="image" src="https://github.com/user-attachments/assets/f470ac97-35ab-4bba-bf83-9de76ed523d7" />




## RESULT
Thus, a neural network regression model was successfully developed and trained using PyTorch.
