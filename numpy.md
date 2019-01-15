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
#### array() - 建立陣列
```python
import numpy as np
a1 = np.array([1,2,3])             # Create a rank 1 array
a2 = np.array([[1,2,3],[4,5,6]])   # Create a rank 2 array
print(a1)
print(a2)
```
a1 是一維陣列，a2 是 2×3 的2維陣列，a2第一個軸(axis)的長度是2，第二個軸(axis)的長度是3。<br>
ndarray 有 ndim(維度)、shape(各軸長度)、size(元素數量)、dtype(元素資料型態)、itemsize(元素資料型態的位元大小)等屬性。<br>

```python
import numpy as np
a1 = np.array([1,2,3])             # Create a rank 1 array
a2 = np.array([[1,2,3],[4,5,6]])   # Create a rank 2 array
print(a1.ndim)      # axes, dimensions
print(a2.ndim)      # axes, dimensions
print(a1.shape)     # the length of each axes
print(a2.shape)     # the length of each axes
print(a1.size)      # the total number of elements
print(a2.size)      # the total number of elements
print(a1.dtype)     # the type of the elements in the array
print(a1.itemsize)  # the size in bytes of each element
```

## References 參考資料
- NumPy developers documentation-The SciPy community, http://www.numpy.org
- NumPy Wikipedia, https://en.wikipedia.org/wiki/NumPy


