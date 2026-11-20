R output #1 Chapter 14
https://psyc3000a.github.io/Data/Code/Rs/Ahmad/
Py version:
```python
#import all necessary libraries
betas=[5,10]
np.random.seed(1234567)
df = pd.DataFrame({
    "studyTime": np.array([2, 3, 5, 6, 6, 8, 10, 12])/3,
    "priorClass": [0, 1, 1, 0, 1, 0, 1, 0]
})
#grade=5(studyTime)+10(priorClass)+ϵ
df["grade"]=betas[0] * df["studyTime"] + betas[1] * df["priorClass"] + np.random.normal(70, 5, 8)
Y = df["grade"].to_numpy()#.reshape(-1, 1)
# create 8 x 2 matrix of zeros

X = np.column_stack([
    np.ones(len(df)), #intercept
    df["studyTime"], 
    df["priorClass"]
])

# beta hat
beta_hat = np.linalg.pinv(X) @ Y
```
