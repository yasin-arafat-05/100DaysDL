
---

# Activation Function:

---

# What is activation function:

![Alt text](image-150.png)

`Activation function হচ্ছে input এবং output এর মধ্যে একটা gate । যেইটা করে একটা neuron active হবে নাকি হবে না। `

---

# Why activation function is important ? 

`Activation Function না ব্যবহার করলে আমরা non-linear data কে capture করতে পারবে না । Linear Activation Function এর ক্ষেত্রে f(x) = x হয় । `

### see code example:

---

# Ideal Activation Function:

- `Activation function should be non-linear: এটা না হলে আমরা  non-linear data কে capture করতে পারবে না । `

- `Activation function should be Differentiable: কারণ আমরা gradient descent ব্যবহার করি । `

- `Should be Computationally inexpensive: differentiation এত complex হবে না যেইটা করতে অনেক বেশি সময় লাগবে । Computationally expensive হলে, আমাদের train এর সময় অনেক বেশি লাগবে ।  `

- `Should be zero centered or nomalize: আমরা train এর সময় normalized data দিলে সেইটা খুব তাড়াতাড়ি converge হবে । example: tanh activation funciton. `

- `Should be non-saturating: এরা একটা ইনপুট কে একটা range  এর মধ্যে আবন্ধ করে । যেমনঃ sigmoid range(0~1) or tanh range(-1,1) . Saturating activation function হচ্ছে relu, max(o,x) । non-sturating activation function এর ক্ষেত্রে vanising gradient descent দেখা দেওয়ার  probability অনেক বেশি । `











