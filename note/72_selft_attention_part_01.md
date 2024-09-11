
# Self Attention: Part-01

` যে কোন NLP Task Complete করার জন্য জন্য সবচেয়ে গুরুত্বপূর্ণ কাজ কি ?  `

- Ans হচ্ছেঃ Word কে Number এ convert করা । শুরুতে, `OHE` এর পর  `Bag of words, Bag of N-gram`  এই সব গুলো `(ml based)` এগুলো আসার পরে, `Word to vec (dl based)` আসে ।  । নিচের নোট গুলোর ছবি দেওয়া আছে রিভিশন করে নাও । 

<br>

`প্রথমে দেখবোঃ `

- `What is feature extraction from text?`
- `Why do you need it(feature extraction)?`
- `Is it very difucult?`

![image_01](photo/img01.jpeg)

<br>

# `# 1. ONE HOT ENCODING AND BAG OF N GRAMS: `

<br>

![image_02](photo/img02.jpeg)

<br>

# `# 2. BAG OF WORDS & BAG OF N_GRAMS: `

<br>

![image_03](photo/img03.jpeg)

![image_04](photo/img04.jpeg)

![image_04](photo/img05.jpeg)

<br>

# `# 3. TF_IDF: `

<br>

![image](photo/img06.jpeg)

<br>

![image_image](photo/img07.jpeg)

<br>

<br>

# `# 4. Word TO VEC: `

<br>

![image_image](photo/img08.jpeg)

<br>

![image_image](photo/img09.jpeg)

<br>

![image_image](photo/img10.jpeg)

<br>

![image_image](photo/img11.jpeg)

<br>

<br>
<br>

## `Problem With Word Embedding  `

<br>
<br>

- `Word Embedding capture average meaning `

![image_image](photo/image12.png)


`ধরি একটা corpus আছে যেখানে, উপরের ছবিতে থাকা ৪ টা লাইন আছে । যেখানে, প্রথম তিনটা লাইনে apple fruits  হিসেবে বাকি একটা apple technology(কোম্পানি) ব্যবহৃত হয়েছে । embedding    [x y] যেখানে, x = (apple as a fruits),  y = (apple as a technology)  হলে, আমাদের corpus এ apple fruits  হিসেবে ব্যবহৃত হয়েছে তার documnet সংখ্যা বেশি । তাই, embedding টা      [0.9 0.3] হিসেবে ব্যবহৃত হয়েছে । যেহেতু, apple fruits হিসেবে  ব্যবহৃত হয়েছে তার documnet সংখ্যা বেশি তাই, x component বা x এর value বেশি হবে ।    `


`যদি এমন কোন sentence থাকে (Apple launched a new phone while i was eating a apple) যার  word meaning আমরা বের করবো সেক্ষেত্রে, Wording embedding static (একবার embedding vector তৈরি হয়ে সেইটা বার বার ব্যবহৃত হয়)  হওয়ার  কারণে,  আগে word embedding এর embedding vector, apple এর জন্য [0.9 0.3] ছিল । তাই, এখানে, দুইটা apple এর মিনিং , x = (apple as a fruits) হিসেবে গণ্য করবে । এই সমস্যা থেকে বের হওয়ার জন্য আমাদের একটা dynamic contextual word embedding technique দরকার । যেইটা context অনুযায়ী তার embedding vector change করতে পারবে । আর আমাদের সেই contextual word embedding technique হচ্ছে, Self Attention । অর্থাৎ, উপরের sentence (Apple launched a new phone while i was eating a apple) এর ক্ষেত্রে Self Attention দুইটা Apple এর meaning দুই রকম ধরবে, অর্থাৎ, খাবার , আর technology কোম্পানি দুইটা পাবো  ।   `



