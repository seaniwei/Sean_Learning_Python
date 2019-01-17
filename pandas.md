# Chapter: Pandas - [Sean Python 學習課程教材]
Pandas 是python的一個數據分析擴充程式庫，提供高效能、易於使用的資料結構和資料分析工具。

### 單元目標
- Pandas簡介
- 套件安裝
- 建立 Series


### Pandas簡介
- 提供兩種主要的資料結構：Series 與 DataFrame。Series 是可以自訂索引值的一維序列；DataFrame 則用來處理結構化(Table like)資料，有列索引與欄標籤的二維資料集，例如關聯式資料庫、Excel、CSV 等。
- 和 Numpy 的 ndarray 不同的是 Pandas DataFrame 可以存放異質資料(不同資料型別)。
- 優異的輸入來源及輸出整合性，可以從資料庫讀取資料進 Dataframe，也可將處理完的資料存回資料庫。
- 強大的資料處理功能。

### 套件安裝
- 在 Anaconda 中，Pandas 套件已預設安裝好。
- 可以透過 pip 或 Linux 套件管理來安裝，請參考《Pandas Installation》 http://pandas.pydata.org/pandas-docs/stable/install.html

### Series(一維陣列)

```python
# 建立 Series
import pandas as pd
ironman = pd.Series([0.11,0.22,0.33,0.44])
ironman
```

```python
# Series values 屬性 & index 屬性
import pandas as pd
ironman = pd.Series([0.11,0.22,0.33,0.44])
print('ironman.values------->',ironman.values)
print('ironman.index------->',ironman.index)
```


## References 參考資料
- Pandas 官方網站, http://pandas.pydata.org/
- python 入門到分析股市, https://ithelp.ithome.com.tw/users/20111390/ironman/1791
- [Day10]Learning Pandas - Series、DataFrame、Index, https://ithelp.ithome.com.tw/articles/10204656



