

---

# NAG -  Nesterov Accelerated Gradient 

---

### BGD For a Problem:

(around 30 ephoc)

![Alt text](img/image-199.png)


### Momentum Optimizer For same Problem:

(around 50 ephoc with decay factor 0.9)

![Alt text](img/image-200.png)

(around 30 ephoc with decay factor 0.8)

![Alt text](img/image-201.png)

(around 15 ephoc with decay factor 0.5)

![Alt text](img/image-202.png)

`উপরে decay factor 0.9 হলে global minima তে পৌছাতে যে সময় লেগেছিলো  সেই সময়কে কম করার জন্য আমরা `

# Understanding NAG:

![Alt text](img/image-204.png)

`আমরাদের momentum optimizer এ weight update এর ক্ষেত্রে (history of velocity)_(Beta * V_t-1) + (gradient) এর উপর নির্ভর করতেছে । momentum optimizer আমরা একই সাথে উপরের 2 টা property  calculation   করি । `

![Alt text](img/image-203.png)

`আমরাদের momentum optimizer এ weight update এর ক্ষেত্রে (history of velocity)_(Beta * V_t-1) + (gradient) এর উপর নির্ভর করতেছে । momentum optimizer আমরা শুরুতে  (history of velocity) calculation করে প্রথমে সামনের দিকে একটা jump নেই তারপর আমরা এর gradient calculation করে আবার সামনের দিকে jump নেই । তাই, আমাদের  momentum optimizer এর থেকে Nesterov Accelerated Gradient fast বেশি হয় । `


![Alt text](img/image-205.png)

`প্রথমে আমরা তো Momentum এর জন্য jump নেই একে look ahed বলে ।  `

# Geometric Intuition:

![Alt text](img/image-206.png)

- `Momentum Optimizer: Momentum সামনের দিকে gradient পিছনের দিকে । দুইটার নেট করে করতে পারে না । তাই আমাদের যদিও পিছনের দিকে আসার কথা কিন্তু না করার কারণে আমরা সামনেই দিকেই যাচ্ছি । `

- `Nesterov Accelerated Gradient: Momentum সামনের দিকে gradient পিছনের দিকে । আমরা পিছনে চলে আসি । `


# Disadvantage of NAG:

![Alt text](img/image-207.png)

- `Local minima তে ফেঁসে যেতে পারে । `



---

# Code implementation of (Momentum Optimization and NAG)


---


