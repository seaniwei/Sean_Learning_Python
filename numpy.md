# Chapter: NumPy - [Sean Python 學習課程教材]
NumPy (Numerical Python, pronounced /ˈnʌmpaɪ/)：是Python很基礎且重要的擴充程式庫，提供強大且豐富的多維陣列與矩陣運算功能，可處理大量的多維陣列，進行線性代數、傅立葉轉換、統計分析等，並且有優異的執行效能。

### 單元目標
- NumPy簡介
- 套件安裝
- 建立陣列
- 讀取陣列
- 基本運算

### NumPy簡介
- NumPy的核心是 "ndarray" - 多維陣列(multi-dimensional array; n-dimensional)資料型態。
- NumPy ndarray 和 Python lists 串列不同處在於，ndarray 同質且固定大小。
- ndarray 在建立時就固定大小，不像 Python lists 是動態的，ndarray 改變大小就會建立一個新 ndarray 物件。
- 在 ndarray 物件中的元素均為相同的資料型態。
- 在處理大量的資料時，NumPy 比 Python 內建序列資料型態更有效率且更方便。
- 因此 NumPy ndarray 被許多 Python 套件當作基礎的處理資料型態而被廣泛運用。

### 套件安裝
- 在 Anaconda 中，NumPy 套件已預設安裝好。
- 可以透過 pip 或 Linux 套件管理來安裝，請參考《Installing NumPy》 https://scipy.org/install.html

### 建立陣列
**array()** 參數放入 list 串列或 tuple 元組資料，即可建立陣列。<br>

```python
import numpy as np
a1 = np.array((1,2,3))                 # Create a rank 1 array with tuple
a2 = np.array([1,2,3])                 # Create a rank 1 array with list
a3 = np.array([[1,2,3],[4,5,6]])       # Create a rank 2 array
a4 = np.array([(1.5,3),(2,4),(3.0,6)]) # Create a rank 2 array
print(a1)
print(a2)
print(a3)
print(a4)
```

a1 中放入 tuple，a2 放入 list 都會產生一維陣列，a3 是 2x3 的2維陣列，a2 第一個軸(axis)的長度是2，第二個軸(axis)的長度是3。a4 是 3x2 的2維陣列。<br>
注意 ndarray 是同質，所以 a4 中的所有元素都轉成了浮點數資料型態。<br>
ndarray 有 ndim(維度)、shape(各軸長度)、size(元素數量)、dtype(元素資料型態)、itemsize(元素資料型態的位元大小)等屬性。可用 ndarray.ndim 方式取得，以下範例註解後方是輸出結果。

```python
import numpy as np
a1 = np.array([1,2,3])                 # Create a rank 1 array
a2 = np.array([[1,2,3],[4,5,6]])       # Create a rank 2 array
a3 = np.array([(1.5,3),(2,4),(3.0,6)]) # Create a rank 2 array
print(a1.ndim)      # axes/dimensions --> 1
print(a2.ndim)      # axes/dimensions --> 2
print(a1.shape)     # the length of each axes --> (3,)
print(a2.shape)     # the length of each axes --> (2,3)
print(a3.shape)     # the length of each axes --> (3,2)
print(a1.size)      # the total number of elements --> 3
print(a2.size)      # the total number of elements --> 6
print(a3.size)      # the total number of elements --> 6
print(a1.dtype)     # the type of the elements in the array --> int64
print(a3.dtype)     # the type of the elements in the array --> float64
print(a1.itemsize)  # the size in bytes of each element --> 8
print(a3.itemsize)  # the size in bytes of each element --> 8
```

**zeros()** 用來建立零矩陣，參數放入各軸長度(shape)，即可建立該維度的零矩陣，預設是浮點數 0，可以用 dtype=int 參數設定為整數。<br><br>
**ones()** 用來建立元素均為 1 的矩陣，預設是浮點數 1。<br><br>
**eye()** 用來建立對角元素皆為1，其他元素皆為零的單位矩陣(identity matrix)，預設是浮點數。<br><br>
**full()** 用來建立元素均相同的矩陣。<br><br>
**random.random()** 可建立元素為隨機值的矩陣。<br><br>
**arange([start,]stop,[step,]dtype=None)** 可產生指定間隔的數列：start 為起始值，預設為 0，stop 為終值，step 為間隔值。<br><br>
**linspace(start,stop,num=50,endpoint=True,retstep)** 在2數間產生指定個數的相同間隔數列：start 為起始值，stop 為終值，num 為數列個數，endpoint 為是否包含終值，預設為 True (包含)，retstep 是否回傳間隔值。<br><br>
**reshape(a,newshape)** 改變矩陣的 shape 維度：a 為要改變的矩陣，newshape 為改變後的 shape 維度。<br><br>
**ravel(a)** 攤平矩陣，由多維陣列變一維陣列：a 為要攤平的矩陣。<br><br>
**ravel(a)** 攤平矩陣，由多維陣列變一維陣列：a 為要攤平的矩陣。<br><br>

```python
import numpy as np
a1 = np.zeros(3)
a2 = np.zeros((2,3),dtype=int)
a3 = np.eye(3)                # Create a 3x3 identity matrix
a4 = np.full((2,2),5)         # Create a constant array
a5 = np.random.random((2,2))  # Create an array filled with random values
a6 = np.arange(10)            # [0,1,2,3,4,5,6,7,8,9]
a7 = np.arange(0,10,2)        # [0,2,4,6,8]
a8 = np.arange(0,3,0.5)       # [0.,0.5,1.,1.5,2.,2.5]
a9 = np.linspace(2,3,num=5)   # [2.,2.25,2.5,2.75,3.]
a10 = np.linspace(2,3,num=5,endpoint=False)  # [2.,2.2,2.4,2.6,2.8]
a11 = np.linspace(2,3,num=5,retstep=True)    # array([2.,2.25,2.5,2.75,3.]),0.25)
a12 = np.arange(6)            # [0,1,2,3,4,5]
a13 = np.reshape(a12,(3,2))
a14 = np.arange(6).reshape((3,2))
a15 = np.reshape(a14,(2,3))
a16 = np.reshape(a15,6)
a17 = np.arange(24).reshape(2,3,4)  # Create a 2x3x4 3d array
a18 = np.ravel(a17)   				# returns the flattened array
```

### 讀取陣列
NumPy ndarray 可如同 Python lists 串列以索引(index)進行 indexing, slicing, iterating 並存取元素。<br>
indexing 和 slicing 的方法和 Python lists 相同。但 slicing 產生的陣列是原陣列的 view，修改會影響到原陣列。<br>
同樣可使用 for 迴圈讀取 NumPy ndarray 中的資料，稱為 iterating (迭代、反覆)。<br>

```python
# One-dimensional arrays indexing, slicing
import numpy as np
a = np.arange(10)
a[2]
a[2:5]
a[0:10:2] = -10  # set every 2nd element to -10
a[ : :-1]        # reverse 反轉
```

```python
# Multidimensional arrays indexing, slicing
import numpy as np
a = np.arange(20).reshape((5,4))
print(a)
print(a[2,3])
print(a[0:5, 1])  # each row in column 1
print(a[:, 1])    # each row in column 1
print(a[1:3, :])  # row 1~2
print(a[-1])      # the last row. Equivalent to a[-1, :]
```

```python
# A slice of an array is a view into the same data, so modifying it will modify the original array.
import numpy as np
a = np.arange(20).reshape((5,4))
b = a[:2, 1:3]
print(b)
b[0, 0] = 99 # 修改 sliced matrix 中的元素
print(a)
```

```python
# Iteration over one-dimensional arrays
import numpy as np
a = np.arange(10)
for i in a:
    print(i)
```

```python
# Iteration over multidimensional arrays
import numpy as np
a = np.arange(20).reshape((5,4))
for row in a:
    print(row)
    
# 以 flat 屬性將 multidimensional arrays 中的元素逐一取出
for i in a.flat:
    print(i)
```

### 基本運算
NumPy 中以元素為單位(elementwise)進行處理的運算與函數被稱為 Universal Functions(ufunc, 聚合功能)。<br>
和 MATLAB 及一般矩陣運算不同，NumPy 中的 * 是 elementwise multiplication 一般乘法；使用 @ 運算子(python >= 3.5) 或 dot() 才是矩陣乘積(matrix product)。<br>

```python
# Elementwise array arithmetic operations & Universal Functions
import numpy as np
a = np.array([[4,4],[2,2]])
b = np.array([[2,2],[1,1]])

# Elementwise sum
print(a + b)
print(np.add(a, b))

# Elementwise difference
print(a - b)
print(np.subtract(a, b))

# Elementwise product
print(a * b)
print(np.multiply(a, b))

# Elementwise division
print(a / b)
print(np.divide(a, b))

print(10*np.sin(a))

print(np.sqrt(a))

# Logical operation 邏輯運算
print(a<35)
```

```python
# NumPy Universal Functions
import numpy as np
a = np.arange(12).reshape((3,4))
print(a)
print(a.sum())  # 元素加總
print(a.max())  # 回傳最大元素
print(a.min())  # 回傳最小元素
print(a.argmax())     # 回傳最大元素的索引
print(a.argmin())     # 回傳最小元素的索引
print(a.sum(axis=0))  # 以 row 進行加總(column元素)
print(a.sum(axis=1))  # 以 column 進行加總(row元素)
print(a.max(axis=0))  # 以 row 回傳最大元素
print(a.min(axis=1))  # 以 column 回傳最小元素
```

```python
# matrix product
import numpy as np
a = np.array([[1,1],[0,1]])
b = np.array([[2,0],[3,4]])
print(a * b)        # elementwise product
print(a @ b)        # matrix product
print(a.dot(b))     # matrix product with dot()
print(np.dot(a, b)) # matrix product with dot()
```

## References 參考資料
- NumPy developers documentation-The SciPy community, http://www.numpy.org
- NumPy Wikipedia, https://en.wikipedia.org/wiki/NumPy
- Stanford cs213n Python-numpy-tutorial, http://cs231n.github.io/python-numpy-tutorial/



