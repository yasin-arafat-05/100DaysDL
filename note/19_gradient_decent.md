---

<br> <br> <br>

---
# What i learn in ML about gradient decent:

### Gradient Descent and Cost Function

![Alt text](image-75.png)

Y = mx +C 
আমাদের ml এ  x and y এর মান দেওয়া থাকে আর আমরা এর থেকে equation টা নির্ণয় করি । এইখানে price এর মান বের করার equation বের করেছি । 

### Area vs price এর scatter plot: 
![Alt text](image-76.png)

যেহেতু এইটা linear function, তাই এখানে অনেক গুলো লাইন আকা যাবে । এখন এই লাইন গুলোর মধ্যে কোনটা বেস্ট লাইন তা কীভাবে খুঁজে বের করবো ??

![Alt text](image-77.png)

বেস্ট লাইন বের করার জন্য আমরা প্রথমে একটা যেকোন লাইন আকবো তারপর, ছবির মত  formula দিয়ে  error calculation করবো । 

![Alt text](image-78.png)

এইখানে, উপরের  formula  calculation করার পর যেই value আসে তাকে আমরা বলি mean square error, 

![Alt text](image-79.png)

- Y_i actual data point. 
- Y_predicted আমরা যে লাইন বা মডেল বা যেই hypothesis পেলাম সেইটা । 

![Alt text](image-81.png)

- এই mean square error (with summation) কে আমরা cost function বলি ।
- আর শুধু মাত্র mean square error (without summation কে ) loss function বলি ।  
- Gradient descent হলো একটা optimization algorithrm যেইটা minimize করে loss (loss function) by updating the model parameters (such as weights and biases)। 
- অন্যদিকে, Backpropagation is then employed to compute these gradients or parameter(weights and bias) efficiently by propagating the errors backward through the network, starting from the output layer to the input layer.
`অর্থাৎ, Backpropagation algorithrm এর মধ্যে আমরা Gradient Descent apply করি । `

![Alt text](image-82.png)

উপরের গ্রাফে x,y,z axis বরাবর, m,b and mse(mean square error) বিভিন্ন মান বসিয়ে যে গ্রাফ পাই এই গ্রাফের mse সবচেয়ে কম হবে গ্রাফে দেখানো   point টিতে। যেইটা blue লাইনটীকে নির্দেষ করে । এর এইটাই হচ্ছে best fit line.

![Alt text](image-83.png)

এই গ্রাফ টীকে দুইটা sub-graph এ বিভক্ত করবো  । একবার b যেই লাইন বরাবর আছে সেই লাইন বরাবর গ্রাফটিকে observe করবো আবার, m যেই লাইন বরাবর আছে সেই লাইন বরাবর গ্রাফটিকে observe করবো । 

![Alt text](image-84.png)

Step এর পরিমান, এখানে star b এর initial value indicate করে । তারপর প্রত্যেক step এ arrow আর পরিমান করে আমরা b এর ভ্যালু decrease করি ।  step এর পরিমান এত বেশি হলে আমরা global minimum miss করে যাবো তাই, আমরা step এর পরিমান আরো অনেক কম করে নিব । 

![Alt text](image-85.png)

এর জন্য আমরা b এর মান কমানোর সাথে সাথে step এর মান ও কমাতে থাকবো । আমরা যেই  পয়েন্ট এ থাকবো সেই পয়েন্ট বরাবর একটা tangent আঁকবো তারপর এই tangent বরাবর সামনের দিকে যাবো তারপর আর b এর মান কমাতে থাকবো । 

Curve line এ  tangent এর equation কীভাবে বের করবো এর জন্য আমদের partial differentiation সম্পকে জানতে হবে । 
![Alt text](image-86.png)


 m and b এর মান কীভাবে বের করবো ??
![Alt text](image-87.png)

প্রথমে, m and b এর যেকোন random value ধরে নিয়ে, উপরের formula implement করবো । 
![Alt text](image-88.png)

Code:
![Alt text](image-89.png)

With graph: 
![Alt text](image-90.png)
যখন, আমাদের cost তেমন বেশি change হচ্ছে না তখন, আমরা লুপ থেকে বের হয়ে যেতে পারি , math.close() method ব্যবহার করে । 
![Alt text](image-91.png)

--- 
---

# Stochastic Gradient Descent vs Batch Gradient Descent vs Mini Batch Gradient Descent


## Batch Gradient Descent: 

![Alt text](image-94.png)

এই  ডাটা সেটের জন্য আমরা, w1,w2 and bias এর মান বের করবো । এর জন্য আমরা, 
শুরুতে, w1,w2 and bias = 1 ধরবো,  

![Alt text](image-95.png)

তারপর, প্রথম row এর জন্য model  অনুযায়ী আমরা  error1 এইভাবে, error6 পর্যন্ত calculate করবো । একে বলে epoch যেহেতু এইটা 1st epoch তাই আমরা একে end of first epoch বলবো ।  

![Alt text](image-96.png)

প্রথম,epoch শেষ হলে আমরা mean square error calculation করে নতুন weight1, weight2 and bias এর মান adjust করবো। 
এইভাবে আমরা best fit line বা model বের করবো । 
![Alt text](image-97.png)

যে gradient descent এ আমরা সকল training sample এর error calculate করি তাকে batch gradient descent বলে । 

<br>

## Stochastic Gradient Descent: 

এখন, যদি আমাদের কাছে 10 million data থাকে সেক্ষেত্রে তো আর সব গুলো training sample এর error calculation করা possible না । আর 10 million data এর জন্য আমদের 20 million বার partial derivative করতে  হবে সেইটা computation expensive। deep learning এও এর ব্যবহার আছে । এত  বড় calculation করা আমাদের কম্পিউটারের পক্ষে সম্ভব নয় । তাই আমরা , যেকোন একটা  random sample কে সিলেক্ট করি তারপর সেইখানে gradient descent apply করি । একে আমরা বলি stochastic gradient descent . 

Difference between batch gradient and stochastic gradient descent: 
![Alt text](image-99.png)


## Mini-batch gradient descent: 

এটা SGD এর মতোই কিন্তু আমরা একটা randomly sample select করার পরিবর্তে আমরা বেশ কয়েকটি sample ব্যবহার করি । 

![Alt text](image-100.png)



<br> <br> <br>

----

# In Deep Learning:

![Alt text](image-92.png)

![Alt text](image-93.png)

<br>


---

---

#### Here are the names of different types of gradient descent algorithms:

1. Batch Gradient Descent
2. Stochastic Gradient Descent (SGD)
3. Mini-batch Gradient Descent
4. Gradient Descent with Momentum
5. AdaGrad
6. RMSProp (Root Mean Square Propagation)
7. Adam (Adaptive Moment Estimation)


<br>
<br>



