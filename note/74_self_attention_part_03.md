
<br>
<br>

# Why we do scale in Self Attention ? : 

<br>
<br>

From our previous lecture,if our Query vector is (Q), Key vector is (K) and the Value vector is (V) then our self attention equation be like: 

<br>

![image_13](photo/image13.png)

<br>

But if we see the research paper then we will see that, they scale the self attention:

<br>

![image_14](photo/image14.png)

<br>

`Why we scale it? To get rid from unstable gradient`. But  why we scale with $\sqrt{d_k}$ and what is $(d_k)$ ? $d_K$ `is the dimention of the key vector.` In our previous example, the Key vector of $K_(money) $, $K_(bank)$, $K_(grows)$ is same and `the value was three(3). Hense, in our case,`  $\sqrt{d_k}$ = $\sqrt{3}$ . In, one line ans we can also said that we divide with  $\sqrt{3}$ beacuse of `the nature of the dot product`.

<br>

![image_15](photo/image15.png)


`এখানে আমরা,` $\dot{Q,K^T}$ `করতেছি । একটি কলাম ও অন্যটি রো matrix , করার ফলে আমরা (3x3) dimentional এর একটা matrix পাচ্ছি । এখানে, আমরা 9 টা নাম্বার পাচ্ছি, এই নাম্বার গুলোর এখন আমরা mean, deviation  করতে পারবো । কিন্তু, fact হচ্ছে, base on (the nature of the dot product)` 

- from low dimentional vector's dot product we got low variance .
- from high dimentional vector's dot product we got high variance .

`আমরা ১০০০ রো এর দুইটা matrix একবার গুণ করে তাদের পল্ট করে তাদের variance তুলনা করার চেষ্টা করছি । প্রথমে, ছবিতে ৩ , ১০০, ১০০০ হলে তাদের কেমন হবে তা নিচের ছবি গুলোতে দেখানো হলো।  `

<br>

### `# 3 dimentional`

<br>

![image_16](photo/image16.png)

<br>

### `# 1000 dimentional`

<br>

![image_16](photo/image17.png)

<br>

### `# 3, 100, 1000 dimentinoal vector's histrogram and from here we can get their variance.`

<br>

![image_16](photo/image18.png)

<br>

#### `Hense, we can say that, From low dimentional vector's dot product we got low variance. From high dimentional vector's dot product we got high variance .`

<br>
<br>

# `# Now, we will study about softmax function nature: `


The equation for the **softmax function** is used to convert raw scores (logits) into probabilities, commonly applied in the output layer of neural networks for classification tasks. Here's the mathematical formula:

### Softmax Function:

Given a vector  $\mathbf{z} = [z_1, z_2, ..., z_n]$ , the softmax function $\sigma(\mathbf{z})_i$ for each component $z_i$ is defined as:


$\sigma(\mathbf{z})_i = \frac{e^{z_i}}{\sum_{j=1}^{n} e^{z_j}}$

Where:
- $\sigma(\mathbf{z})_i$ is the probability for the i-th class.
- $z_i$ is the i-th element of the input vector $\mathbf{z}$ the raw score or logit for class i.
- n is the total number of classes.
- e is Euler's number (approximately 2.718).

` অর্থাৎ softmax আমাদের কে  probability হিসেবে আউটপুট করে । এখন দুইটা নাম্বারের মধ্যে  variance কম হলে (যেমনঃ ৪,৫ ) এর ক্ষেত্রে  softmax  তাদেরকে কাছাকাছি দুইটা probability দেয় । কিন্তু, যদি দুইটা নাম্বারের মধ্যে  variance বেশি হলে (যেমনঃ ১,১০ ) এর ক্ষেত্রে  softmax তাদেরকে কাছাকাছি দুইটা probability দেয় । নিছের ছবি তে উদাঃ গুলোর কোড implementation দেওয়া হলো । ` 

<br>

![image_19](photo/image19.png)

<br>

![image_20](photo/image20.png)

<br>


# `# High variance সমস্যা কি?`

<br>

`সমস্যা হচ্ছে, যখন আমরা backpropagration করবো তখন softmax এর পরে আমরা যেই value পাবো, তাদের মধ্যে কিছু বড় হবে আর কিছু ছোট হবে (because of nature of softmax) । এর ফলে  backpropagration এর সময় বড় ভ্যালু গুলো priority বেশি পাশে আর ফলে ছোট ভ্যালু গুলো update হবে না ফলে, vinishing gradient problem দেখা দিবে ।  `


<br>

![image_13](photo/image13.png)

<br>

---

<br>


# `# Hense, our problem statement is to reduce: high variance.`

<br>

---

`নিচের ছবিতে আমরা কাছে একটা  array আছে বড় সংখ্যা হওয়ার কারণে high variance পেয়েছি । পরে আমরা ১০ দিয়ে ভাগ দেওয়ার কারণে variance কমে গিয়েছে । আমরা সেম কাজ করবো self attention এ কিন্তু ,এখন প্রশ্ন হচ্ছে যে, এখানে আমরা ১০ দিয়ে ভাগ করেছি, self attention এর ক্ষেত্রে আমাদের scaling factor কত হবে ? ,  `

![image_21](photo/image21.png)



