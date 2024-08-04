### Detection of Cyberbullying 🤬😠
___

### Business Application in Social Media
Cyberbullying is a serious issue, especially in the age of social media where interactions turn hurtful. Some applications of cyberbullyting detection include:

- **Real-time Monitoring**: Continuously scan social media posts or messages for signs of cyberbullying.
- **Alerts and Notifications**: Notify users when potentially harmful content is detected.
- **Reporting Mechanism**: Allow users to report incidents and take appropriate action.
___

### Which pre-trained model is chosen and why❓❔
I have used **distilbert-base-uncased** transformers which is lighter and faster than BERT. 
*- It has the same capability of distillation loss calculation and Masked Language Modeling(MLM) like that of BERT*
*- My dataset contains 1000 training and evaluation observations each, and I have limited GPU availability, hence distilbert is the most suitable one for this context.*

### Tweet Toxicity Prediction 💬
The model is trained on the https://www.kaggle.com/datasets/saurabhshahane/cyberbullying-dataset Dataset to predict the toxicity of texts to pre-emptively prevent any occurrence of cyberbullying and harassment before they tend to occur. I have chose distilled version of BERT as to overcome challenges including understanding the context of text so as to detect sarcasm and cultural references, as it uses Masked Transformer Encoders and Attention Mechanism to understand the relationship between words and sentences, the context from a given sentence.

### 
