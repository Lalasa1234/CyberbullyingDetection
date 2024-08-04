### Detection of Cyberbullying (Finetuning of LLMs) 🤬😠
___

### Business Application in Social Media
Cyberbullying is a serious issue, especially in the age of social media where interactions turn hurtful. Some applications of cyberbullyting detection include:

- **Real-time Monitoring**: Continuously scan social media posts or messages for signs of cyberbullying.
- **Alerts and Notifications**: Notify users when potentially harmful content is detected.
- **Reporting Mechanism**: Allow users to report incidents and take appropriate action.
___

### Which pre-trained model is chosen and why❓❔

**Distilbert-base-uncased is chosen over other transformers**

*- For sentiment analysis, bidirectional semantic comprehension is important, hence not choosing GPT (which is appropriate for text generation)*

*- It has the same capability of distillation loss calculation and Masked Language Modeling(MLM) like that of BERT, but lighter and faster*

*- As part of text cleaning, the text is going to be small capped, hence using the uncased model version as capping is not significance here*

*- I have limited/irregular GPU availability and a small (~2000) corpus, hence distibert is the most appropriate one*


___

### Coding Blocks 👩‍💻👩‍💻 💬

**EDA and Feature Engineering** *to remove unwanted columns, treat missing values and ensure the right datatypes of columns*

**Note**: It is important to have integer labels (not float) here else the BCEwithLogitsLoss would throw error during model training


**Data Processing using Regex and NLTK**

*- Convert to lower case*
  
*- Remove all hastags (#), handles (@), hyperlinks (http), URLs (www.)*
  
*- Remove all characters except numbers or alphabets (emoticons, punctuations or multi-space blocks)*
  
*- Identify commonly found words and append them to stopwords and lemmatize*

*- Remove the duplicates*

*- Analyze the length of each sequence, this is going to be useful while padding or truncating during tokenization*

*Defining the PyTorch Dataset and Dataloader functions along with specific transformations for image data and masked data*

Defining the encoder/upsampling, bottleneck and decoder/downsampling block along with skip connections from encoder to its corresponding decoder

Training and evaluating the Model for 50 epochs along with tqdm tracking of loss

**Note:** Specials comments for common mistake handling and justification throughout the code
