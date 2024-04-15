
---

# Vanishing Gradient 

`Neural Network train করার সময় আমরা কিছু সমস্যার সম্মুক্ষীন হয় । এর মধ্যে একটা হচ্ছে Vanishing Gradient । Vanishing Gradient হলে Neural Network ভালোভাবে train হতে পারে না । `

![Alt text](image-126.png)

![Alt text](image-127.png)

- `দুইটা এক এর থেকে ছোট সংখ্যা গুন করলে সেইটা আর ছোট হতে থাকে । `

- `Deep Neural Network এর ক্ষেত্রে এই সমস্যা দেখা দেয় । `

- `activation function sigmoid or tanH হলে সাধারণত এই সমস্যা গুলো দেখা দেয় ।`

- `weight and bias update Using Backpropogation and Gradient descent এর ক্ষেত্রে এর মান ০~১ এই range হয় । এই ক্ষেত্রে activation function এর আউটপুটগুলোর এর মান ১ এর থেকে ছোট হয় । তাই (GD-> derivation)এর মান গুলোর গুনফল এত ছোট হবে যে, weight and bias update বা convergence অনেক অনেক কম হবে । আমাদের weight and bias এত কম ভ্যালু তে change হলে, আমরা accurate weight and bias পাবো না । আবার অনেক সময়, worst case এর ক্ষেত্রে weight and bias change  হবেই না । তাই লস ফানংশন ও change হবে না ।`
<br>

`1 দিয়ে example এর ক্ষেত্রে new weight value Vanishingly small  তাই এখান থেকে নাম এসেছে  **Vanishing Gradient** `

<br>

---

# কিভাবে বুঝবো আমাদের Vanishing Gradient হচ্ছে ?

![Alt text](image-128.png)

i) loss is not changing.
ii) Drawing the graph of weights

---

Code Demo

---

# How to solve this vanishing gradient problem.

`আমরা total 5টা way দেখবো এর মধ্যে আমরা দুই টা এই ভিডিওতে দেখবো । `

- **Reduce Model Complexity:** আমরা যদি  hidden layer এর সংখ্যা কমিয়ে দেয় তাহলে এই প্রবলেম এর সমস্যার সমাধান করতে পারবো । কিন্তু, আমরা hidden layer এর সংখ্যা বাড়িয়ে ছিলাম একটা complex প্রবলেমকে করার জন্য । কিন্তু এইটা (reduce the number of hidden layer) হলে তো আমরা আর complex প্রবলেমটা  solve করতে পারবো না । `আর যদি প্রবলেম টা complex না হয় সেক্ষেত্রে এইটা কাজ করবে । `


![Alt text](image-129.png)

<br>

---

Code Demo With Previous Problem

---

# Using different actication function (generally we use `Relu`):


![Alt text](image-130.png)

- `relu activation function: ` (0~z) (Z is a positive number) এই range এ নিয়ে আসে । relu activation function এর  output কে  differentiation করলে সেইটার উত্তর ০ বা ১ আসে । অনেক গুলো ১ * ১ * ১ = ১ গুন হলে উওর ১ ঐ আসে  তাই আর Vanishing Gradient প্রবলেমের মধ্যে পড়তে হয় না। নেগিটিভ ভ্যালু থাকলে সেইটাকে 0 তে নিয়ে আসে, তাই dying relu একটা প্রবলেমের দেখা দেয় । এইটা থেকে বাচার জন্য আমরা Leaky Relu ব্যবহার করবো এই গুলো আমরা পরে দেখবো । 


