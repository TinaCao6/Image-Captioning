# Image Captioning

A deep learning model integrating a pre-trained VGG-16 CNN for image recognition with a LSTM network for caption generation, applied on the Flickr30k dataset

**Our Model**
- This will consist of a CNN (specifically the VGG16 pre-trained model) and an LSTM
architecture that we will attach to the penultimate layer of the CNN. We are building and training
this LSTM from scratch, and hence will require pre-processing steps to deal with the captions.
- VGG16 is composed of 16 layers that have weights. This includes 13 convolutional layers,
followed by three fully connected layers. The convolutional layers use small (3x3) filters, which
allow the network to capture fine-grained patterns in the image. The ReLU activation function is
used by the model.
- Given the success of VGG16 in image recognition, its weights from training on the ImageNet
dataset were imported. This is crucially important since all the animals in our dataset are
included in the 1000 categories of ImageNet and so the pre-trained model was able to identify
these animals without need for further training.
- A basic captioning network was designed using LSTM layers. After encoding the captions using
our tokenizer, we passed the encoded captions to an embedding layer to transform them into the
text embedding space. Once the encoded captions were in the embedded space, they were passed
to the LSTM layers, so learning of captions could happen. LSTM layers are known for capturing
long-term dependencies and as such, are well-suited for caption generation where such
dependencies are essential.
- Given the small size of our dataset, and the massive number of trained parameters (over 6
million), overfitting was a serious challenge that we were concerned about. To avoid overfitting,
we included a validation set during the training process and enabled early stopping with a
patience counter to halt training if validation loss fails to improve over 3 epochs.
- Furthermore, to mitigate the effects of overfitting, we added dropout layers in nearly every part
of the network. A dropout layer was added to the image embeddings obtained from VGG16 with
a dropout rate of 25%. A dropout layer with a rate of 25% was similarly applied to the caption
embeddings. Finally, and most crucially, a dropout rate of 35% was also applied inside the
LSTM units to avoid overfitting to the training captions.

