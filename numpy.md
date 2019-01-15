# Chapter: NumPy - [Sean Python 學習課程教材]
NumPy (Numerical Python, pronounced /ˈnʌmpaɪ/)：是Python很基礎且重要的擴充程式庫，提供強大且豐富的多維陣列與矩陣運算功能，可處理大量的多維陣列，進行線性代數、傅立葉轉換、統計分析等，並有優異的執行效能。

### 單元目標
- NumPy簡介
- 套件安裝
- 建立陣列
- 陣列操作
- 索引與排序

### NumPy簡介
- NumPy的核心是 "ndarray" - 多維陣列(multi-dimensional array; n-dimensional)資料型態。
- NumPy ndarray 和 Python lists 不同處在於，ndarray 同質且固定大小。
- ndarray 建立時就固定大小，不像 Python lists 是動態的，ndarray 改變大小就會建立一個新 ndarray 物件。
- 在 ndarray 物件中的元素為相同的資料型態。
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
注意 ndarray 是同質，所以 a4 中的資料都轉成了浮點數。<br>
ndarray 有 ndim(維度)、shape(各軸長度)、size(元素數量)、dtype(元素資料型態)、itemsize(元素資料型態的位元大小)等屬性。可以 ndarray.ndim 方式取得，以下範例註解後方是輸出結果。

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

**zeros()** 用來建立零矩陣，參數放入各軸長度(shape)，即可建立該維度的零矩陣，預設是浮點數 0，可以用 dtype=int 參數設定為整數。<br>
**ones()** 則用來建立內容均為 1 的矩陣。

```python
import numpy as np
a1 = np.zeros(5)
a2 = np.zeros((3,4),dtype=int)
print(a1)
print(a2)
```
## References 參考資料
- NumPy developers documentation-The SciPy community, http://www.numpy.org
- NumPy Wikipedia, https://en.wikipedia.org/wiki/NumPy



