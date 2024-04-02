# Lost Function: (Lecture-06)

![Alt text](image-19.png)

# Problem with perceptron Trick : 


1st problem  এক্ষেত্রে দুইটা লাইন ঐ ঠিক । কিন্তু কার ভ্যালু কত  accurate বা কোনটা better line  তা perceptron trick quantify করতে পারে না । 

![Alt text](image-20.png)

এক্ষেত্রে সমস্যা হচ্ছে, আমরা যেই ১০০০ বার লুপ ঘুরাবো সেই ১০০০ বার  same point select হয় । যদিও এর সম্ভবনা খুব কম । 

এখন সবচেয়ে ভালো trick হলো perciption trick ব্যবহার না করে lost function ব্যবহার করা । সহগ গুলোর মান বের করার জন্য । 

# Loss Function:  ( IN ALSO ML-> Machine Learning)

The loss function is a method of evaluating how well your machine learning algorithm models your featured data set. In other words, loss functions are a measurement of how good your model is in terms of predicting the expected outcome.

### What is loss function: 
Although there are different types of loss functions, fundamentally, they all operate by quantifying the difference between a model's predictions and the actual target value in the dataset. The official term for this numerical quantification is the prediction error. The learning algorithm and mechanisms in a machine learning model are optimized to minimize the prediction error, so this means that after a calculation of the value for the loss function, which is determined by the prediction error, the learning algorithm leverages this information to conduct weight and parameter updates which in effect during the next training pass leads to a lower prediction error.



Like, এখানে একটা ফাংশন বানানো আছে এর মধ্যে ভ্যালু provide করলে যার জন্য আমরা  prediction error পাবো . উপরের ছবিতে যার prediction error 23 সেই function এর W1,W2,b এর ভ্যালু গুলো দিয়ে যে রেখা পাবো সেইটা best fit করবে । 

বিভিন্ন সমস্যা সমাধানের জন্য বিভিন্ন ধরনের lost function আছে । perceptron এর জন্য আমরা perceptron loss function নিয়ে পড়বো । 


Perceptron Loss Function: 

 এখানে, ১ম চিত্রে কোন রেখার উপর  যতগুলো misclassified point আছে তাদের সবগুলোর মান এক ধরে তাদের মোট prediction error  বের করা হয়েছে যেই টা ঠিক না । কারণ, মূলবিন্দু থেকে যার দূরত্ব বেশি তার  prediction error তত বেশি । 

তাই, ডানপাশের চিত্রে ঐ রেখা থেকে তাদের লম্ব দুরত্ব কত তা বের করে যোগ করা হয়েছে। যেহেতু রেখার দুরত্ব বের করা complex

 তাই, আমরা রেখার লাইনে cordinate এর মান গুলো বসিয়ে prediction error calculation করি । এইটা আর রেখার থেকে লম্ব দুরত্ব বের করা proportional. Overall, ভ্যালু গুলোর mod নিয়ে negative value আসলে । 


-> "f(x) parameterized by x," it's indicating a function named "f" where the output depends on the input variable "x."

Yi - (Ypredicated) = yi - (mxi+b)^2.













