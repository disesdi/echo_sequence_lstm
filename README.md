# Echo Sequences with Long Short-Term Memory (LSTM) Networks

*a project demonstrating the persistent memory of Encoder-Decoder LSTMs via their ability to "remember" randomly generated number sequences, with custom-generated data and encoding, implemented using the Keras library.*

code available in [this jupyter notebook](https://github.com/disesdi/echo_sequence_lstm/blob/9f9410e9b315259277e9c3ba685a580fd374d1e7/echo_sequences_with_lstm.ipynb)

## generating training data

the echo sequence prediction problem asks for the value of a specific index in a vector of random values (in this case, *integers*) that the model has "learned." for this project, the problem space is defined as integers between `0` and `99`.

this project uses the `randint()` function from the python 3 `random` module to generate random integers within the specified range, implemented in a home-made function called `make_seq`.

i also implemented a custom encoder function, `one_hot_encoder`, which creates a vector of binary values for each possible feature in the dataset.

## model definition & compiling

the model is built using the `Sequential` module from `keras.models`.

the `Sequential` model is defined with two layers: an LSTM layer with 25 memory units, and a fully connected dense layer with one neuron per feature.

i used two layer types from the `keras.models` module:  `LSTM`, and `Dense`.

![image](https://user-images.githubusercontent.com/110150470/211439008-497ebcab-a542-427f-8ae2-6aafc6be41ce.png)

this model uses the [log loss function](https://keras.io/api/losses/), specified under the loss parameter as `categorical_crossentropy`.

for its optimizer, the model uses the [adam optimizer](https://keras.io/api/optimizers/adam/), and outputs accuracy measurements `acc` each epoch. see code below.

![image](https://user-images.githubusercontent.com/110150470/211439105-4670dced-06e4-4547-a754-3bb8c16c4f5e.png)

## evaluation

i built a simple function to test model accuracy called `eval_model` 

![image](https://user-images.githubusercontent.com/110150470/211439350-ae032780-ebb7-4498-a932-8d087649dedb.png)


## more information

Working with RNNs (Keras):
https://keras.io/guides/working_with_rnns/

python 3 random module documentation:
https://docs.python.org/3/library/random.html

sklearn preprocessing documentation:
http://scikit-learn.org/stable/modules/classes.html#module-sklearn.preprocessing

a very cool blog post about how LSTMs work:
http://colah.github.io/posts/2015-08-Understanding-LSTMs/
