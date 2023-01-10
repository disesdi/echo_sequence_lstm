# Echo Sequences with Long Short-Term Memory (LSTM) Networks

*a project demonstrating the persistent memory of Encoder-Decoder LSTMs via their ability to "remember" randomly generated number sequences, with custom-generated data and encoding, implemented using the Keras library.*

## generating training data

the echo sequence prediction problem asks for the value of a specific index in a vector of random values (in this case, *integers*) that the model has "learned." for this project, the problem space is defined as integers between `0` and `99`.

this project uses the `randint()` function from the python 3 `random` module to generate random integers within the specified range, implemented in a home-made function called `make_seq`.

i also implemented a custom encoder function, `one_hot_encoder`, which creates a vector of binary values for each possible feature in the dataset.

## model definition

the model is built using the `Sequential` module from `keras.models`.

the `Sequential` model is defined with two layers: an LSTM layer with 25 memory units, and a fully connected dense layer with one neuron per feature.

i used two layer types from the `keras.models` module:  `LSTM`, and `Dense`.


## more information

Working with RNNs (Keras):
https://keras.io/guides/working_with_rnns/

python 3 random module documentation:
https://docs.python.org/3/library/random.html

sklearn preprocessing documentation:
http://scikit-learn.org/stable/modules/classes.html#module-sklearn.preprocessing

a very cool blog post about how LSTMs work:
http://colah.github.io/posts/2015-08-Understanding-LSTMs/
