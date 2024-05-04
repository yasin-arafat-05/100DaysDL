
---

# Padding & Strides

---

`Problem with filter: আমরা filter ব্যবহার করার পর যে feature map পায় সেখানে আমাদের dimention এর কমে যায় । যেমনঃ 6x6 এর জন্য 3*3 হলে আমরা 4*4 এর feature map পায় । আর filter করার সময় ছবির উপরের যে pixel গুলো থাকে সেইগুলোকে fillter করার করার পর আমরা যেই feature map পায় সেখানে উপরের pixel গুলোর importance  কমে যায় । যদি side এ information বেশি থাকে তাহলে filter করার পর আমরা যেই feature map পাবো যেইখানে side এর information গুলো পাবো না । `

