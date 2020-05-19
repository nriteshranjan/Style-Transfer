# Style-Transfer
This notebook recreates a style transfer method that is outlined in the paper, Image Style Transfer Using Convolutional Neural Networks, by Gatys in PyTorch.
In this paper, style transfer uses the features found in the 19-layer VGG Network, which is comprised of a series of convolutional and pooling layers, and a few fully-connected layers. In the image below, the convolutional layers are named by stack and their order in the stack. Conv_1_1 is the first convolutional layer that an image is passed through, in the first stack. Conv_2_1 is the first convolutional layer in the second stack. The deepest convolutional layer in the network is conv_5_4.
<br />
<img src = "https://github.com/nriteshranjan/Style-Transfer/blob/master/notebook_ims/vgg19_convlayers.png" width = 500 height = 263 title = "Structure">
# Separating Style and Content
Style transfer relies on separating the content and style of an image. Given one content image and one style image, we aim to create a new, target image which should contain our desired content and style components:

objects and their arrangement are similar to that of the content image
style, colors, and textures are similar to that of the style image
An example is shown below, where the content image is of a cat, and the style image is of Hokusai's Great Wave. The generated target image still contains the cat but is stylized with the waves, blue and beige colors, and block print textures of the style image!

<img src = "https://github.com/nriteshranjan/Style-Transfer/blob/master/notebook_ims/style_tx_cat.png" width = 1000 height = 263 title = "Style Transfer">

_In this notebook, we'll use a pre-trained VGG19 Net to extract content or style features from a passed in image. We'll then formalize the idea of content and style losses and use those to iteratively update our target image until we get a result that we want._

### Credits: _Udacity_
