### Detection of Cyberbullying 🤬😠
___

### Business Application in Social Media
Cyberbullying is a serious issue, especially in the age of social media where interactions turn hurtful. Some applications of cyberbullyting detection include:

- **Real-time Monitoring**: Continuously scan social media posts or messages for signs of cyberbullying.
- **Alerts and Notifications**: Notify users when potentially harmful content is detected.
- **Reporting Mechanism**: Allow users to report incidents and take appropriate action.
___

### Choice of Model Selection 
I have used 'distilbert-base-uncased' transformers which is lighter and faster than BERT. My dataset contains 1000 training and evaluation observations each, and I have limited GPU availability, hence distilbert is the most suitable one for this context.

### Text Toxicity Prediction 💬
Our text classification BERT model is trained on the Jigsaw Toxic Comment Classification Dataset to predict the toxicity of texts to pre-emptively prevent any occurrence of cyberbullying and harassment before they tend to occur. We're chose BERT as to overcome challenges including understanding the context of text so as to detect sarcasm and cultural references, as it uses Masked Transformer Encoders and Attention Mechanism to understand the relationship between words and sentences, the context from a given sentence.

### 
