# Machine-Translation-English-to-Hindi

The model translates English text to Hindi text with the help of LSTM. The project was implemented in Keras Framework on TensorFlow.
An encoder was used to convert the English phrases to feature vectors that can be trained upon and a decoder converts the output vector back to normal Hindi text (utf-8).
## Dataset
The dataset consist of 2869 English phrases along with their Hindi translations. The data is given in utf-8 format.

## Preprocessing
The data was loaded and were plotted on a histogram with the size of the data points on 1 axis and number of datapoint with that size on the other axis. Then the graphs were obsereved to find an optimal length upto which the data should be passed to the LSTM for training. Larger sizes of datapoints which occur rarely are not of much use to us as they only increase the complexity of the training and doesn't contribute much to training. This way an optimal length of data was found above which all the datapoints were discarded. The optimal lengths were:
English - 78
Hindi - 87
This way our dataset became smaller and more useful.

Two sets were created :
input_characters: consist of all the english characters present in the dataset.
output_characters: consist of all the hindi characters present in the dataset.

## Model

#### Encoder
Encoder takes the English data as input and converts it into vectors that is passed to an LSTM model for training. We discard the encoder output and only keep the states.

#### Decoder
The decoder takes in Input the states of the encoder and the Hindi data points corresponding to the English input of Encoder. It trains an LSTM to produce the translated phrase in output. The decoder used softmax layer.

## Training
The model was trained using LSTM on My PC. So no use of GPU. The model was trained in parts due to lack of computational power.
It was run for 100 epochs at a time which took around 2 hrs. And I trained it approx. 10 to 12 times without resetting the weights and finally reached an accuracy of about 50 %.
Used cross-entropy loss.
Used rmsprop optimizer.
The data was passed to the model in batches of size 64.
Latent Dimensionality of the Encoding space : 256


