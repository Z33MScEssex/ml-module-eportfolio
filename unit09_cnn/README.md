# Unit 9: CNN model activity

**Learning outcomes:** LO1, LO2, LO3

**Notebook:** [cnn_object_recognition.ipynb](cnn_object_recognition.ipynb). It's the module's CIFAR-10 CNN,
trained on CPU, plus my tests on images 1 to 16, per-class accuracy, the most common mistakes, and
"confident but wrong" cases.

**What I found**
- 64% accuracy on 10,000 unseen images (10 classes, so guessing gets 10%). Early stopping halted training at
  epoch 7 as it started to overfit (74% training vs 64% validation).
- Test images 1 to 16: 11 right. The mistakes include two planes called a ship and a cat, and a frog called a
  deer at 91% confidence.
- "Cat" is the model's dumping ground: 361 of 1,000 dogs were called cats, and only 38% of its "cat"
  predictions were right.
- 381 of its 3,582 mistakes were made with over 90% confidence. A confidence score isn't a guarantee.

**Fix I made:** `model.predict_classes` was removed in TensorFlow 2.6, so the last cell crashed. I used the
same `np.argmax(model.predict(...))` pattern the module already uses further up.

**The written part** (the ethical and social implications from Wall, 2019) is in my reflection.

**Data:** CIFAR-10 (Krizhevsky, 2009), downloaded by Keras.
