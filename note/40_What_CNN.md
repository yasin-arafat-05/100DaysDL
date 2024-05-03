
---

# What is CNN

---

![Alt text](image-226.png)

`ANN এ আমরা Matrix Multiplication Use করি অন্যদিকে CNN এ Convolution layer নামে একধরনের layer থাকে সেই layer গুলোতে আমরা একটা special operation perform এই operation কে  Convolution Operation বলে । ছবিতে, convolution layer এর নিচে convolution লিখা আছে । যদি কোন Neural Network এ একটাও Convolution layer থাকে তাহলে আমরা বুঝতে এখানে CNN করা হয়েছে । CNN এ ৩ ধরনের layer থাকেঃ `

- `Convolution layer`
- `Pooling layer`
- `FC layer or Fully Connected layer also in ANN`

<br>

![Alt text](image-227.png)

<br>

![Alt text](image-228.png)

<br>

### CNN is Inspired From Human Vision (Visual Cortex)


![Alt text](image-229.png)

`CNNs were pioneered by Yann LeCun, Leon Bottou, Yoshua Bengio, and Patrick Haffner in the late 1980s and early 1990s. Their initial purpose was to process visual data for tasks such as handwritten digit recognition.`

# ANN Vs CNN

![Alt text](image-230.png)

`আমরা CNN এর প্রবলেম গুলো ANN দিয়ে করতে পারি । যেমনঃ MNIST Data set এ আমরা ANN 98% Accuracy অর্জন করেছিলাম ।  কিন্তু, এতে আমরা কিছু সমস্যার সম্মুখীন হই ।  `

- `High Computational Cost: ANN এ Image কে input দেওয়ার জন্য 2D image কে আমরা 1D তে convert করে Row by Row উপরের চিত্রের মতো input দেই । আমাদের কাছে যদি 40x40 এর একটা image থাকে তাহলে 40*40 = 1600 আর যদি input layer এ 100 node থাকে তাহলে আমাদের  input layer weight হবে 1600*100 = 160000 আর যদি ছবিটা 1000x1000  আকারের হয় তাহলে তো আর কোন কথায় নেই 1000*1000*100 = 100000000 weight হবে । `



