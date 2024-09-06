
# # 1. `Introduction to GAN.`

A Generative Adversarial Network, or GAN, is a type of neural network architecture for generative modeling.

Generative modeling involves using a model to generate new examples that plausibly(
বিশ্বাসযোগ্য) come from an existing distribution of samples, such as generating new photographs that are similar but specifically different from a dataset of existing photographs.

A GAN is a generative model that is trained using two neural network models. One model is called the “generator” or “generative network” model that learns to generate new plausible(
বিশ্বাসযোগ্য) samples. The other model is called the “discriminator” or “discriminative network” and learns to differentiate generated examples from real examples.

![Alt text](/01_Gan_Advance/Note_image/img1.png)

**Problem statement:** ধরি, আমাদের কাছে 100k  বিড়ালের ছবি আছে । এখন এই ছবি গুলো দিয়ে আমাদের একটা নতুন বিড়ালের ছবি আউপুট এ আনতে হবে । অর্থাৎ, আমরা নতুন কিছু তৈরি করতেছি । এইটা একটা unsupervised learning প্রবলেম । supervised learning প্রবলেম এ আমরা classification করা শিখেছি । এখন এইধরনের neural network আমরা উপরের  architecture ফলো করে বানাতে পারি । 

![Alt text](/01_Gan_Advance/Note_image/img2.png)

আমরা জানি যে, GAN দুই ধরনের neural network models থাকে । তারমধ্যে একটা হচ্ছে, `“discriminator” or “discriminative network”` যেইটা নরমাল ছন্ন থাকতে পারে । এতে একটা ছবি ইনপুট হিসেবে দিলে এই ছবিটা ফেক নাকি রিয়েল, (০,১) আউটপুট হিসেবে দেয় । অর্থাৎ, এইখানে, discriminator supervised learning প্রবলেম হিসেবে কাজ করতেছে । 

অন্যদিকে, শুরুতে `“generator” or “generative network”` আমরা একটা noise দেই এর ফলে আমরা একটা fake image পাই । এই fake image আমরা পরে discriminator এ দেই, fake image এর সাথে আমরা discriminator এ আমরা real image  দেই । তারপর, discriminator আমাদের আউপুট ছবিটা fake নাকি real, (0->fake, 1->real) আউটপুট দেয় । শুরুতে, “generator” আর "discriminator" দুইটায় খারাপ আউটপুট দেয় । সময়ের সাথে সাথে, discriminator এর performance improve করে, সাথে সাথে “generator” এর performance improve করে, (for backpropagation) ।

<br>

# # 2. `Application of GAN:`

- Generate Examples for Image Datasets
- Generate Photographs of Human Faces
- Generate Realistic Photographs
- Generate Cartoon Characters
- Image-to-Image Translation
- Text-to-Image Translation
- Semantic-Image-to-Photo Translation
- Face Frontal View Generation
- Generate New Human Poses
- Photos to Emojis
- Photograph Editing
- Face Aging
- Photo Blending
- Super Resolution
- Photo Inpainting
- Clothing Translation
- Video Prediction
- 3D Object Generation

### To know more about these application visit [machinelearningmastery](https://machinelearningmastery.com/impressive-applications-of-generative-adversarial-networks/)


<br>

# # 3. `Different type of GAN`

<br>


### **1. Vanilla GAN**
- **Description**: The original GAN introduced by Ian Goodfellow in 2014.
- **Architecture**: Consists of two neural networks, a **generator** and a **discriminator**. The generator creates fake data, while the discriminator tries to distinguish between real and fake data.
- **Use Case**: Basic image generation tasks (e.g., generating handwritten digits, low-resolution images).

---

### **2. Deep Convolutional GAN (DCGAN)**
- **Description**: Introduced in 2015, this is a GAN that leverages **convolutional neural networks (CNNs)** instead of fully connected layers.
- **Architecture**: Uses convolutions, batch normalization, and Leaky ReLU activations to stabilize training and generate high-quality images.
- **Use Case**: Image generation with better visual features (e.g., faces, textures, art).

---

### **3. Conditional GAN (cGAN)**
- **Description**: A GAN conditioned on **auxiliary information**, such as class labels or data attributes.
- **Architecture**: The generator and discriminator are both provided with extra information, like class labels, in addition to the input noise vector.
- **Use Case**: Generating specific types of data, like images of a particular class (e.g., dogs, cars) based on the input condition.

---

### **4. Wasserstein GAN (WGAN)**
- **Description**: A GAN that uses the **Wasserstein distance** as a loss function to improve training stability.
- **Architecture**: The discriminator is replaced by a **critic** that provides real-valued feedback rather than binary classification.
- **Use Case**: Reducing mode collapse and improving training stability for more complex generative tasks.

---

### **5. Wasserstein GAN with Gradient Penalty (WGAN-GP)**
- **Description**: An improvement over WGAN, it introduces a **gradient penalty** to enforce the Lipschitz constraint, further improving stability.
- **Architecture**: Adds a gradient penalty term in the loss function to ensure the model adheres to the Lipschitz continuity condition.
- **Use Case**: More stable and reliable training for high-resolution image generation.

---

### **6. Least Squares GAN (LSGAN)**
- **Description**: Modifies the loss function to use **least squares** instead of binary cross-entropy, leading to more stable training and better-quality results.
- **Architecture**: Minimizes the squared difference between the predicted value and the target value for the discriminator output.
- **Use Case**: Generates sharper and more realistic images with less noise.

---

### **7. CycleGAN**
- **Description**: A GAN designed for **image-to-image translation** without paired datasets, introduced in 2017.
- **Architecture**: Two GANs are used for bi-directional image transformation between two domains (e.g., turning photos into paintings and vice versa).
- **Use Case**: Style transfer, such as converting horse images to zebras, photo enhancement, or artistic style applications.

---

### **8. StyleGAN**
- **Description**: Developed by NVIDIA, StyleGAN introduces a new way to generate images by controlling the **style at each convolutional layer**.
- **Architecture**: Uses a generator network that allows control over different levels of features in generated images (e.g., facial features like hair, eyes, or facial structure).
- **Use Case**: High-resolution image synthesis, face generation, artistic content.

---

### **9. BigGAN**
- **Description**: Developed by Google, BigGAN scales up GAN training to generate **high-resolution images** with better diversity and quality.
- **Architecture**: Introduces **larger batch sizes**, deeper models, and more feature channels.
- **Use Case**: Ultra-high-resolution image generation (e.g., 512x512 images) with high quality and detailed features.

---

### **10. Super-Resolution GAN (SRGAN)**
- **Description**: A GAN designed to generate **super-resolution images** from low-resolution inputs.
- **Architecture**: Uses perceptual loss to capture high-level feature differences and ensure that the generated image has sharp and realistic details.
- **Use Case**: Enhancing the resolution of low-quality images (e.g., converting 64x64 images to 256x256).

---

### **11. Pix2Pix**
- **Description**: A type of GAN that performs **paired image-to-image translation**. It requires a dataset of paired images, such as black-and-white images and their corresponding colored versions.
- **Architecture**: Uses a **U-Net generator** and a PatchGAN discriminator to improve the quality of output.
- **Use Case**: Tasks like colorization, sketch-to-image generation, satellite image translation.

---

### **12. Progressive Growing GAN (PGGAN)**
- **Description**: A GAN that grows both the generator and discriminator **progressively** during training, starting with low-resolution images and gradually increasing resolution.
- **Architecture**: Adds layers to both networks as training progresses, allowing the model to learn better features for high-resolution images.
- **Use Case**: High-quality image generation (e.g., HD faces, landscapes).

---

### **13. StarGAN**
- **Description**: A GAN designed for **multi-domain image translation**, allowing transformations between multiple image domains with a single model.
- **Architecture**: Utilizes a single generator and discriminator for transforming images across different domains (e.g., different facial expressions, age, or gender).
- **Use Case**: Generating images with specific attributes or transformations, such as age progression.

---

### **14. InfoGAN**
- **Description**: A GAN that maximizes the mutual information between a small subset of the generator’s noise and the data, enabling better control over the output features.
- **Architecture**: Adds an information-theoretic regularization term to the GAN’s objective.
- **Use Case**: Learning disentangled representations (e.g., generating digits with specific orientations, colors).

---

### **15. Self-Attention GAN (SAGAN)**
- **Description**: Introduces a **self-attention mechanism** in the generator and discriminator to model long-range dependencies in the data.
- **Architecture**: Uses self-attention layers to capture global image features, especially useful for generating images with large-scale structures.
- **Use Case**: High-resolution image generation where both global and local features are important.

---

### **16. Auxiliary Classifier GAN (ACGAN)**
- **Description**: A GAN variant that includes a classifier to predict the class of generated images, enhancing control over the generated data.
- **Architecture**: The discriminator is tasked with classifying the realness of the images and predicting the class labels of generated images.
- **Use Case**: Image generation for specific classes or categories (e.g., generating images of specific animals or objects).

---

### **17. Semi-Supervised GAN (SGAN)**
- **Description**: A GAN that uses both labeled and unlabeled data to improve the model's ability to generate high-quality images.
- **Architecture**: The discriminator is trained to classify real images into one of several classes, or to classify generated images as fake.
- **Use Case**: Improving generative tasks in scenarios where labeled data is scarce.

---

