---

# Problem with Perceptron:

--- 

Perceptron একটা liner model এইটা non-linear decision boundary create করতে পারে না এর জন্য আমরা MLP(multi-layer perceptron) ব্যবহার করি । MLP ব্যবহার করে একটা বড় neural network বানাতে পারি যেইটা `universal function approximator` হিসেবে কাজ করে non-linear decision boundary create করতে পারবে । 

<br>

![Alt text](img/image-33.png)

এইখানে, আমাদের একটা dataset এ দুইটা class আছে । এই class দুইটাকে আলাদা করার জন্য আমাদের একটা boundary লাগবে যেইটা non-linear decision boundary . আমরা perceptron ব্যবহার করে এই non-linear decision boundary create করবো।  

---

# How perceptron work with sigmoid

---

এখানে আমরা, activation funciton  হিসেবে sigmoid function আর loss function হিসেবে logloss function ব্যবহার করবো । logloss যেইটা logistic regression এর equivalent . Picture from sk-learn documentation:

![Alt text](img/image-35.png)


<br> <br>

iq,cgpa and placement এর example এর ক্ষেত্রে, <br>

![Alt text](img/image-34.png)

cgpa = 3.7, iq = 8.7, w_1 = 5, w_2 = 10 and b = 3, আমাদের model এর equation হচ্ছে, W1 * cgpa + W2 * iq + b 
এখন, z এর মান  z = W1 * cgpa + W2 * iq + b  calculation করে আমরা যেই মান পাবো সেইটা activation function (sigmoid) এ বসিয়ে এই node এর output পাবো । 
<br>

sigmoid এর output এর range (0 ~ 1 ) । আমাদের যেই model আছে সেই model এর উপর sigmoid এর ouput হবে 0.5 । এর পর উপরের দিকে sigmoid এর output 0.5 এর থেকে বেশি (placement এর probability p(Y->yes) বাড়বে ) হবে  similarly placement না হওয়ার probability p(N->no) কমবে ।  

<br>


### Multilayer perceptron visulization: 

![Alt text](img/image-36.png)

এখানে আমরা দুইটা perceptron এর model generate করেছি । তারপর এই দুইটা টা perceptron এর decision boundary কে আমরা add করবো । তারপর সেইটাকে smooth করে নতুন একটা non-linear decision boundary পাবো । 

![Alt text](img/image-37.png)

<br>

`উপরের জিনিসটা mathematically কীভাবে proof করা যেতে পারেঃ `

![Alt text](img/image-38.png)

আমরা প্রথমে ডাটাসেটের একটা point এর সাপেক্ষে দুইটা model এর output বের করছি । প্রথমটা 0.7 এবং দ্বিতীয় টা 0.8 । তারপর এই দুইটার probability যোগ করে পাই, 1.5 কিন্তু আমাদের ভ্যালু এর range ( 0 ~ 1) এই ভ্যালু কে আমরা আবার, sigmoid function এ দিয়ে যেই ভ্যালু পাবো সেইটা হচ্ছে final ans . এক্ষেত্রে, 0.82 অর্থাৎ তার placement done. এইভাবে আমরা non-linear decision boundary বের করতে পারি । 

![Alt text](img/image-39.png)

<br> <br>

### Dominating a specific perceptron: 

![Alt text](img/image-40.png)

এখানে আমাদের কাছে দুইটা perceptron আছে । এখন, আমরা কি আমাদের model কে এমন ভাবে train করতে পারি না যাতে perceptron ১ এর বেশি domination করে । 


![Alt text](img/image-41.png)


আগের বার আমরা শুধু probabilit গুলো যোগ করেছিলাম কিন্তু এইবার আমরা (weighted addition) করবো । যার piority বেশি দিতে চায় আর wight বেশি দিব পরের টা কম দিয়ে যেই ভ্যালু পাবো তার sigmoid করবো । 

![Alt text](img/image-42.png)

ইচ্ছে করলে আমরা এর মধ্যে bias term add  করতে পারি । পরে বাকি student গুলোর জন্য আমরা সেম জিনিস ওই করতে পারি । এইভাবে আমাদের multi-layer perceptron কাজ করে । 

<br>

### Visualization: 

![Alt text](img/image-43.png)

![Alt text](img/image-44.png)

cgpa এর ভ্যালু দুইটা perceptron এই যাচ্ছে একই সাথে iq এর ভ্যালু দুইটা একই সাথে দুইটা perceptron এই যাচ্ছে ।


### Let's view a more complex structure:

`Neural Network Architecture: ` node বা perceptron গুলো একে অপরের সাথে কিভাবে connected । আমরা আমাদের প্রয়োজন মতো architecture এ changes করতে পারি । Total 4 way দেখবো আমরা neural network এর architecture change  করার । 


- `Increase the number of perceptron in hidden layer : `
আগের উদাহারনে আমরা দুই টা node দেখেছিলাম । এখানে আমরা 3 টা node দিয়ে কাজ করতেছি । ৩ টা কাজ করার সুবিধা হচ্ছে এই খানে আমাদের non-linear boundary আগের থেকে complex . আমাদের কাছে যত বেশি non-linear boundary complex হবে আমরা তত বেশি extra node add করবো । 

![Alt text](img/image-45.png)

- `Increase the number of node in the input layer: `
এইটা শুধু তখনই করতে পারবো যখন আমাদের dataset এ number of column বাড়বে । এক্ষেত্রে আমরা 3d graph পাবো ।  আর perception model হিসেবে 2d plane পাবো । তারপর এদের কে linearly combine করে activation function এ দিব । 

![Alt text](img/image-46.png)


- `Increase the number of node in the output layer: `
Multicalss classification এর ক্ষেত্রে, output layer এ অনেক গুলো node থাকে । একটা image input দিলাম সেইটা dog,cat or human কোনটা এর জন্য আলাদা আলাদা output layer এ 3 টা perceptron থাকবে । output এ যার probability  বেশি থাকবে output এ সেই perceptron এর ছবি আসবে । 

![Alt text](img/image-48.png)


- `Increase the number of hidden  layer: `
আমাদের কাছে যদি non-linearity অনেক অনেক বেশি হয় সেক্ষেত্রে আমরা multiple hidden layer add করতে পারি । আমরা যদি enough time and enough data দেয় তাহলে যেকোন non-linearity বা অনেক অনেক বেশি complex  function achieve করতে পারি । তাই perceptron কে `universal function approximator` বলে । 

![Alt text](img/image-49.png)

