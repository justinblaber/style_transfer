# Style Transfer
This project is an implementation of "Perceptual Losses for Real-Time Style Transfer and Super-Resolution". The gif below is a real-time stream of my hand (holding an iphone) from the `stream.ipynb` notebook using the following style image:

![](stream.gif) ![](https://i.imgur.com/YqsqLiE.jpg)

The images from my camera are gray-scale, so it may have looked even cooler with color images. 

In addition, image based style transfer ("A Neural Algorithm of Artistic Style") was also done:

![](https://i.imgur.com/4VGVZAz.jpg) ![](https://i.imgur.com/KDbT2pD.jpg) ![](https://i.imgur.com/VGrtZrB.jpg)

Some things:
* "gram loss" is super cool
* I think reflection padding for the network-based approach helped make the images look "good" near the edges. 
* The "feature loss" (from fastai) implementation I used uses pytorch hooks to automagically get the layers you want for style and content loss, so you should be able to use different encoders (i.e. a resnet) although I have not tried it yet.
* The image based approach is actually quite fast, easier to tweak/iterate, and generates better images (which makes sense, since the loss is minimized directly on a pixel level instead of through a network). If you want to generate single images and don't need real-time performance I would go this route. 
