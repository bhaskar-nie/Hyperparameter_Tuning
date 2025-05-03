# Hyperparameter Tuning with Keras Tuner

This project demonstrates how to use **Keras Tuner** to perform hyperparameter tuning on a neural network for binary classification using the **Pima Indians Diabetes Dataset**.

## Project Overview

The goal of this project is to automate the process of selecting the best hyperparameters for a neural network model. Hyperparameters such as the number of layers, number of units in each layer, activation functions, optimizers, and more can significantly affect the performance of a model. Instead of manually testing various combinations, **Keras Tuner** helps automate this process, which can lead to better-performing models with less effort.

## Dataset

The dataset used is the **Pima Indians Diabetes Database**, which contains medical information about patients, and the goal is to predict whether they have diabetes based on these features.

## Key Steps

### 1. **Data Preprocessing**

* Load the dataset and inspect the correlation between features.
* Remove irrelevant features based on correlation.
* Scale the input features to standardize the data.
* Split the data into training and testing sets.

### 2. **Build the Base Model**

A basic neural network model is defined with a single hidden layer using `ReLU` activation and a `sigmoid` output for binary classification. This model is compiled with the `Adam` optimizer and binary cross-entropy loss.

### 3. **Hyperparameter Tuning**

Hyperparameter tuning is done using **Keras Tuner**. Key parameters are tuned automatically:

* **Optimizer**: Choosing between `Adam`, `SGD`, `RMSprop`, and `Adadelta`.
* **Number of Units**: Tuning the number of units in the hidden layer.
* **Number of Layers**: Varying the number of hidden layers in the model.
* **Dropout**: Adding dropout layers to prevent overfitting.

### 4. **Tuning Process**

For each hyperparameter combination:

1. **Build a model** with the selected hyperparameters.
2. **Train the model** on the training data.
3. **Evaluate performance** using validation accuracy (`val_accuracy`).
4. Select the best performing model based on validation accuracy.

The Keras Tuner's `RandomSearch` method is used, which randomly samples hyperparameter combinations from a defined search space. This method evaluates different combinations and finds the one that yields the best performance.

### 5. **Model Training and Evaluation**

After hyperparameter tuning, the best model configuration is selected, and training continues for additional epochs. The model is evaluated on the test set to assess its final performance.

## Results

The best-performing model after hyperparameter tuning achieved an accuracy of approximately **75%** on the validation set. This shows how hyperparameter tuning can improve the model’s performance compared to a manually selected set of hyperparameters.

## Libraries Used

* **TensorFlow**: For building and training the neural network model.
* **Keras Tuner**: For performing hyperparameter optimization.
* **scikit-learn**: For data preprocessing and splitting the dataset.

### Required Libraries:

To run the project, you'll need to install the following:

```bash
pip install tensorflow keras-tuner scikit-learn
```

## Conclusion

This project demonstrates the power of **Keras Tuner** to automate the hyperparameter tuning process for neural networks. By using automated tuning, we can efficiently explore a wide range of hyperparameters to improve the performance of machine learning models.
