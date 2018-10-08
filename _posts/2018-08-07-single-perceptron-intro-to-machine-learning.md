---
layout: project
title: single layer perceptron intro to machine learning
date:  "2018-08-07 2:00 -0700"
meta: a intro for machine learning the single layer perceptron. explains how the inputs and hidden are connected and transfers to the output.
pic: images/neural-network.jpg
tags: ["machine learning", "single layer perceptron", "programming", "neural network"]
---

# single layer perceptron intro to machine learning

![a picture of a neural network]({{ site.baseurl }}/images/neural-network.jpg "a picture of a neural network")


## what is a single layer perceptron

A single layer perceptron is one of the fundamentals of machine learning.

Usually a single layer perceptron has 3 layers two inputs node, one hidden node and one output. For inputs you could think of it as X and Y, for the hidden layer it can be thought of as a machine learning recipe, for the output it is what the single perceptron thought the correct answer was.

what machine learning does it tries to make a graph with the inputs and give you an output. You could think of the single layer perceptron as function that tries to make a linear line.

## step: 1 the inputs

the inputs to the single layer perceptron are numbers usually it is best to normalize the values between 0 and 1. It is best to do this because we don't want one input to dramatically increase the odds in one direction. for example lets say you wanted to use a single layer perceptron to predict how much a house cost, the inputs in this case would be how many rooms, bathrooms and how much square feet is the house. Now lets say that the house had 2 rooms and 1 bathroom and the square feet of the house is 1000. The square feet of the house will increase the price of the house by a long shot. so it is best to normalize the values. Once the inputs are received before it gets sent to the hidden layer they are multiplied by weights. Weights signify how important the input actually is. the input is multiplied by a weight and the sum is taken of the weights multiplied by the inputs. this is sent to the hidden layer.


## step: 2 the Hidden Layer

you can think of the hidden layer is the machine learning recipe. In the hidden layer there is a activation function that takes inputs and outputs a range. A example of a activation function would be checking if the value is less than or equal to 0 returns 0 and if it is greater than 0 returns 1

## step: 3 the output / training

now we have the output and can modify the weights by the error. now we can train the single layer perceptron. to train the single layer perceptron we have to give it inputs and targeted value. The perceptron takes the inputs multiplies to a weights and inputs it into a activation function and then give us the output. now we have to find the error by subtracting the value we got from the perceptron from the targeted value (error = targeted - guess). the new weight = weight + (error * learning_rate * input). You might of notice the variable learning_rate this is included because when trying to find the most optimal weights we don't want to overpass the value we want. now we keep repeating this process until we found the best weights.

## Fundamentals

the fundamentals for the a neural network also known as a single / multiple layer perceptron

  * inputs
  * weights for the inputs, to show how important each value is
  * a hidden layer with activation function to convert the values to a range
  * once it get calculated it get sent out to the output and evaluated
  * now we calculate the error by subtracting the right answer by the guess
  * now the weights get changed according to the error

## conclusion

A single layer perceptron is good start off with when learning machine learning. the next step is a multiple layer perceptron which takes the same concepts but can solve problems that aren't linear which means that it can have more that two outputs.