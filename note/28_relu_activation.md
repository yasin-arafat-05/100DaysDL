
---

# (ReLU) and its some problem and variants

---

### `Rectified Linear unit (ReLU)`


# Dying Relu Porblem:

![Alt text](image-166.png)

`অনেক সময় আমরা activation function হিসেবে relu দিলে output zero হয়ে যায় । এইসব neuron কে dead neuron বলে । আর যদি আমাদের neural network এ 50% এর বেশি dead neuron থাকে তাহলে সেইটা non-linear property কে capture করতে পারে না । আর এই সমস্যাকে Dying Relu Porblem বলে । Worst case, 50% neuron dead হয়ে যেতে পারে সেইক্ষেত্রে আমাদের neural network কোন কাজেই আসবে না ।  `


## Why daying Relu Problem Occur:

![Alt text](image-167.png)

`উপরের ছবির neural network এ আমরা activation function হিসেবে relu ব্যবহার করেছি। মাঝের hidden layer  এর weighted sum যদি negative হয় তাহলে আমরা relu এর আউটপুট হিসেবে 0 পাবো ।  `

![Alt text](image-168.png)


`আর final output নির্নয়ের ক্ষেত্রে আমাদের differentiation করতে হয় বা আমরা gradient descent ব্যবহার করি । এ ক্ষেত্রে আমাদের output শূন্য আছে । আর আমাদের weight এর ভ্যালু update হয় না । তখন আমরা যেই neuron কে dead nueron বলি । সব কিছুর মূলে রয়েছে weighted sum এবং যখন সেইটা negative হয় । `


## weighted sum কখন negative হয় ?? 

![Alt text](image-169.png)

- `**High Learning Rate:** বেশি হলে differentiation(Gradient Descent) করার পর এর সাথে Learning Rate গুন দিলে একটা বড় +Ve মান পাবো । আর সেই বড় +Ve মান থেকে W_old এর ভ্যালু থেকে minus করলে আমরা একটা  negative value পাবো, যার ফলে আমারা Dying Relu Porblem এ পড়ে যাবো । `

![Alt text](image-170.png)

- `**High -Ve Bias:** যদি আমাদের Bias অনেক -Ve হয়ে যায় তাহলে সেক্ষেত্রেও আমরা Dying Relu Porblem এ পড়ে যাবো। `





