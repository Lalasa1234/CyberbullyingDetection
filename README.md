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

*- Convert to lower case (Not necessary for the bert uncased model)*
  
*- Remove all hastags (#), handles (@), hyperlinks (http), URLs (www.)*
  
*- Remove all characters except numbers or alphabets (emoticons, punctuations or multi-space blocks)*
  
*- Identify commonly found words and append them to stopwords and lemmatize*

*- Remove the duplicates*

*- Analyze the length of each sequence, this is going to be useful while padding or truncating during tokenization*

**Defining the Transformer Dataset**

*- Convert the clean dataframe to a transformer dataset to leverage its fast computation and batch processing*
  
*- Use the autotokenizer associated with distilbert with the longest padding and truncation strategy*
  
*- Split into train and test dataset*
  
*- Define the distilbert model*

**Leveraged the Trainer class for faster training enabled by accelerate**

*- Initialize the training arguments, define functions for training and evaluation*

**Note:** Specials comments for common mistake handling and justification throughout the code
___
  
### Result for epochs = 2

<img width="526" alt="image" src="https://github.com/user-attachments/assets/b7a2caf6-b38b-440d-bfb9-048895419f4c">


**Deployment**

Model is pushed to HuggingFace at https://huggingface.co/LalasaMynalli/Training_Checkpoint/

**Next Steps**

- Increase the no. of epochs
- Hyperparameter tuning
- Deploy on AzureML



