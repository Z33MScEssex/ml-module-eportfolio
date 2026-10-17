# Unit 10 seminar: CNN layers and new images

**Learning outcomes:** LO1, LO2, LO3

**Task.** Look at what the CNN does at different layers (ReLU, intermediate), then test it on new images, some
like its training classes and some not: [cnn_own_images_and_layers.ipynb](cnn_own_images_and_layers.ipynb).
It reuses the model trained in [Unit 9](../unit09_cnn/README.md).

**Images.** Nine freely licensed photos from Wikimedia Commons, credited in [my_images/CREDITS.md](my_images/CREDITS.md).
I used licensed images rather than ones scraped from a search engine, so the repo carries no copyright problems.

**What I found**
- Deeper layers are sparser. After ReLU, 68% of values are zero in the first convolution and 82% in the second.
- **Only 2 of the 6 familiar objects were right**: the plane and the car, both centred on plain backgrounds like
  CIFAR's own photos. A white horse against a big sky became a ship (83%). A close-up of a dog became a frog
  (77%). The model's 64% test accuracy didn't carry over to ordinary photos. That's distribution shift.
- **All 3 unfamiliar objects got a confident wrong label**: bicycle as horse (93%), plant as truck (78%),
  teacup as ship (73%). The model has no way to say "I don't know".
