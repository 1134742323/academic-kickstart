---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "SharpTorch: A good framework to start your deep learning"
summary: "Your first dive into DL"
authors: [Yushi Lan, Xiaotong Li]
tags: [Deep Learning, Neural Network, Open Source]
categories: [Framework]
date: 2019-12-13T19:16:10+08:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Neural network can represent complicated mapping from space to space"
  focal_point: "Center"
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: "https://github.com/NIRVANALAN/SharpTorch"
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---
This project allow you to define the structure of your network in a layer by layer manner, and you can choose what activation function to use per layer. We implemented forward propogation, cost function such as 
- Loss Functions
  - Cross Entropy Loss
  - Mean Square Error Loss
  - NLLLoss 
- Activation Functions
  - Relu
  - LeakyRelu
  - Sigmoid


Our framework supports training, backward propogation and other helper functions. You can apply this framework on your own regression and classification work in a rather simple way.

## Here is a form of succinct description to what functions all the modules of our codes perform. Hope it will help you gain a better understanding of this framework. ##

| Component                          | Description                                                                                                                                                                |
| :--------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DataLoader.cs, Dataset.cs, help.cs | Load dataset and perform data pre-process like shuffle, split training set, dev set and test set, initialize weight matrices and so on.                                    |
| Evaluate.cs                        | Define cost functions, you can add your own codes regarding evaluation of the performance of models here.                                                                  |
| layer.cs                           | Define the structure of each layer and the activation function of each layer such as Relu, L-Relu, sigmoid, tanh and so on. We also plan to implement drop out later here. |
| loss.cs                            | Define the calculation function to compute loss on training sets.                                                                                                          |
| model.cs                           | Aggregate all layers defined previously, implement the complete forward propogation and backward propogation.                                                              |
| NN.cs                              | Implement the whole process of training.                                                                                                                                   |
| Optimizer.cs                       | Define different ways to optimize the final result.                                                                                                                        |
| Program.cs                         | A test case to validify that our program is useful.                                                                                                                        |

## In the follow, we will give demos as regard to how to use this framework. ##
Here we define a model
```
var inputLayer = new Linear(1, 13);
var activationLayer1TanH = new HyperTan();
var hiddenLayer1 = new Linear(13, 13);
var activationLayer2TanH = new HyperTan();
var hiddenLayer2 = new Linear(13, 1);
var model = new Model(new Layer[] {inputLayer, activationLayer1TanH, hiddenLayer1, activationLayer2TanH, hiddenLayer2});
```
initiate the weights and define momentum & learning rate
```
 if (provideInitialWeights)
{
model.SetWeights(initialWeights);
}
const double learning_rate = 0.005;
const double momentum = 0.001;
```
define optimizer and dataloader
```
var optimizer = new SGD(model, learning_rate, momentum);
var dataLoader = new DataLoader(trainSet, 1, shuffle_flag);
```
Then, we can train the network in pyTorch way, using SGD and MSELOSS
```
while (epoch < numEpochs)
{
  epoch++;
  if (epoch % epochInternal == 0 && epoch > 0)
  {
      var mse = Evaluate.MSE(model, testSet);
      Console.WriteLine("epoch = " + epoch + " acc = " + (1 - mse).ToString("F4"));
  }

  for (int i = 0; i < dataLoader.loopTime; i++)
  {
      var data = dataLoader.Enumerate();
      Helper.SplitInputOutput(data, out var inputData, out var outputData);
      var yPred = model.Forward(inputData[0]);
      var loss = new RegressionLoss(yPred, outputData[0]);
      optimizer.Zero_grad();
      before .backward()
      loss.Backward();
      optimizer.Step();
  }
}
