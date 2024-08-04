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

**Note**: It is important to have integer labels (not float) else BCEwithLogitsLoss throws error during model training

**Data Processing using Regex and NLTK**

*- Convert to lower case (Not necessary for the bert uncased model)*
  
*- Remove all hastags (#), handles (@), hyperlinks (http), URLs (www.)*
  
*- Remove all characters except numbers or alphabets (emoticons, punctuations or multi-space blocks)*
  
*- Identify commonly found irrelevant words and append them to stopwords and lemmatize*

*- Remove the duplicates*

*- Analyze the length of each sequence, this is going to be useful while padding or truncating during tokenization*
___

**Defining the Transformer Dataset**

*- Convert the clean dataframe to a transformer dataset to leverage its fast computation and batch processing*
  
*- Use the autotokenizer associated with distilbert with the longest padding and truncation strategy*
  
*- Split into train and test dataset*
  
*- Define the distilbert model*
___

**Training**

*- Leverage the Trainer class for faster training enabled by PyTorch accelerate*

*- Initialize the training arguments, define functions for training and evaluation*

**Note:** Specials comments for common mistake handling and justification throughout the code
___
  
### Result for epochs = 2

<img width="526" alt="image" src="https://github.com/user-attachments/assets/b7a2caf6-b38b-440d-bfb9-048895419f4c">

Epoch	Training Loss	Validation Loss	Accuracy	F1
1	No log	0.347739	0.867000	0.901845
2	No log	0.198645	0.937000	0.954578
3	No log	0.113666	0.970000	0.977974
4	No log	0.074253	0.978000	0.983776
5	No log	0.031244	0.992000	0.994126
6	No log	0.018076	0.994000	0.995595
7	No log	0.006023	0.998000	0.998534
8	0.159100	0.003826	0.998000	0.998536
9	0.159100	0.001554	0.999000	0.999267

___

**Deployment**

Model is pushed to HuggingFace at https://huggingface.co/LalasaMynalli/Training_Checkpoint/

**Next Steps**

- Increase the no. of epochs
- Hyperparameter tuning
- Deploy on AzureML



