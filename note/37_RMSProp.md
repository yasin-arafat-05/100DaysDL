
---

# RMSProp (Root Mean Squared Propagation.)

---

![Alt text](img/image-219.png)

### `RMSProp হচ্ছে Improvement of AdaGrad`

![Alt text](img/image-220.png)

`AdaGrad আমরা যত global minima এর দিকে যায় তত v_t এর মান বাড়তে থাকে(V_t calculation এর সময় আমরা আগের V_t এর সাথে সাথে Loss function এর square যোগ করি তাই সময়ের সাথে সাথে v_t বাড়ে) ।`

![Alt text](img/image-221.png)

`উপরের সমস্যাটির সমাধান হিসেবে আমরা v_t এর formula change করি । এই formula তে আমরা আমাদের past epoch কে  কম ভ্যালু দেয় আর present epoch গুলোকে সবচেয়ে বেশি ভ্যালু দেই । `

![Alt text](img/image-222.png)

`উপরের, calculation থেকে আমরা বলতে পারি, 1st epoch এর value সবচেয়ে কম তারপর  2nd epoch এর value আর একটু বেশি আর সবচেয়ে বেশি হচ্ছে  3rd epoch এর value । তাই একে আমরা exponentially decaying average বলি । `

# Disadvantage:

`RMSProp এর কোন Disadvantage নেই । কিন্তু, RMSProp এর থেকে ভালো আরেকটা optimizer (Adam) আমাদের কাছে আছে । যদি কোন সমস্যার সমাধান আমরা Adam দিয়ে না পায় তাহলে, Adam এর পর আমরা  সেইটা RMSProp use করি । `



