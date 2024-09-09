
---

# graduate admission (Regression problem)

---


# Output Layer:
### activation function should be linear because we are working with regression problem

```python
model.add(Dense(1,activation='linear'))
```


# While compile the model:

```python
model.compile(loss="mean_squared_error",optimizer="Adam",metrics=["accuracy"])
```


# Accuracy:

<br>
`Regression problem  এর ক্ষেত্রে আমরা r2_score  ব্যবহার করি । `                              
<br>                        


```python

from sklearn.metrics import r2_score
r2_score(y_test,y_pred)

```

---
---
