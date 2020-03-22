# Style Transfer
This project is an implementation of "Perceptual Losses for Real-Time Style Transfer and Super-Resolution". The gif below is a real-time stream from the `stream.ipynb` notebook:

![](stream.gif)

The model itself was copied almost verbatim from the pytorch examples github. The style image used for this network was:

![](http://i.imgur.com/s7ExyuL.jpg)

No colors appear because the training data was colorized but my machine vision camera is monochrome.

Some things:
* One issue I had initally when using my own model was artifacts around the edges of the generated image... This may have been because the convolutions I used before did not do the reflection padding that the pytorch example uses, but I'm not sure.
* The "feature loss" (from fastai) implementation I used uses pytorch hooks to automagically get the layers you want for style and content loss, so you should be able to use different encoders (i.e. a resnet) although I have not tried it yet.
* I had some issues training which I think stems from the content and style loss weights. Sometimes the network would make all images the same "style" for every image (style loss weighted too high) or would more or less duplicate the input (content loss too high). I used the defaults set in the pytorch example which worked well
* "gram loss" is super cool
