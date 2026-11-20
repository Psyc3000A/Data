R output #1 Chapter 14
https://psyc3000a.github.io/Data/Code/Rs/Ahmad/
Py version:
```python
#import all necessary libraries
np.random.seed(123456)
df = pd.DataFrame({
    "intercept": [1,1,1,1,1,1,1,1],
    "studyTime": np.array([2, 3, 5, 6, 6, 8, 10, 12])/3,
    #"priorClass": [0, 1, 1, 0, 1, 0, 1, 0]
})
#df["intercept"] = 1
df["grade"]=5 * df["studyTime"] + np.random.normal(70, 5, 8)
Y = df["grade"].to_numpy()#.reshape(-1, 1)
# create 8 x 2 matrix of zeros
X = np.zeros((8, 2))
# first column = studyTime
X[:, 0] = df["intercept"]
# first column = studyTime
X[:, 1] = df["studyTime"]
# beta hat
beta_hat = np.linalg.pinv(X) @ Y
```
