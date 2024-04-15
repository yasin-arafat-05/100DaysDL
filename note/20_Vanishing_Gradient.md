
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

# কিভাবে বুঝবো আমাদের Vanishing Gradient হচ্ছে ?




