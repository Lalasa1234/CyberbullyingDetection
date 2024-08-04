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

*- For sentiment analysis, bidirectional semantic comprehension is important, hence not choosing GPT (which is appropriate for text generation*

*- It has the same capability of distillation loss calculation and Masked Language Modeling(MLM) like that of BERT*

*- As part of text cleaning, the text is going to be small capped, hence using the uncased model version as capping has not significance here*

*- I have limited GPU availability and a small (~2000) dataset, hence distibert is the most appropriate one*


___

### Coding Blocks 👩‍💻👩‍💻 💬

*EDA and testing geometric, color-space, and miscellaneous transformations*

Defining the PyTorch Dataset and Dataloader functions along with specific transformations for image data and masked data

Defining the encoder/upsampling, bottleneck and decoder/downsampling block along with skip connections from encoder to its corresponding decoder

Training and evaluating the Model for 50 epochs along with tqdm tracking of loss

**Note:** Specials comments for common mistake handling and justification throughout the code
