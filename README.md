<h1>ABSTRACT</h1>

A2E is a CNN based system which coverts static hand gestures of the American Sign Language to English Text. A2E aims to solve reduce the communication between an average person and a differently-abled person.

It uses various libraries like <b>TensorFlow (Keras)</b>, <b>scikit-learn</b>, <b>OpenCV</b>, etc for different purposes. Various concepts have been implemented, amog which a few are : CNN, Data Augmentation and Transfer Learning.

A2E does the conversion in real time. 

Concepts learned and used during this project:
<ul>
<li> Convolutional Neural Network
<li> Transfer Learning
<li> Image Augmentation
</ul>

<h1>DATA COLLECTION AND CLEANING</h1>

We tried to collect data from 50 different sources, after few weeks of hard work we were able to do so.... BUT.... the data we collected turned out to be VERY noisy and basically unusable. So we had to come up with a different solution.

Hence, the "webcam data.ipynb" notebook. We used this notebook to take and save pictures using <b>OpenCV</b>. We took around 50 pictures for each alphabets of shape (200,200,3). No further cleaning was required as the pictures taken were in pretty good condition.

<h1>DATA AUGMENTATION AND PREPROCESSING</h1>

The amount of data we had was not enough to counteract over fitting and decent generalization. So we had to use data augmentation. We used the <b>ImageDataGenerator</b> class for this purpose. The training data was allowed to be augmented in various ways, but the validation and test data only went through Normalization ( division by 255 ).

<h1>SHALLOW CNN MODEL</h1>

We tried various models before we could finalize one. The model was giving about 86-90% accuracy before we started hyper-tuning it. We used the "Custom GridSearch w Augmentation.ipynb" notebook to achieve this. After this the model was giving about 92-96% accuracy. The problem with these models was that they could not perform well on the "testing live.ipynb" notebook even after having nice accuracies on the train-validate-test sets.

<h1>TRANSFER LEARNING</h1>

After realizing that the Shallow CNN might not make the cut we decided to give transfer learning a shot. We tried various architectures with pre-trained weights on the ImageNet data-set. Finally we landed on the conclusion that VGG16 with a single layer ANN on it works the best. After that, it was the hyper-tuning game again. This model gave an accuracy around 89% which disappointed us in the beginning, but after using it on the "testing live.ipynb" notebook it was declared the ultimate winner.

<h1>CONCLUSION AND FINAL OUTCOME</h1>

Using the "testing live.ipynb" notebook , we were able to convert the American Sign Language Alphabets to English Text in realtime by using the <b>OpenCV</b> library. The model performs perfectly well with decent lights and plain background. Even though the model achieved an overall accuracy of 89% , it still converts all the American Sign Language Alphabets to English text perfectly. 
