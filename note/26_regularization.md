---

# Regularization 

---

`আমাদের মডেল যদি overfit করে তাহলে আমরা Regularization ব্যবহার করে সেইটা থেকে মুক্ত হতে পারি । `


# Why Neural Network Overfit?

`আমরা যখন একটা Neural Network এ একটা node রাখি তখন সেইটা আমাদের একটা line draw করে দেয় শুধু । আমরা Neural Network যদি Neural Network এ node বা hidden layer বাড়াতে থাকি তাহলে আমাদের সেই line তত  বেশি curve হতে থাকে । আর আমাদের training data এর minor point গুলোও capture করতে থাকে।  `

![Alt text](image-144.png)


` overfitting এর সমস্যা দুর করার জন্য আমরা node কমাতে পারি । node কমাতে হলে আমাদের সেই node weight বা  piority কে আমরা শূন্য এর কাছাকাছি নিয়ে যাবো । `



