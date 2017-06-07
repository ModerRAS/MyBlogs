# Writing Something about CNN

Because I use English . May be something I can't write very well.

An easiest convolutional neural network just has an input layer,a conv layer,a RELU layer,a pooling layer,a fully connect layer and a logistics regression classifier or a softmax regression classifier,then a output layer to output.

First is input layer. I think it needn't to say. It is just input some data and transport to the next layer.

The next is conv layer. This layer will compute the output of neurons that are connected to local regions in the input, each computing a dot product between their weights and a small region they are connected to in the input volume. In TensorFlow , conv2d is a 4D layer which need to input 4 parameters likes [1,28,28,1]. And it need stride. Most time we will use [1,1,1,1]. padding use "SAME". It will output a feature map and the shape is (If input is a 28x28 picture,[1,28,28,1].And it has 12 filters) [1,28,28,12] .

Then is RELU(Rectified Linear Units).

