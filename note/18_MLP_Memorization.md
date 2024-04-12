<br>
<br>

---

<br>
<br>

# What is Memoization?

![Alt text](image-110.png)

`google defination: dp cpp দিয়ে পড়ার সময় আমরা memoization এর defination দেখেছিলাম এখানে তেমন ভাবেই দেওয়া । `


---

# HOw to use memoization in a neural network using backpopagration algorithrm:


![Alt text](image-111.png)

আমরা neural network এর যত ইনপুট এর দিকে যাবো আমাদের derivative তত বেশি  complex হওয়া শুরু করবে । 

`নিচে mathematical ফরমুলা দেওয়া হয়েছে যদি derivative দুইটা variable এর নির্ভর করে তখন তাদের কীভাবে বের করতে হয় । `

<br>

![Alt text](image-112.png)

আমরা যতই  neural network এর যত ইনপুট এর দিকে যাচ্ছী ততই আমাদের derivative complex হওয়া শুরু করছে আর derivative repeat হচ্ছে । এখানে, back propagation algorithm memoization ব্যবহার করে । 

