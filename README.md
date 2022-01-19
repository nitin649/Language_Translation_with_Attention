# English to Hindi Language Translation with Attention Mechanism (Machine Translation)

# Description:

## Machine Translation
Machine Translation (MT) is the task of automatically converting one natural language into another, preserving the meaning of the input text, 
and producing fluent text in the output language.


# Project Structure

1. For the purpose of this project,I have used online dataset of english and hindi sentences. 

## Model Aerchitecture 

### Attention Mechanism
1.    In psychology, attention is the cognitive process of selectively concentrating on one or a few things while ignoring others.
      A neural network is considered to be an effort to mimic human brain actions in a simplified manner. Attention Mechanism is also 
      an attempt to implement the same action of selectively concentrating on a few relevant things, while ignoring others in deep neural networks. 
2.    The attention mechanism emerged as an improvement over the encoder decoder-based neural machine translation system in natural language processing 
      (NLP). Later, this mechanism, or its variants, was used in other applications, including computer vision, speech processing, etc.


### Sequence to Sequence Modelling
![seq_2_seq](https://user-images.githubusercontent.com/55678844/149960315-3e1f8269-0303-44c4-aa8e-5a54ee75c8d3.png)

1.  Sequence Modelling problems refer to the problems where either the input and/or the output is a sequence of data (words, letters…etc.)
2.  Sequence-to-Sequence (Seq2Seq) problems is a special class of Sequence Modelling Problems in which both, the input and the output is a sequence. 
Encoder-Decoder models were originally built to solve such Seq2Seq problems. 

### Encoder-Decoder Model
![encoder_decoder_model](https://user-images.githubusercontent.com/55678844/149959954-099b3ef4-3690-4ae9-98c9-d931db4e4cc8.png)

1. An Encoder-Decoder architecture was developed where an input sequence was read in entirety and encoded to a fixed-length internal representation.
   A decoder network then used this internal representation to output words until the end of sequence token was reached. 
2. Recurrent networks are used for both the encoder and decoder
3. I have used LSTM for this task.

### The Encoder Block
   The encoder part is an LSTM cell. It is fed in the input-sequence over time and it tries to encapsulate all its information and store it in its 
   final internal states hₜ (hidden state) and cₜ (cell state). The internal states are then passed onto the decoder part, which it will use to try 
   to produce the target-sequence. This is the ‘context vector’ which we were earlier referring to.The outputs at each time-step of the encoder part 
   are all discarded.
      
### The Decoder Block
   The decoder block is also an LSTM cell. The main thing to note here is that the initial states (h₀, c₀) of the decoder are set to the final states 
   (hₜ, cₜ) of the encoder.These act as the ‘context’ vector and help the decoder produce the desired target-sequence.Now the way decoder works, is, that 
   its output at any time-step t is supposed to be the tᵗʰ word in the target-sequence/Y_true. 
