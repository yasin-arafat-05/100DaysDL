
---

# Optimizers in Deep Learning

---


` কীভাবে আমাদের neural network traning speed up করা যায় এর জন্য আমরা ঃ i) weight initialization ii) Batch Normalization iii) Activation function  দেখেছি । আর আজকে থেকে আরেকটা neural network traning speed up করা যায় এমন একটা technique দেখবো ।  `


# Role of Optimizers

![Alt text](image-160.png)

`neural network এ আমরা weight and bias এর সঠিক ভ্যালু টা খুঁজে বের করার চেষ্টা করি । শুরুতে আমরা randomly weight and bias এর একটা ভ্যালু নেই । তারপর, predicted value এর সাথে real value এর loss আমরা calculation করি । আর এইকে reduce আর weight and bias কে update করার মাধ্যমে আমরা সঠিক weight and bias এর value পাই । অর্থাৎ,neural network একটা Optimizers এর এখানে Optimizers হিসেবে কাজ করে gradient descent . `

