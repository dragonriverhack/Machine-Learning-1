# scikit-learn

### 常用
* 划分验证集

```python
from sklearn.cross_validation import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=0)
```
* Grid Search 
```python
param_grid = {'n_estimators': [300, 500], 'max_features': [10, 12, 14]}
model = grid_search.GridSearchCV(estimator=rfr, param_grid=param_grid, n_jobs=1, cv=10, verbose=20, scoring=RMSE)
model.fit(X_train, y_train)
```
* LabelEncoder
```python
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
le.fit([1,5,67,100])
le.transform([1,1,100,67,5])
#输出： array([0,0,3,2,1])
#可通过le.inverse_transform(x)转换回去
```
* sklearn.utils.shuffle(多个数组按同样顺序打乱)
```python
def fill_feed_dict(data_X, data_Y, batch_size):
    """Generator datasets to yield batches"""
    # Shuffle data first.
    shuffled_X, shuffled_Y = shuffle(data_X, data_Y)
    for idx in range(data_X.shape[0] // batch_size):
        x_batch = shuffled_X[batch_size * idx: batch_size * (idx + 1)]
        y_batch = shuffled_Y[batch_size * idx: batch_size * (idx + 1)]
        yield x_batch, y_batch
```

### 算法
* [GBDT（MART）迭代决策树入门教程 | 简介](http://blog.csdn.net/suranxu007/article/details/49910323)

### 实现
* [常用算法调用(LR/ RF/ GBDT/ knn/ SVM)](./useful.py)
* [logistic回归](./sklearn_LR.py)
* [皮尔逊相关度](./pearsonr.ipynb)
* [利用kmeans对图片颜色聚类并可视化](./demo/kmeans_color.py)
* [高维数据可视化tSNE](./demo/tSNE.py)

### Choosing the right estimator

![Choosing the right estimator](./choose.png)






