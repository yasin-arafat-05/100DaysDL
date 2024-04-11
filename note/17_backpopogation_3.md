---

# Backpopogation: (Why কেন এইটা সঠিক ভাবে কাজ করে ? আমাদের সঠিক রেজাল্ট দেয় ? )

---

### Revise the backpopogation algorithrm:

![Alt text](image-102.png)


---

# Let's understand: `Lost Function is a function of all trainable parameter`

![Alt text](image-103.png)

- আমরা একটা regression প্রবলেম এর সমাধান করতেছি । 
- লস ফাংশন হিসেবে `mse(mean_squared_error)` আর activation function  হিসেবে `liner` ব্যবহার করতেছি । 
- আমাদের লস ফাংশন (y - y_bar) যেখানে, y হলো constant । তাই লস ফাংশন শুধু মাত্র y_bar এর উপর নির্ভরশীল । 
- `forward propogation` এর মাধ্যমে আমরা y_bar এর ফরর্মূলা নির্ণয় করলাম । এখান থেকে আমরা ক্লিয়ার যে `Lost Function is a function of all trainable parameter`। 
