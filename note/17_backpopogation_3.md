---

# Backpopogation: (Why কেন এইটা সঠিক ভাবে কাজ করে ? আমাদের সঠিক রেজাল্ট দেয় ? )

---

### Revise the backpopogation algorithrm:

![Alt text](image-102.png)


---

# Let's understand: `Lost Function is a function of all trainable parameter`

![Alt text](image-103.png)

- আমরা একটা regression প্রবলেম এর সমাধান করতেছি । 
- লস ফাংশন হিসেবে `mse(mean_squared_error)` আর activation function  হিসেবে `liner` ব্যবহার করতেছি । 
- আমাদের লস ফাংশন (y - y_bar) যেখানে, y হলো constant । তাই লস ফাংশন শুধু মাত্র y_bar এর উপর নির্ভরশীল । 
- `forward propogation` এর মাধ্যমে আমরা y_bar এর ফরর্মূলা নির্ণয় করলাম । এখান থেকে আমরা ক্লিয়ার যে `Lost Function is a function of all trainable parameter`। 

`আমাদের লস ফাংশন সকল parameter(weight,bias) এর উপর নির্ভশীল । একটা বা সবগুলোর weight or bias ভ্যালু change করলে লস change  হবে .`

---

# Let's talk about `Gradient Descent:`

![Alt text](image-104.png)

- Gradient descent হলো একটা optimization algorithrm যেইটা minimize করে loss (loss function) by updating the model parameters (such as weights and biases)।

- Gradient descent আমরা derivative নির্নয় করি । Derivative নির্ণয় করার মানে হলো `slope` নির্ণয় করা । 


---

# Let's talk about `Concept of Derivative:`

![Alt text](image-105.png)

- derivative means rate of change. 

- `dy/dx = 2 , (+Ve)` X এ ১ unit change করার ফলে y এ পজিটিভ ২ unit পরিবতিত হয় । 

- `dy/dx = -2 , (-e)` X এ ১ unit chagne করার ফলে y এ নেগিটিভ ২ পরিবতিত হয় । 

` অর্থাৎ, শুরু মান নয় মান সহ চিহ্ন ও গুরুত্বর্পূণ । `

- Derivative at a point বলতে সেই point এর slope কে বুঝায় । 


