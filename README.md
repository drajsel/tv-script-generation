# tv-script-generation

## Project specification 


### All required files and tests


- [x] The project submission contains the project notebook, called “dlnd_tv_script_generation.ipynb”.

- [x] All unit tests in the project have passed

### Pre-processing Data


The function create_lookup_tables is implemented:

- [x] The function create_lookup_tables create two dictionaries:

	- Dictionary to go from the words to an id, we'll call vocab_to_int
	- Dictionary to go from the id to word, we'll call int_to_vocab
- [x] The function create_lookup_tables return these dictionaries as a tuple (vocab_to_int, int_to_vocab).

A special token dictionary is created:

- [x] The function token_lookup returns a dict that can correctly tokenizes the provided symbols.

### Batching Data

Data is broken into sequences:

- [x] The function batch_data breaks up word id's into the appropriate sequence lengths, such that only complete sequence lengths are constructed.

Data is created using TensorDataset:

- [x] In the function batch_data, data is converted into Tensors and formatted with TensorDataset.

Data is batched correctly:

- [x] Finally, batch_data returns a DataLoader for the batched training data.

### Build the RNN

An RNN class has been defined:

- [x] The RNN class has complete __init__, forward , and init_hidden functions.

The RNN includes at least one LSTM (or GRU) and fully-connected layer:

- [x] The RNN must include an LSTM or GRU and at least one fully-connected layer. The LSTM/GRU should be correctly initialized, where relevant.

### RNN Training

Reasonable hyperparameters are selected for training:

- [x] Enough epochs to get near a minimum in the training loss, no real upper limit on this. Just need to make sure the training loss is low and not improving much with more training.
- [x] Batch size is large enough to train efficiently, but small enough to fit the data in memory. No real “best” value here, depends on GPU memory usually.
- [x] Embedding dimension, significantly smaller than the size of the vocabulary, if you choose to use word embeddings
- [x] Hidden dimension (number of units in the hidden layers of the RNN) is large enough to fit the data well. Again, no real “best” value.
- [x] n_layers (number of layers in a GRU/LSTM) is between 1-3.
- [x] The sequence length (seq_length) here should be about the size of the length of sentences you want to look at before you generate the next word.
- [x] The learning rate shouldn’t be too large because the training algorithm won’t converge. But needs to be large enough that training doesn’t take forever.

The model shows improvement during training:

- [x] The printed loss should decrease during training. The loss should reach a value lower than 3.5.

Question about hyperparameter choices is answered:

- [x] There is a provided answer that justifies choices about model size, sequence length, and other parameters.

### Generate TV Script

The generator code generates a script:

- [x] The generated script can vary in length, and should look structurally similar to the TV script in the dataset.

- [x] It doesn’t have to be grammatically correct or make sense.

## Suggestions to Make Your Project Stand Out!
- [ ] Use validation data to choose the best model
- [ ] Initialize your model weights, especially the weights of the embedded layer to encourage model convergence
- [ ] Use topk sampling to generate new words

## Future work: 
- [ ] Try different scripts, eg. Friends!
- [ ] Implement the suggestions above