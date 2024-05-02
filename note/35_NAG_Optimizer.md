

---

# NAG -  Nesterov Accelerated Gradient 

---

### BGD For a Problem:

(around 30 ephoc)

![Alt text](image-199.png)


### Momentum Optimizer For same Problem:

(around 50 ephoc with decay factor 0.9)

![Alt text](image-200.png)

(around 30 ephoc with decay factor 0.8)

![Alt text](image-201.png)

(around 15 ephoc with decay factor 0.5)

![Alt text](image-202.png)

`উপরে decay factor 0.9 হলে global minima তে পৌছাতে যে সময় লেগেছিলো  সেই সময়কে কম করার জন্য আমরা `

# Understanding NAG:

![Alt text](image-204.png)

`আমরাদের momentum optimizer এ weight update এর ক্ষেত্রে (history of velocity)_(Beta * V_t-1) + (gradient) এর উপর নির্ভর করতেছে । momentum optimizer আমরা একই সাথে উপরের 2 টা property  calculation   করি । `

![Alt text](image-203.png)

`আমরাদের momentum optimizer এ weight update এর ক্ষেত্রে (history of velocity)_(Beta * V_t-1) + (gradient) এর উপর নির্ভর করতেছে । momentum optimizer আমরা শুরুতে  (history of velocity) calculation করে প্রথমে সামনের দিকে একটা jump নেই তারপর আমরা এর gradient calculation করে আবার সামনের দিকে jump নেই । তাই, আমাদের  momentum optimizer এর থেকে Nesterov Accelerated Gradient fast বেশি হয় । `


