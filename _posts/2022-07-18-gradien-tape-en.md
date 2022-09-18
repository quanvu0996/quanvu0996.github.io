---
title: '[En] Gradient tape - deploy gradient descent with tensorflow'
date: 2022-07-18
permalink: /posts/en/2022/07/gradient-tape/
tags:
  - Tensorflow
  - Gradient descent
  - Deep learning
  - English
---

![Poster](/images/post/gradient_tape.jpeg){: width="800" }<br>
Tools for building machine learning and deep learning models such as Tensorflow and Pytorch are more and more popular. Building a model becomes easy with just one fit statement. However, to optimize or create new architecture, we need a more flexible tool like Gradient Tape to train special architectural models.

For the source code of this article: [English](https://github.com/quanvu0996/data_science/blob/main/tf/gradient_tape1_en.ipynb), [Vietnamese](https://github.com/quanvu0996/data_science/blob/main/tf/gradient_tape1_vi.ipynb)

Basic concepts of tensorflow
----

**Constant**: <br>
Is a fixed value tensor. It may be a number (scalar, one-dim tensor), or the matrix (2-dim tensor), or n-dim tensor :

```python 
a = tf.constant(1)

b = tf.constant([3, 5])

c = tf.ones(shape=(2,2))
```

**Variable**: <br>
An object that can change the value.

```python 
X = tf.Variable(initial_value= tf.zeros((2, 2)), trainable= True)
```

These concepts correspond to the concepts in linear algebra.  <br>
Gradient Tape is the derivative tool of Tensorflow. The following syntax calculates the derivative of the function 
$y=x^2$ at $x=4$, $y'(x=4) = 8$:

```python 
x = tf.constant(4.0)

with tf.GradientTape() as tape:
    tape.watch(x) # while x is not a tf.Variable => we need to set the tape watch it, or else the derivative will be 0.

                  # if x is a tf.Variable then watch is no need
    y = x ** 2
dy_dx = tape.gradient(y, x)
print(dy_dx)

del tape
```

``` tf.Tensor(8.0, shape=(), dtype=float32)```

Deploy second-order derivative by the following syntax:

```python 
x = tf.constant(4.0
with tf.GradientTape() as t2:
    t2.watch(x)
    with tf.GradientTape() as t:
        t.watch(x)
        y = x ** 2
    dy_dx = t.gradient(y, x)
d2y_dx = t2.gradient(dy_dx, x)
print(d2y_dx)

del t, t2
```
` tf.Tensor(2.0, shape=(), dtype=float32))`

Simple gradient descent pipeline
----

We will consider an example of building a simple linear regression model: $Y = aX + b$. <br>
In this example, a and b are the parameters of the model, we expect to find optimal values for them so the model could generalize the relationship between X and Y. So, a and b in this example are 2 variables. We declare 2 variables:

```python 
a = tf.Variable(initial_value=0., trainable= True)
b = tf.Variable(initial_value= 0., trainable= True)
```
X and Y represent the real training data, so they are known constants. Their shapes depend on the batch size.
We define a simple loss function:

```python 
def loss_fn(y_true, y_pred)

    return tf.reduce_sum(tf.square(y_true-y_pred)):
```

For model training, we execute the gradient descent steps: find prediction value, calculate loss value, calculate partial derivative of the loss function by each parameter, update values of the parameters. The syntax with Gradient Tape  is as following:

```python 
learning_rate = 0.001
with tf.GradientTape(persistent =True) as tape:
    # Find prediction value and calculate loss value
    y_pred = a*X+b
    loss = loss_fn(Y, y_pred)

# Calculate partial derivative by each parameter
a_gradient = tape.gradient(loss, a)
b_gradient = tape.gradient(loss, b)

# update value of each parameter: w1 = w0 - learning_rate * d(loss)/dw
a.assign_sub(a_gradient*learning_rate)
b.assign_sub(b_gradient*learning_rate)

print(a)
print(b)

del tape1
```

We set persistent=True to allow tape to calculate gradient(tape.gradient) more than 1 time. 
For monitoring the optimal process, we train with many epoch and check the value of the loss function:

```python 
def train_step(x_true, y_true)
    with tf.GradientTape(persistent =True) as tape:
        # Find prediction value and calculate loss value
        y_pred = a*X+b
        loss = loss_fn(Y, y_pred)

        print("Loss: ", loss.numpy())

    # calculate partial gradient by each parameter
    a_gradient = tape.gradient(loss, a)
    b_gradient = tape.gradient(loss, b)

```
```
Epoch:  
Loss:  19.457
Epoch:  1
Loss:  10.9911995
Epoch:  2
Loss:  5.402389
Epoch:  3
Loss:  2.5634406
Epoch:  4
Loss:  2.05420330
```

It can be seen that the value of loss function decreases over time and value a and b gradually converging becomes stable through epochs.
The above functions use the basic gradient descent, in fact we will want to use the more effective optimizers. In addition, the number of parameters of a deep learning network can reach millions of parameters in reality. We do not want to have to update each parameter manually. At that time, we will do the following:

```python
model = tf.keras.Sequential(
                           tf.keras.layers.Dense(1, kernel_initializer='zeros', bias_initializer='zeros')
])

optimizer= tf.optimizers.Adam(learning_rate = .07)

def train_step2(x_true, y_true):
    with tf.GradientTape(persistent =True) as tape:
        # Find prediction value and calculate loss value
        y_pred = model(tf.expand_dims(X,-1))
        loss = loss_fn( tf.expand_dims(Y, -1), y_pred)
        print("Loss: ", loss.numpy())

    # calculate partial gradient by each parameter
    variables = model.trainable_variables 
    gradients = tape.gradient(loss, variables)

    # update value of each parameter: w1 = w0 - learning_rate * d(loss)/dw
    optimizer.apply_gradients(zip(gradients, variables))


for i in range(5):
    print("Epoch: ", i)
    train_step2(X, Y)
```

```
Epoch:  0
Loss:  19.457
Epoch:  1
Loss:  10.9911995
Epoch:  2
Loss:  5.402389
Epoch:  3
Loss:  2.5634406
Epoch:  4
Loss:  2.05420330

```


REFERENCES
----

GradientTape [Link](https://www.tensorflow.org/api_docs/python/tf/GradientTape)

Neural style transfer [Link](https://www.tensorflow.org/tutorials/generative/style_transfer)