<br>
<br>

# `# Transformer Encoder Part: `

<br>
<br>

![image_image](img/img40.png)

##### `Research Paper এর Transformer এ ৬টা Encoder  and Decoder Block ব্যবহার করা হয়েছে । তাই, আমরা ইচ্ছে করলে আমাদের নিজের মতো এই সংখ্যা বাড়ানো কমানো যাবে । তবে,  ৬টা ব্যবহার করার কারণ হচ্ছে, ৬টা দিয়ে বেস্ট রেজাল্ট পাওয়া যায় । তাই, উপরের চিত্রে Nx ব্যবহার করা হয়েছে ।  `

![image_image](img/img41.png)

##### `একেকটা encoder block এ, একটা Self-Attention Block and একটা Feed Forward Neural Network Block থাকে । Diagramtically, দেখতে নিচের মতো হয় । ` যেখানে, ADD মানে আমরা Residual Connection ব্যবহার করে addition । আর, Norm মানে Normalization, আমরা আগেই জেনেছি, আমরা Transformer এ layer Normalization ব্যবহার করি । Neural Network Block ব্যবহার করার কারণ হচ্ছে, আমরা এতে relu activation ব্যবহার করে, non-linearity capture করতে পারবো । 

![image_image](img/img42.png)

### `Total 6 Encoder Block Then we get Our Output:`

![image_image](img/img43.png)

![image_image](img/img44.png)


# `#01 Let's take a example sentence: `

![image_image](img/img45.png)
![image_image](img/img46.png)
![image_image](img/img47.png)
![image_image](img/img48.png)
![image_image](img/img49.png)

<br>
<br>

# `#02 Encoder Feed Forward Network: `

<br>
<br>

![image_image](img/img50.png)
![image_image](img/img51.png)
![image_image](img/img52.png)


<br>
<br>

# `#03 Some important Question: `

<br>
<br>


### `1. Why use residual connections?`
### `2. Why use FFNN?`
### `3. Why use 6 encoder block?`





