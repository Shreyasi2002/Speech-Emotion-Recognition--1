# Speech Emotion Recognition
This is a Speech Emotion Recognition based on RAVDESS dataset, project repository for summer 2021, Brain and Cognitive Science Society.

## Abstract:

Speech Emotion Recognition, abbreviated as SER, is the act of attempting to recognize human emotion and the associated 
affective states from speech. This is capitalizing on the fact that voice often reflects underlying emotion through tone and pitch. 
Emotion recognition is a rapidly growing research domain in recent years. Unlike humans, machines lack the abilities to perceive 
and show emotions. But human-computer interaction can be improved by implementing automated emotion recognition, thereby 
reducing the need of human intervention.

In this project, basic emotions like calm, happy, fearful, disgust etc. are analyzed from emotional speech signals. We use machine learning techniques like Multilayer perceptron Classifier (MLP Classifier) which is used to categorize the given data into respective groups which are non linearly separated. We will also use CNN (Convolutional Neural Networks) and RNN-LSTM model. Mel-frequency cepstrum coefficients (MFCC), chroma and mel features are extracted from the speech signals and used to train the MLP classifier. For achieving this objective, we use python libraries like Librosa, sklearn, pyaudio, numpy and soundfile to analyze the speech modulations and recognize the emotion. 

Using RAVDESS dataset which contains  around 1500 audio file inputs from 24 different actors (12 male and 12 female) who recorded short audios in 8 different emotions, we will train a NLP- based model which will be able to detect among the 8 basic emotions as well as the gender of the speaker i.e. Male voice or Female voice.  
After training we can deploy this model for predicting with live voices.

## Deliverables:

Learn the basics of Python, ML/DL, NLP, librosa, sklearn, etc , Literature Review , analyzing the dataset and Feature extraction. Building and training the model on the training data, followed by testing on test data. And finally, testing the model on live audio input (unseen) and collecting the results:)

## Dataset
We have used the RAVDESS Dataset for our project. The Ryerson Audio-Visual Database of Emotional Speech and Song (RAVDESS) contains 7356 files (total size: 24.8 GB). The database contains 24 professional actors (12 female, 12 male), vocalizing two lexically-matched statements in a neutral North American accent.

<img width="665" alt="waveform" src="https://github.com/Shreyasi2002/Speech-Emotion-Recognition--1/assets/75871525/7e5c9107-e723-4249-8972-20e63ab8e08d">


Here is the filename identifiers as per the official RAVDESS website:

 * Modality (01 = full-AV, 02 = video-only, 03 = audio-only).
 * Vocal channel (01 = speech, 02 = song).
 * Emotion (01 = neutral, 02 = calm, 03 = happy, 04 = sad, 05 = angry, 06 = fearful, 07 = disgust, 08 = surprised).
 * Emotional intensity (01 = normal, 02 = strong). NOTE: There is no strong intensity for the 'neutral' emotion.
 * Statement (01 = "Kids are talking by the door", 02 = "Dogs are sitting by the door").
 * Repetition (01 = 1st repetition, 02 = 2nd repetition).
 * Actor (01 to 24. Odd numbered actors are male, even numbered actors are female).
 
So, here's an example of an audio filename. 02-01-06-01-02-01-12.mp4. This means the meta data for the audio file is:

- Video-only (02)
- Speech (01)
- Fearful (06)
- Normal intensity (01)
- Statement "dogs" (02)
- 1st Repetition (01)
- 12th Actor (12) - Female (as the actor ID number is even)

## Feature Extraction

<img width="601" alt="spec" src="https://github.com/Shreyasi2002/Speech-Emotion-Recognition--1/assets/75871525/89618135-3f16-43c9-a5cb-1cd3601846bd">


Feature extraction is important in modeling because it converts audio files into a format that can be understood by models.

1. MFCC (Mel-Frequency Cepstral Coefficients)- It is a representation of the short-term power spectrum of a sound, based on linear cosine transformation of a log power spectrum on nonlinear mel frequency scale.
2. Chroma- It closely relates to the 12 different pitch classes. It captures harmonic and melodic characteristics of music.
3. Mel Scale- It is a perceptual scale of pitches judged by listeners to be in equal in distance from one another. 
4. Zero Crossing Rate (ZCR)- It is the rate at which a signal changes from positive to zero to negative or from negative to zero to positive.
5. Spectral Centroid- It is the center of 'gravity' of the spectrum. It is a measure used in digital signal processing to characterize a spectrum.

<img width="921" alt="feature" src="https://github.com/Shreyasi2002/Speech-Emotion-Recognition--1/assets/75871525/074f5daf-8380-4399-afe4-2dc19b3b9106">


    
## Model Implementation

**MLP (Multi-Layer Perceptron) Model:**
The  arrays containing features of the audios are given as an input to the MLP Classifier that has been  initialized. The Classifier identifies different categories in the datasets  and classifies them into different emotions.


**Convolutional Neural Network (CNN):**
The activation layer called as the RELU layer is  followed by the pooling layer. The specificity of the CNN layer is  learnt from the functions of the activation layer.


**RNN-LSTM Model:**
We used RMSProp optimizer to train the RNN-LSTM model, all  the experiments were carried with a fixed learning rate. Batch  Normalization is applied over every layer and the  activation function used is the SoftMax activation function.

## Results:
  - CNN model gave an accuracy of 73% 
  - LSTM model gave an accuracy of 71%
  - MLP model gave an accuracy of 62%

## Documentation and Poster
The documentation can be accessed at the following link:
https://drive.google.com/file/d/1ojnUU7AOe5E43PwwtJH2CN3Rz2ozQxWA/view?usp=sharing

The poster can be viewed at the following link:
https://drive.google.com/file/d/1PsmzCaxg3v899fhk8vF_oC2yWWS900V7/view


## References
1. Python basics: https://github.com/bcs-iitk/BCS_Workshop_Apr_20/tree/master/Python_Tutorial. 
-Shashi Kant Gupta, founder BCS. 
2. Intro to ML: https://youtu.be/KNAWp2S3w94 , Basic CV with ML: https://youtu.be/bemDFpNooA8 
3. Intro to CNN: https://youtu.be/x_VrgWTKkiM , Intro to DL: https://youtu.be/njKP3FqW3Sk
4. Feature Extraction: https://www.kaggle.com/ashishpatel26/feature-extraction-from-audio , https://youtube.com/playlist?list=PL-wATfeyAMNqIee7cH3q1bh4QJFAaeNv0 ,           https://medium.com/analytics-vidhya/understanding-the-mel-spectrogram-fca2afa2ce53
5. Research paper: https://ijesc.org/upload/bc86f90a8f1d88219646b9072e155be4.Speech%20Emotion%20Recognition%20using%20MLP%20Classifier.pdf
6. Research Paper on SER using CNN: https://www.researchgate.net/publication/341922737_Multimodal_speech_emotion_recognition_and_classification_using_convolutional_neural_network_techniques
7. K Fold Cross Validation: https://machinelearningmastery.com/k-fold-cross-validation/
8. Research Paper for LSTM Model in SER: http://www.jcreview.com/fulltext/197-1594073480.pdf?1625291827
9. Dataset: https://www.kaggle.com/uwrfkaggler/ravdess-emotional-speech-audio.
     
