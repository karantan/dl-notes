# Recurrent Neural Network

The way we train RNN's is to feed them a serie of sequences.

The RNN's have well known issues with backpropagation of the gradient (see Bengio & al). This is the reason why we usually feed limited sequences to the RNN to train it. So in your example, you should cut the text into smaller pieces (sentences?) in order to build your training set.

For the sake of simplicity of implementation, keras only accepts sequences of the same length in a batch (Recurrent Models with sequences of mixed length). So if your sequences don't have the same length, this is where the pad_sequence is useful.

pad_sequence takes a LIST of sequences as an input (list of list) and will return a list of padded sequences.

To get your example to work, you will have to somehow cut the text into sequences of chars. To do that you can pick the separator of your choice ('.' ? ) and then pad all the sentences to the same length. Or, smarter in my opinion, consider the text as a sequence of char (even spaces and \n), cut every n char and then feed this list of sequences as training data. This will avoid you to use padding except for the last sequence (if the number of char in your data is not a multiple of your sequence length n).

Of course, don't forget to tokenize your characters and embed them in a vector space before feeding them into the RNN. The RNN won't work on categorical data.

ref:
  - https://stackoverflow.com/questions/42042338/what-keras-pad-sequence-do
  - https://blog.keras.io/using-pre-trained-word-embeddings-in-a-keras-model.html
  - https://github.com/fchollet/keras/blob/master/examples/pretrained_word_embeddings.py
