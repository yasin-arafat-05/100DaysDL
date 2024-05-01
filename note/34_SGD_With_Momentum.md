
---

# SGD With Momentum:

---

# `First we learn some Basic: `

### Understanding Graphs:

![Alt text](image-178.png)

`2D,3D and Contour Plot.`

![Alt text](image-179.png)

`আমরা জানি, neural network এ weight and bias এর সঠিক মান বের করার বা Loss কে কম করার জন্য আমরা Loss function ব্যবহার করি । আমরা যেমনঃ Math এ কোন function দেওয়া থাকলে আমরা তার আঁকতে পারি, তেমন ভাবে আমরা Loss function  এর গ্রাফ আঁকলে উপরের গ্রাফ গুলো পাবো । আমরা জানি, Loss Function একটা nueral network যতগুলো parameter(weight+bias) থাকে তাদের উপর নির্ভর করে । এখন আমাদের কাছে কোন একটা nueral network এ যদি (15 weight  আর 10 bias থাকে) তাহলে তার গ্রাফ হবে 25D । কিন্তু সমস্যা হচ্ছে, মানুষ 3D বা এর কম dimention ছাড়া কোন কিছু ভালো করে observe করতে পারে না । তাই আমাদের দরকার Contour Plot । উপরের 3D  Plot কে Contour Plot represent করেছি । `

- `2D তে একটা axis এ Loss অন্য একটা  axis weight (assuming that, we have only one weight and no bias.)`

- `3D তে একটা axis এ Loss অন্য একটা  axis weight আর অন্য একটা  axis এ bias। `

<br> <br>
# Contour Plot Examples:

![Alt text](image-182.png)

` আমরা যেহেতু higer dimention থেকে lower dimention যচ্ছি তাই আমরা অনেক গুলো dimention হারিয়ে ফেলছি সেইগুলোকে আমরা color এর মাধ্যমে represent করতেছি contour graph এ । যেমনঃ উপরের ছবিতে yello color যেইটা একটু উপরের দিকে আছে । আর purple color একটু নিচের দিকে আছে ।  `

![Alt text](image-183.png)


![Alt text](image-184.png)


![Alt text](image-185.png)


![Alt text](image-186.png)


![Alt text](image-187.png)


![Alt text](image-188.png)


![Alt text](image-189.png)


![Alt text](image-190.png)



<br> <br> <br>


# Convex vs Non-Convex:

![Alt text](image-180.png)

`আমাদের loss function এর গ্রাফে যদি একটা minima থাকে তাহলে সেইটা কে গ্রাফ Convex বলে । আর যদি একাধিক minima  থাকে (local+global) তাহলে সেইটা কে non-convex গ্রাফ বলে । একটা non-convex গ্রাফে এ saddle point(আগে দেখেছি),local minima, global minima আর high curvature থাকতে পারে । `

![Alt text](image-181.png)

`**High Curvature:** উপরের ছবিতে দুইটা বৃত্ত আছে । এখন, বড় বৃত্তটির radius বড় আর ছোট বৃত্তটির radius ছোট । যার radius বড় তার curvature ছোট আর যার radius ছোট তার curvature বড় । বড় curvature গুলো  traverse  করা কষ্টকর। এই সমস্যা গুলোর জন্য আমাদের SGD,BGD,mini-BGD ভালো করে solve করতে পারে না । তাই আমাদের optimizer এর দরকার হয় । `

# Momentum Optimization

![Alt text](image-192.png)

`Non-convex এর ক্ষেত্রে আমরা যেই সমস্যা গুলো ফেইস গুলো সব গুলোকে Momentum Optimizer solve করতে পারে । `



