# BERT Tutorial

## 1.	Introduction
Bidirectional Encoder Representations from Transformers(BERT) is an open-sourced Natural Language Processing(NLP) technique developed by researchers at Google in 2018(Khalid,2020). Several reasons made BERT a breakthrough in the Deep Learning(DL) space, including better state-of-the-art performance and pre-trained on a bidirectional language representation model enabling fine-tuning of specific NLP tasks more efficiently than its predecessors(Devlin et al.,2019;Khalid,2020). BERT can be used as an embedding to extract features from data and for finetune models for NLP tasks such as text summarisation, question answering, language translation and sentimental analysis (Khalid,2020; ProjectPro,2023). 
## 2.	Relevance of BERT
DL-based NLP models require huge volumes of data on specific task training to perform well, however, there is no sufficient human-annotated data available for training these kinds of models(Khalid,2020). This is one of the major challenges faced in this field and this problem can be resolved using pre-training and fine-tuning models(ibid). Researchers have developed various pre-training techniques that can leverage unlabelled data on the internet for training general-purpose language models and then fine-tuning those models for specific tasks allowing them to perform well for those tasks without training them from scratch(ibid). 
Furthermore, the standard language models before BERT were trained unidirectional, restricting them from understanding the context of the text from both directions which is crucial for fine-tuning based models for token-level tasks such as question answering (Devlin et al.,2019). BERT leverages a Masked Language Model(MLM) that enables it to understand the context from both directions(ibid). MLM masks the tokens randomly from the input text and attempts to predict the masked vocabulary id correctly by understanding the context of the text(ibid). This feature of BERT also makes it suitable for fine-tuning the models more efficiently than predecessor models(ibid).
## 3.	BERT Architecture and Working
Having understood the relevance of BERT, this section covers the architecture and its working in more detail. BERT employs a multi-layered bidirectional encoder based on the architecture of Transformers for processing text (Devlin et al.,2019; Ravichandran,2022). Therefore, it is good to have an understanding of Transformers before diving into BERT architecture.
### 3.1.	Transformers
Transformers are widely used Neural Network(NN) architectures because they overcame the limitations of its predecessors including Recurrent Neural Networks(RNNs) and Long Short Term Memory(LSTM) (Giacaglia,2019). Fig.1 depicts the limitations of RNNs and LSTM architectures. 

 <img width="650" alt="image" src="https://github.com/treesa-joseph/BERT_Tutorial/assets/123733358/bdd1fcbe-134b-4bb8-b137-88dd6f5c9b42">

Figure 1.Limitations of RNN and LSTM Architectures(Giacaglia,2019)

It’s good to look at the architecture to get clear understanding on underlying architecture of BERT and how transformers overcome the limitations of its predecessors. As illustrated in Fig.2, the architecture of transformers consists of two components: Encoder and Decoder(Jain,2022). The Encoder extracts features from the input sequence and Decoder uses the features to generate an output(KiKaBeN,2021). The transformer model comprises a stack of Encoders and Decoders as demonstrated in Fig.3. Each component is covered in the next sections.

<img width="400" alt="image" src="https://github.com/treesa-joseph/BERT_Tutorial/assets/123733358/7ddd9cc3-6b23-4123-888e-cd514ad1949e">

Figure 2.High-level Architecture of Transformers(Vaswani et al.,2017)

<img width="400" alt="image" src="https://github.com/treesa-joseph/BERT_Tutorial/assets/123733358/0cbba990-f8e7-4ae0-bccd-4f76847f2fc5">

Figure 3.Encoder-Decoder Architecture of Transformers(Alammar,2018b)

### 3.1.1.	Encoder
Transformer encoder comprises a stack of identical layers where each layer has two main sub-layers: Multi-Head Attention(MHA) and Feed-Forward Network(FFN) (Cristina,2023). The input embedding layer will pre-process the input sequence before it is processed for self-attention(Jain,2022).
### 3.1.1.1.	Input Embedding
The input embedding layer maps each word or token in the input text sequence to a learned vector representation through tokenisation and vectorisation(Jain,2022). NNs learn through numerical values, so each word is represented using a continuous value in the vector(ibid). This process is also known as Word Embedding(ibid). As illustrated in Fig.4, each word in the input sentence is converted into tokens during the tokenisation process and then each token is converted into a vector which is a numerical representation of the word using Word2Vec or GloVe encoding during the vectorisation process(ibid).

<img width="362" alt="image" src="https://github.com/treesa-joseph/BERT_Tutorial/assets/123733358/95400d0f-c333-474c-a2eb-83bb84ec947f">

Figure 4.Tokenisation and Vectorisation(Jain,2022)

### 3.1.1.2.	Positional Encoding(PE)
The order and position of the words in a sentence are important in human language to interpret its meaning and context(Saeed,2023). The NLP using the RNN model leverages techniques to keep track of the order of words in the input sentence(ibid). However, the Transformers model considers each word as an independent token and adds PE to retain information about the position of the token within a text sequence(ibid). 

<img width="359" alt="image" src="https://github.com/treesa-joseph/BERT_Tutorial/assets/123733358/c1b3c394-d2a8-4be4-9de3-356b68e39ea2">

Figure 5.Positional Encoding Matrix for 'I am an Engineer'(Saeed,2023)

Instead of using numerical values such as index values, PE assigns a unique numerical representation that identifies the position of each token in a given sequence(Saeed,2023). One reason for not using index value is that index value can be a large number for long text sequences and normalising these indices between 1 and 0 might not provide expected results for variable length sequences(ibid). Hence, PE leverages a positional matrix in which each row is the summation of the encoded object with its positional information as illustrated in Fig.5(ibid). This transformation is achieved through sine and cosine functions as depicted in Fig.6 and an example is illustrated in Fig.7.

<img width="418" alt="image" src="https://github.com/treesa-joseph/BERT_Tutorial/assets/123733358/f21b24a6-16b6-4fa0-aad7-3d4386d40356">

Figure 6.Positional Encoding Equations(Jain,2022;Saeed,2023)






