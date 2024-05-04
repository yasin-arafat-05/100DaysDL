
---

# Padding & Strides

---

`Problem with filter: আমরা filter ব্যবহার করার পর যে feature map পায় সেখানে আমাদের dimention এর কমে যায় । যেমনঃ 6x6 এর জন্য 3*3 হলে আমরা 4*4 এর feature map পায় । আর filter করার সময় ছবির উপরের যে pixel গুলো থাকে সেইগুলোকে fillter করার করার পর আমরা যেই feature map পায় সেখানে উপরের pixel গুলোর importance  কমে যায় । যদি side এ information বেশি থাকে তাহলে filter করার পর আমরা যেই feature map পাবো যেইখানে side এর information গুলো পাবো না । এই প্রবলেম দুইকে কে solve করে padding । `

# Padding :

![Alt text](image-249.png)

`Actual image এর চারপাশে আমরা zero দিয়ে padding করে দেয় । একে padding with zero বলে । `

![Alt text](image-250.png)

`zero দিয়ে padding করার পর (Actual image 5x5, After padding 7x7) হলে আমরা আউটপুট হিসেবে input image এর সমান dimention এর আউট পায় । `


![Alt text](image-251.png)

`kears এ দুইধনের filter আছে । i)Valid দিলে Actual image পরিবর্তিত করে ।   আর ii)Same দিলে kears, Actual image অপরিবর্তিত রাখে । `

<br>

---

<br>

## Code Demo of Keras:

<br>

---

<br>




