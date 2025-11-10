# Chapter 1: Overview of AI Engineering
This has led to the
emergence of model as a service: models developed by these few organizations are
made available for others to use as a service. Anyone who wishes to leverage AI to
build applications can now use these models to do so without having to invest up
front in building a model.
In short, the demand for AI applications has increased while the barrier to entry for
building AI applications has decreased. This has turned AI engineering—the process
of building applications on top of readily available models—into one of the fastest-
growing engineering disciplines.
## The rise of AI engineering

### Language models

A language model encodes statistical information about one or more languages. Intui‐
tively, this information tells us how likely a word is to appear in a given context. For
example, given the context “My favorite color is __”, a language model that encodes
English should predict “blue” more often than “car”.

The basic unit of a language model is token. A token can be a character, a word, or a
part of a word (like -tion), depending on the model.2 For example, GPT-4, a model
behind ChatGPT, breaks the phrase “I can’t wait to build AI applications” into nine
tokens, as shown in Figure 1-1. Note that in this example, the word “can’t” is broken
into two tokens, can and ’t. You can see how different OpenAI models tokenize text
on the OpenAI website.

The process of breaking the original text into tokens is called tokenization. For
GPT-4, an average token is approximately ¾ the length of a word. So, 100 tokens are
approximately 75 words.
The set of all tokens a model can work with is the model’s vocabulary. You can use a
small number of tokens to construct a large number of distinct words, similar to how
you can use a few letters in the alphabet to construct many words. The Mixtral 8x7B
model has a vocabulary size of 32,000. GPT-4’s vocabulary size is 100,256. The toke‐
nization method and vocabulary size are decided by model developers.

* This made sense? *

Why do language models use token as their unit instead of word or
character? There are three main reasons:
1. Compared to characters, tokens allow the model to break
words into meaningful components. For example, “cooking”
can be broken into “cook” and “ing”, with both components
carrying some meaning of the original word.
2. Because there are fewer unique tokens than unique words, this
reduces the model’s vocabulary size, making the model more
efficient (as discussed in Chapter 2).
3. Tokens also help the model process unknown words. For
instance, a made-up word like “chatgpting” could be split into
“chatgpt” and “ing”, helping the model understand its struc‐
ture. Tokens balance having fewer units than words while
retaining more meaning than individual characters.

There are two main types of language models: masked language models and autore‐
gressive language models. They differ based on what information they can use to pre‐
dict a token:
Masked language model
A masked language model is trained to predict missing tokens anywhere in a
sequence, using the context from both before and after the missing tokens. In
essence, a masked language model is trained to be able to fill in the blank. For
example, given the context, “My favorite __ is blue”, a masked language model
should predict that the blank is likely “color”. A well-known example of a
masked language model is bidirectional encoder representations from transform‐
ers, or BERT (Devlin et al., 2018).
As of writing, masked language models are commonly used for non-generative
tasks such as sentiment analysis and text classification. They are also useful for
tasks requiring an understanding of the overall context, such as code debugging,
where a model needs to understand both the preceding and following code to
identify errors.
Autoregressive language model
An autoregressive language model is trained to predict the next token in a
sequence, using only the preceding tokens. It predicts what comes next in “My
favorite color is __.
”3 An autoregressive model can continually generate one
token after another. Today, autoregressive language models are the models of choice for text generation, and for this reason, they are much more popular than
masked language models.

*lef in page 6*


