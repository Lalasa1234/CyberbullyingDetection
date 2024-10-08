### Detection of Cyberbullying (Natural Language Processing) 🤬🗣️
___

### Business Application in Social Media
Cyberbullying is a serious issue, especially in the age of social media, where interactions turn hurtful. Some applications of cyberbullying detection that this code can solve:

- **Real-time Monitoring**: Continuously scan social media posts or messages for signs of cyberbullying.
- **Alerts and Notifications**: Notify users when potentially harmful content is detected.
- **Reporting Mechanism**: Allow users to report incidents and take appropriate action.
___

### Which pre-trained model is chosen and why❓❔

**Distilbert-base-uncased is chosen over other transformers.**

*- For sentiment analysis, bidirectional semantic comprehension is important, hence not choosing GPT (which is appropriate for text generation)*

*- It has the same capability of loss calculation and Masked Language Modeling (MLM) like that of BERT, but lighter and faster than the latter*

*- As part of text cleaning, the text is going to be small capped; hence, using the uncased model version as capping is not significant here*

*- I have limited/irregular GPU availability and a small (~2000) corpus; making Distibert the most appropriate one*


___

### Coding Blocks 👩‍💻👩‍💻 💬

**EDA and Feature Engineering** *to remove unwanted columns, treat missing values and ensure the right datatypes of columns*

**Note**: It is important to have integer target labels (not float); else BCEwithLogitsLoss throws an error during model training

**Data Processing using Regex and NLTK**

*- Convert to lower case (Not necessary for the Bert uncased model)*
  
*- Remove all hastags (#), handles (@), hyperlinks (http) and URLs (www.)*
  
*- Remove all characters except numbers or alphabets (emoticons, punctuations or multi-space blocks)*
  
*- Identify commonly found irrelevant words and append them to stopwords and lemmatize*

*- Remove the duplicates*

*- Analyze the length of each sequence; this is going to be useful while padding or truncating during tokenization*
___

**Defining the Transformer Dataset and Training**

*- Convert the clean dataframe to a transformer dataset to leverage its fast computation and batch processing*
  
*- Use the autotokenizer associated with distilbert with the longest padding and truncation strategy*
  
*- Split into train and test datasets*
  
*- Define the distilbert model*

*- Leverage the Trainer class for faster training, initialize its arguments and define functions for evaluation*
___

### Result for epochs = 10

<img width="900" alt="image" src="https://github.com/user-attachments/assets/9ce635a6-370e-431c-91d9-ed06084853b3">

___

<img width="400" alt="image" src="https://github.com/user-attachments/assets/bf85e6f9-f25b-48ac-9fcf-54e928b93b01">

___

**Deployment**

[https://huggingface.co/LalasaMynalli/LalasaMynalli_First_LLM/resolve/main/README.md](https://huggingface.co/LalasaMynalli/LalasaMynalli_First_LLM/)

**Next Steps**

- Hyperparameter tuning



