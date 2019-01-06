# Sean Python 學習課程教材
Learning Python tutorials and materials<br>
<h2>Control Flow Statements: if</h2>
什麼是程式？<br>
<strong>"Algorithms + Data Structures = Programs"</strong> by Niklaus Wirth (1976) - 1984 Turing Award<br>
處理（控制）流程 + 資料：就是程式！<br>
if 敘述是最常用的控制流程判斷式，以下是 if 敘述的內容和結構。<br>
<h3>if 敘述：</h3>

```Python
if condition expression:
	statement(s)
elif condition expression:
	statement(s)
else:
	statement(s)
```
<h3>結構說明：</h3>
<strong>if</strong> - if 敘述關鍵字，必要。<br>
<strong>condition express</strong> - 條件判斷式，必要。<br>
<strong>:</strong> - Python 敘述結尾符號，必要。<br>
<strong>statement(s)</strong> - 若符合條件時要執行的動作敘述，必須內縮(縮排)，必要。<br>
<strong>elif</strong> - 若 if 的條件不符合，就再判斷這個條件，非必要。<br>
<strong>else</strong> - 若前述的條件統統都不符合，就執行這裡的動作，非必要。<br>
<h3>範例：</h3>

```Python
if 5 > 2:   # 如果 (5 > 2) 則印出 "5 > 2 為真(True)"
	print("5 > 2 為真(True)")
```



